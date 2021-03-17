# Как отредактировать задачу

Чтобы изменить задачу, перейдите на ее страницу. Если у вас не хватает прав для редактирования, [запросите их](../faq.md#section_xgr_zng_4bb) у владельца очереди или администраторавашей организации.

{% note info %}

Страницы задач обновляются в реальном времени. Если кто-то изменит или прокомментирует задачу, страница которой открыта, вы увидите уведомление об этом.

{% endnote %}

## Изменить описание задачи {#section_yrw_npn_jz}

Справа от описания задачи нажмите значок ![](../../_assets/tracker/icon-edit.png) и отредактируйте текст. Для форматирования текста используйте [вики-разметку](wiki-markup.md). Чтобы сохранить изменения, нажмите кнопку **Сохранить**.

В описании задачи можно указать ключ любой другой задачи — тогда {{ tracker-name }} автоматически их свяжет.

{% note info %}

Если в тексте вам необходимо вставить ссылку на другую задачу, но при этом избежать связывания, перед ключом задачи укажите `st:` (например, `st:TEST-1234`). В таком случае в тексте появится [магическая ссылка](wiki.md#magic-link-descr), но связь между задачами создана не будет.
Полностью отключить автоматическое связывание задач из разных очередей можно в [настройках очереди](../manager/edit-queue-general.md).

{% endnote %}

Если вы не сохранили описание задачи и закрыли либо перезагрузили страницу, ваше описание сохранится в черновиках. Чтобы восстановить текст из черновика, снова нажмите значок редактирования ![](../../_assets/tracker/icon-edit.png), затем на панели инструментов нажмите значок ![](../../_assets/tracker/drafts.png) и выберите черновик.

## Добавить комментарий {#sec_comment}

Чтобы прокомментировать задачу, введите текст в поле в нижней части страницы. В комментариях вы можете использовать [вики-разметку](wiki-markup.md), а также прикреплять к ним изображения и файлы.

В описании задачи можно указать ключ любой другой задачи — тогда {{ tracker-name }} автоматически их свяжет.

Если вы не отправили комментарий и закрыли либо перезагрузили страницу, текст вашего комментария сохранится в черновиках. Чтобы восстановить текст из черновика, на панели инструментов над полем комментария нажмите значок ![](../../_assets/tracker/drafts.png) и выберите черновик.

Подробнее о действиях с комментариям читайте в разделе [{#T}](comments.md).

## Изменить параметры задачи {#section_jqw_ppn_jz}

[Параметры задачи](create-param.md#section_ymd_ycj_1gb) отображаются на панели справа. Чтобы изменить значение параметра, нажмите на его название. Чтобы сохранить изменения, нажмите кнопку **ОК**.

Если вы не видите на панели справа нужных параметров, добавьте их с помощью кнопки ![](../../_assets/tracker/task-params-btn.png).

## Прикрепить к задаче изображения и файлы {#section_qyt_4nx_pz}

Чтобы прикрепить файл к описанию задачи:

1. Нажмите кнопку ![](../../_assets/tracker/icon-edit.png) возле описания задачи.

1. Перетащите файлы на область под описанием или воспользуйтесь кнопкой **Выберите файлы**. Размер прикрепляемого файла не может превышать 200 МБ.
    Чтобы разместить прикрепленные к задаче изображения в тексте описания, нажмите кнопку ![](../../_assets/tracker/add-image.png).

1. Нажмите кнопку **Сохранить**.

Таким же образом можно прикрепить файл к комментарию.

Прикрепленные файлы отображаются под описанием задачи или под комментарием.

Чтобы просмотреть список всех файлов, размещенных на странице задачи, перейдите на вкладку **Файлы** под описанием задачи. Файлы, добавленные в {{ tracker-name }}, не занимают место на Яндекс.Диске. Ограничение на объем данных, хранимых в {{ tracker-name }}, отсутствует. 

## Добавить связь с другой задачей {#section_wz1_rpn_jz}

Чтобы связать задачу с другой задачей:

1. Выберите **Действия** → **Добавить связь**.

1. Выберите подходящий тип связи.

1. Укажите ключ задачи, с которой нужно создать связь. Найти ключ можно на странице задачи сразу под заголовком (например, `TEST-1234`).

1. Нажмите **Добавить связь**.

Подробнее о связях читайте в разделе [{#T}](ticket-links.md).

{% note info %}

Связь с задачей создается автоматически, если указать ее ключ в комментарии или описании.

{% endnote %}

## Связать коммит с задачей {#sec_commit}

Вы можете привязать к задаче коммит в репозиторий, который [подключен к {{ tracker-name }}](../manager/add-repository.md). Для этого укажите ключ задачи в комментарии к коммиту. Привязанные коммиты можно просмотреть:

- на странице задачи на вкладке **Коммиты**;
- на странице очереди на вкладке **Коммиты**.

Если вы не видите вкладки **Коммиты**, убедитесь, что она включена в [настройках очереди](../manager/edit-queue-general.md).

## Настроить отображение дат {#section_e2p_zqx_vgb}

Параметры, содержащие дату, и время могут отображаться в задаче в полном (день, месяц, год и время) и сокращенном (день и месяц) форматах.

Чтобы изменить формат отображения таких параметров:

1. На верхней панели {{ tracker-name }} нажмите ![](../../_assets/tracker/tracker-settings.png) → **Персональные настройки**.


    {% note info %}

    Вы также можете перейти по ссылке [https://tracker.yandex.ru/settings](https://tracker.yandex.ru/settings).

    {% endnote %}

1. В блоке **Формат дат** выберите нужный формат.

1. Нажмите кнопку **Сохранить**.

## Настроить отображение пользователей {#section_gmp_wn4_xgb}

Вы можете изменить отображение имен пользователей на странице задачи.

1. На верхней панели {{ tracker-name }} нажмите ![](../../_assets/tracker/tracker-settings.png) → **Персональные настройки**.


    {% note info %}

    Вы также можете перейти по ссылке [https://tracker.yandex.ru/settings]({{ link-settings }}).

    {% endnote %}

1. Выберите одну или несколько опций:

    |     |     |
    |-----|-----|
    |**Показывать логин вместо имени** | В полях типа Пользователь данные отображаются в виде логина.|
    |**Включить режим портретов для списков пользователей** | Если в полях типа Пользователей указано несколько значений, вместо имен пользователей отображаются их портреты. Например, список пользователей может находиться в поле **Исполнитель** при выборе нескольких значений.|

1. Нажмите кнопку **Сохранить**.

## Перенести задачу в другую очередь {#section_xwx_qpn_jz}

{% note alert %}

Когда вы переносите задачу, ее подзадачи остаются в исходной очереди. 


{% endnote %}

Чтобы перенести задачу:

1. Выберите **Действия** → **Изменить очередь**.

1. Укажите очередь, в которую вы хотите перенести задачу.

1. При необходимости уточните параметры задачи и нажмите кнопку **Перенести**.


