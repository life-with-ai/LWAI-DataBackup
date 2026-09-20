# DataBackup – Life with AI 1.5.0

[Русский](#русский) | [English](#english)

## Русский

`LWAI-DataBackup` – локальное portable Windows-приложение для копирования или ZIP-архивации выбранной папки с управляемыми исключениями, профилями заданий и проверкой результата.

### Скачать и запустить

- Portable ZIP: `LWAI-DataBackup-1.5.0-windows-x64-portable.zip`.
- Контрольная сумма публикуется в [release-information/v1.5.0.md](release-information/v1.5.0.md).
- Распакуйте ZIP в отдельную папку и запустите `LWAI-DataBackup.exe`. Установка не требуется.
- EXE не имеет цифровой подписи. Windows может показать стандартное предупреждение для загруженного приложения.

Профили и глобальные настройки хранятся в `data-backups.config.json` рядом с EXE. Файл из дистрибутива не содержит пользовательских путей или пользовательских профилей.

### Профили и глобальные настройки

- Каждый профиль хранит источник, назначение, режим copy или ZIP, исключения и дополнительные опции.
- Профиль можно создать пустым либо на основе сохранённых настроек существующего профиля, выбрать, переименовать, удалить и переместить в списке.
- Последний выбранный профиль восстанавливается при следующем запуске.
- Команда `Сохранить профиль` записывает активный профиль вручную.
- Дополнительное автосохранение записывает текст после потери фокуса либо через 5 секунд после последнего изменения, а режим и опции – после выбора.
- Окно `Настройки` управляет темой, языком, автосохранением и отображением дополнительных параметров.
- Светлая и тёмная темы применяются ко всем проектным поверхностям.
- Русский и английский интерфейс переключается сразу; пользовательские пути и имена профилей не переводятся.

### Резервное копирование

- копирование выбранной папки в отдельный каталог;
- создание ZIP-архива;
- исключение папок и файлов по wildcard-маскам до обхода исключённого содержимого;
- отдельное управление включением папок `backup` и `backups`;
- предварительный подсчёт файлов и объёма, прогресс, текущий этап и структурированный журнал;
- предупреждение о путях, превышающих стандартный предел Windows, до создания результата;
- отмена операции либо явное продолжение без перечисленных объектов;
- отдельный итог с пропусками и количеством пропущенных файлов и каталогов;
- временный результат `.tmp` и готовое имя только после успешной проверки.

### Системные требования

- 64-разрядная Windows с совместимым установленным .NET Framework;
- права чтения для источника и записи для назначения и portable-папки;
- исходный и целевой пути в пределах стандартных ограничений используемой версии Windows.

Фактически проверенная матрица систем указывается в [release-information/v1.5.0.md](release-information/v1.5.0.md).

### Защита исходных данных

Приложение использует источник только для чтения и не создаёт, не изменяет, не перемещает и не удаляет в нём объекты. Source и destination не могут совпадать, destination не может находиться внутри source, а опасные reparse-компоненты и перезапись существующего результата блокируются до записи.

Во время операции приложение повторно проверяет прочитанные данные. Изменение, исчезновение, блокировка или неполное чтение обязательного файла прекращает задание без готового результата.

### Приватность, поддержка и лицензия

Приложение работает локально без телеметрии, внешнего API, облачной синхронизации, серверной проверки лицензии и внешнего crash-reporting.

Подробности: [PRIVACY.md](PRIVACY.md), [SECURITY.md](SECURITY.md), [SUPPORT.md](SUPPORT.md), [LICENSE](LICENSE) и [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

## English

`LWAI-DataBackup` is a local portable Windows application for copying a selected folder or creating a ZIP archive with configurable exclusions, task profiles, and result verification.

### Download and run

- Portable ZIP: `LWAI-DataBackup-1.5.0-windows-x64-portable.zip`.
- The checksum is published in [release-information/v1.5.0.md](release-information/v1.5.0.md).
- Extract the ZIP to a separate folder and run `LWAI-DataBackup.exe`. No installation is required.
- The EXE is not digitally signed. Windows may display its standard warning for a downloaded application.

Profiles and global settings are stored in `data-backups.config.json` next to the EXE. The distributed file contains no user paths or user profiles.

### Profiles and global settings

- Each profile stores the source, destination, copy or ZIP mode, exclusions, and additional options.
- A profile can be created empty or from the saved settings of an existing profile, selected, renamed, deleted, and reordered.
- The last selected profile is restored the next time the application starts.
- The `Save profile` command writes the active profile manually.
- Optional autosave writes text after focus leaves a field or 5 seconds after the last edit, while mode and options are saved after selection.
- The `Settings` dialog controls theme, language, autosave, and the visibility of additional options.
- Light and dark themes apply to all project-owned surfaces.
- The Russian and English interfaces switch immediately; user paths and profile names are not translated.

### Backup features

- copy a selected folder into a separate directory;
- create a ZIP archive;
- exclude directories and files with wildcard patterns before excluded content is traversed;
- control inclusion of the `backup` and `backups` directories separately;
- calculate file count and size in advance and show progress, current stage, and a structured log;
- warn about paths that exceed the standard Windows limit before creating a result;
- cancel the operation or explicitly continue without the listed objects;
- report a distinct completed-with-skips result with skipped file and directory counts;
- keep an incomplete result as `.tmp` and publish the final name only after successful verification.

### System requirements

- 64-bit Windows with a compatible installed .NET Framework;
- read access to the source and write access to the destination and portable folder;
- source and destination paths within the standard limits of the Windows version in use.

The verified operating system matrix is provided in [release-information/v1.5.0.md](release-information/v1.5.0.md).

### Source data protection

The application uses the source for reading only and does not create, modify, move, or delete objects in it. Source and destination cannot be the same, destination cannot be inside source, and unsafe reparse components and overwriting an existing result are blocked before writing.

During an operation, the application verifies the data it reads again. A required file that changes, disappears, becomes locked, or cannot be read completely ends the task without publishing a completed result.

### Privacy, support, and license

The application works locally without telemetry, an external API, cloud synchronization, server-side license checks, or external crash reporting.

See [PRIVACY.md](PRIVACY.md), [SECURITY.md](SECURITY.md), [SUPPORT.md](SUPPORT.md), [LICENSE](LICENSE), and [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

Life with AI – [life-with-ai.ru](https://life-with-ai.ru)
