---
sourcePath: ru/ydb/ydb-docs-core/ru/core/reference/ydb-sdk/recipes/debug/_includes/jaeger/go.md
---
```go
package main

import (
	"context"
	"time"

	"github.com/opentracing/opentracing-go"
	jaegerConfig "github.com/uber/jaeger-client-go/config"

	"github.com/ydb-platform/ydb-go-sdk/v3"
	"github.com/ydb-platform/ydb-go-sdk/v3/trace"

	tracing "github.com/ydb-platform/ydb-go-sdk-opentracing"
)

const (
	tracerURL   = "localhost:5775"
	serviceName = "ydb-go-sdk"
)

func main() {
	tracer, closer, err := jaegerConfig.Configuration{
		ServiceName: serviceName,
		Sampler: &jaegerConfig.SamplerConfig{
			Type:  "const",
			Param: 1,
		},
		Reporter: &jaegerConfig.ReporterConfig{
			LogSpans:            true,
			BufferFlushInterval: 1 * time.Second,
			LocalAgentHostPort:  tracerURL,
		},
	}.NewTracer()
	if err != nil {
		panic(err)
	}

	defer closer.Close()

	// set global tracer of this application
	opentracing.SetGlobalTracer(tracer)

	span, ctx := opentracing.StartSpanFromContext(context.Background(), "client")
	defer span.Finish()

	db, err := ydb.New(
		ctx,
		...
		ydb.WithTraceDriver(tracing.Driver(
			tracing.WithDetails(trace.DetailsAll),
		)),
		ydb.WithTraceTable(tracing.Table(
			tracing.WithDetails(trace.DetailsAll),
		)),
	)
	if err != nil {
		panic(err)
	}
	defer func() {
		_ = db.Close(ctx)
	}()
}
```