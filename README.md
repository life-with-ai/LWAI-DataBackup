# DataBackup – Life with AI 1.6.0

[Русский](#русский) | [English](#english)

## Русский

### Назначение

Резервное копирование проектов и рабочих документов в виде обычной файловой копии или ZIP-архива. Для каждого проекта или сценария можно создать отдельный профиль и сохранить в нём пути к исходным данным и месту размещения резервной копии, формат результата, исключения и дополнительные параметры.

### Быстрый старт

1. Распакуйте ZIP-архив с LWAI-DataBackup на рабочий стол или в другую папку, в которой ваша учётная запись Windows имеет права на запись.
2. Откройте распакованную папку и запустите LWAI-DataBackup.exe. LWAI-DataBackup работает в portable-режиме и не требует установки.
3. Укажите пути к исходным данным и папке, в которой будет сохранена резервная копия. Выберите обычную файловую копию или ZIP-архив, при необходимости настройте исключения и нажмите «Старт».

Для первого запуска рекомендуется использовать рабочий стол или другую пользовательскую папку. Размещение в защищённой системной папке может ограничить сохранение профилей, настроек и технического журнала.

EXE не имеет цифровой подписи. При первом запуске Windows может показать стандартное предупреждение для загруженного файла.

### Профили и настройки

В отдельном профиле сохраняются пути к исходным данным и месту размещения резервной копии, формат результата, правила исключений и дополнительные параметры. Профили можно создавать, переименовывать, удалять и располагать в удобном порядке. Последний выбранный профиль восстанавливается при следующем запуске.

Профили и настройки LWAI-DataBackup хранятся в config.json рядом с EXE. В этом файле также сохраняются тема, язык, режим автосохранения, отображение дополнительных параметров и положение окна. Входящий в дистрибутив config.json не содержит пользовательских путей или пользовательских профилей.

По умолчанию используется ручное сохранение командой «Сохранить профиль». При необходимости в окне «Настройки» можно включить автосохранение. Изменения текста записываются после выхода из поля либо через 5 секунд после последнего ввода; переключатели и параметры сохраняются сразу после выбора.

### Совместимость конфигурации

Конфигурация версии 1.5.0 совместима с версией 1.6.0. Чтобы перенести её, скопируйте data-backups.config.json из portable-папки версии 1.5.0 в portable-папку версии 1.6.0 и переименуйте копию в config.json.

### Резервное копирование

Доступны следующие возможности:

- создание обычной файловой копии или ZIP-архива;
- отдельные списки исключаемых папок, файлов и wildcard-масок для каждого профиля;
- отдельное управление включением папок backup и backups;
- предварительный подсчёт файлов и объёма с отображением прогресса, текущего этапа и журнала операции;
- предупреждение о слишком длинных путях до создания результата;
- отмена операции либо продолжение без объектов, перечисленных в предупреждении;
- отдельный итог для полностью завершённой операции и операции с пропусками;
- контроль уникальности имени результата с автоматическим добавлением безопасного суффикса при совпадении.

### Сохранность исходных данных

LWAI-DataBackup использует исходные данные исключительно в режиме чтения.

Доступность исходных данных и папки для резервной копии проверяется только для выбранного профиля после нажатия «Старт». Ожидание ответа сетевого пути не блокирует интерфейс.

Результат сначала создаётся под временным именем и получает окончательное имя только после успешной проверки. При штатной отмене незавершённый временный результат удаляется. Аварийное завершение процесса, Windows или питания может оставить временный объект только в папке резервной копии. Такой объект не продолжается автоматически, поэтому операцию следует запустить заново.

### Технический журнал

Фиксация событий в техническом журнале по умолчанию отключена. Её можно включить в дополнительных параметрах профиля. Записи сохраняются в папке logs рядом с EXE и могут содержать пути и имена файлов. Содержимое резервируемых файлов в журнал не записывается.

### Системные требования

Для корректной работы требуются:

- Windows 8.1 x64 – проверено;
- Windows 10 x64 – проверено;
- Windows 11 x64 – совместимость предусмотрена на уровне реализации, практическое тестирование не выполнялось;
- Microsoft .NET Framework – системная платформа Windows.

Microsoft .NET Framework входит в состав Windows. LWAI-DataBackup проверен с .NET Framework 4.8 в Windows 8.1 и с .NET Framework 4.8.1 в Windows 10.

В Windows 11 совместимая версия .NET Framework установлена по умолчанию. Отдельная установка обычно не требуется.

Если Windows 8.1 или Windows 10 сообщает, что для запуска отсутствует необходимая версия .NET Framework, откройте официальную страницу Microsoft по ссылке ниже. Выберите «Download .NET Framework 4.8 Runtime», скачайте установщик, запустите его и завершите установку по инструкциям Microsoft:
https://dotnet.microsoft.com/en-us/download/dotnet-framework/net48

### Доступ к папкам

Для выполнения резервного копирования и сохранения настроек необходимы:

- доступ на чтение к исходным данным;
- доступ на запись к папке, в которой будет сохранена резервная копия;
- право записи в папку с LWAI-DataBackup.exe; без него сохранение профилей, настроек и технического журнала невозможно.

### Локальная работа и приватность

Обработка данных выполняется локально. Телеметрия, внешний API, облачная синхронизация, серверная проверка лицензии и внешний сбор отчётов об ошибках в приложении отсутствуют. Сетевые пути используются только при прямом выборе пользователя и в пределах файловых разрешений Windows.

### Лицензия и поддержка

LWAI-DataBackup можно бесплатно использовать в личных, профессиональных и коммерческих целях. Распространение дистрибутива, перепродажа, передача третьим лицам, модификация, ребрендинг и замена логотипов запрещены. Полные условия использования приведены в LICENSE.txt.

Сведения о приватности, безопасности и поддержке находятся в PRIVACY.txt, SECURITY.txt и SUPPORT.txt. Сторонние компоненты и их лицензии перечислены в THIRD_PARTY_NOTICES.txt и THIRD_PARTY_LICENSES.txt.

Правообладатель: Life with AI
Сайт: https://life-with-ai.ru
Репозиторий: https://github.com/life-with-ai/LWAI-DataBackup

## English

### Purpose

Backup of projects and working documents as a regular file copy or ZIP archive. A separate profile can be created for each project or workflow to retain paths to source data and the backup location, result format, exclusions, and additional options.

### Quick start

1. Extract the ZIP archive containing LWAI-DataBackup to the desktop or another folder where your Windows account has write access.
2. Open the extracted folder and run LWAI-DataBackup.exe. LWAI-DataBackup runs in portable mode and requires no installation.
3. Specify the paths to the source data and the folder where the backup will be stored. Select a regular file copy or ZIP archive, configure exclusions if needed, and select "Start".

For the first launch, use the desktop or another user folder. Placing the files in a protected system folder may prevent profiles, settings, and the technical log from being saved.

The EXE is not digitally signed. Windows may display its standard warning for a downloaded file on first launch.

### Profiles and settings

A profile stores paths to source data and the backup location, result format, exclusion rules, and additional options. Profiles can be created, renamed, deleted, and arranged in a convenient order. The last selected profile is restored on the next launch.

LWAI-DataBackup profiles and settings are stored in config.json next to the EXE. This file also stores the theme, language, autosave mode, visibility of additional options, and window position. The config.json supplied in the package contains no user paths or user-created profiles.

Manual saving with "Save profile" is used by default. Autosave can be enabled in "Settings" when needed. Text changes are written after focus leaves a field or 5 seconds after the last input; switches and options are saved immediately after selection.

### Configuration compatibility

The version 1.5.0 configuration is compatible with version 1.6.0. To transfer it, copy data-backups.config.json from the version 1.5.0 portable folder to the version 1.6.0 portable folder and rename the copy to config.json.

### Backup

The following capabilities are available:

- creation of a regular file copy or ZIP archive;
- separate lists of excluded directories, files, and wildcard patterns for each profile;
- separate control over inclusion of the backup and backups directories;
- preliminary file and size calculation with operation progress, current stage, and log;
- warning about excessively long paths before a result is created;
- cancellation of the operation or continuation without the objects listed in the warning;
- distinct results for a fully completed operation and an operation completed with skipped objects;
- result name uniqueness control with an automatically added safe suffix on collision.

### Source data protection

LWAI-DataBackup uses source data exclusively in read-only mode.

Source data and backup folder availability is checked only for the selected profile after "Start". Waiting for a network path does not block the interface.

The result is first created under a temporary name and receives its final name only after successful verification. A normal cancellation removes the unfinished temporary result. An unexpected process, Windows, or power failure may leave a temporary object only in the backup folder. It is not resumed automatically, so start the operation again.

### Technical log

Recording events in the technical log is disabled by default. It can be enabled in the additional profile options. Records are stored in the logs folder next to the EXE and may contain paths and file names. The contents of backed-up files are not written to the log.

### System requirements

The following are required for correct operation:

- Windows 8.1 x64 – tested;
- Windows 10 x64 – tested;
- Windows 11 x64 – compatibility is addressed at the implementation level, practical testing has not been performed;
- Microsoft .NET Framework – the Windows runtime platform required to launch LWAI-DataBackup.

Microsoft .NET Framework is included with Windows. LWAI-DataBackup has been tested with .NET Framework 4.8 on Windows 8.1 and with .NET Framework 4.8.1 on Windows 10.

A compatible version of .NET Framework is included with Windows 11 by default. A separate installation is not normally required.

If Windows 8.1 or Windows 10 reports that the required version of .NET Framework is missing, open the official Microsoft page using the link below. Select "Download .NET Framework 4.8 Runtime", download and run the installer, and complete the installation by following Microsoft's instructions:
https://dotnet.microsoft.com/en-us/download/dotnet-framework/net48

### Folder access

The following access is required to create backups and save settings:

- read access to the source data;
- write access to the folder where the backup will be stored;
- write access to the folder containing LWAI-DataBackup.exe; without it, profiles, settings, and the technical log cannot be saved.

### Local operation and privacy

Data is processed locally. There is no telemetry, external API, cloud synchronization, server-side license check, or external collection of error reports. Network paths are used only when selected directly by the user and only within Windows file permissions.

### License and support

LWAI-DataBackup may be used free of charge for personal, professional, and commercial purposes. Distribution of the package, resale, transfer to third parties, modification, rebranding, and logo replacement are prohibited. Full terms of use are provided in LICENSE.txt.

Privacy, security, and support information is provided in PRIVACY.txt, SECURITY.txt, and SUPPORT.txt. Third-party components and licenses are listed in THIRD_PARTY_NOTICES.txt and THIRD_PARTY_LICENSES.txt.

Copyright holder: Life with AI
Website: https://life-with-ai.ru
Repository: https://github.com/life-with-ai/LWAI-DataBackup
