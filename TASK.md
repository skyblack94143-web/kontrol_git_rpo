# Контрольная работа: Git, GitHub и VS Code

## Формат результата

GitHub-репозиторий студента + оформленный `README.md` со скриншотами.

## Цель работы

Закрепить полный практический цикл работы с Git и GitHub через графический интерфейс VS Code:

- вход в GitHub-аккаунт через VS Code;
- клонирование репозитория из GitHub;
- создание или проверка локального Git-репозитория;
- добавление файлов в Stage через Source Control;
- создание осмысленных коммитов через поле `Message` и кнопку `Commit`;
- публикация проекта на GitHub через `Publish Branch`;
- отправка изменений через `Push` / `Sync Changes`;
- проверка удалённых изменений через `Fetch`;
- получение удалённых изменений через `Pull`;
- понимание разницы между `Fetch` и `Pull`;
- работа с Git Graph;
- создание и переключение веток;
- merge ветки в `main`;
- базовое разрешение конфликта в VS Code;
- настройка `.gitignore`;
- оформление `README.md` в Markdown;
- добавление скриншотов в `README.md`.

## Главное правило

Основные Git-действия выполняются через графический интерфейс VS Code:

- Source Control;
- кнопка `+` для Stage;
- поле `Message`;
- кнопка `Commit`;
- `Publish Branch`;
- `Push`;
- `Sync Changes`;
- `Fetch`;
- `Pull`;
- создание и переключение веток;
- `Merge`;
- Git Graph.

Команды Git в этом задании приведены как справка и для понимания того, что происходит внутри Git. Если преподаватель требует работу именно через интерфейс VS Code, не заменяйте её выполнением команд в терминале.

Терминал можно использовать для запуска программы:

```bash
python main.py
```

или:

```bash
python3 main.py
```

## Что нужно сдать

Студент сдаёт:

1. Ссылку на свой GitHub-репозиторий.
2. Оформленный `README.md` с отчётом.
3. Папку `assets/screenshots/` со скриншотами.
4. Историю коммитов, где видно последовательное выполнение работы.
5. Корректный `.gitignore`, который исключает `.env`, логи и временные папки.

## Итоговая структура проекта

В конце работы репозиторий должен иметь такую структуру:

```text
git_practice_Фамилия_Группа/
├── main.py
├── README.md
├── .gitignore
├── assets/
│   └── screenshots/
│       ├── 01_git_init.png
│       ├── 02_first_commit.png
│       ├── 03_gitignore_check.png
│       ├── 04_github_repository.png
│       ├── 05_branch_created.png
│       ├── 06_merge_result.png
│       ├── 07_fetch_status.png
│       ├── 08_pull_conflict.png
│       ├── 09_conflict_resolved.png
│       └── 10_commit_history.png
└── docs/
    └── notes.md
```

Файлы `.env` и `temp.log` нужно создать для проверки `.gitignore`, но они не должны попасть в GitHub.

## Часть 1. Получение проекта

### Вариант A. Если преподаватель дал ссылку на шаблон

1. Откройте VS Code.
2. Откройте Command Palette:
   - Windows / Linux: `Ctrl + Shift + P`;
   - macOS: `Cmd + Shift + P`.
3. Найдите команду `Git: Clone`.
4. Вставьте ссылку на репозиторий-шаблон.
5. Выберите папку на компьютере.
6. После клонирования нажмите `Open`.

Эквивалент команды:

```bash
git clone ссылка_на_репозиторий
```

### Вариант B. Если проект нужно создать с нуля

1. Создайте папку проекта.
2. Назовите её по шаблону:

```text
git_practice_Фамилия_Группа
```

Пример:

```text
git_practice_ivanov_isp_21
```

3. Откройте папку в VS Code через `File -> Open Folder`.
4. Откройте Source Control.
5. Нажмите `Initialize Repository`.

Эквивалент команд:

```bash
git init
git branch -M main
git status
```

Сделайте скриншот и сохраните его:

```text
assets/screenshots/01_git_init.png
```

## Часть 2. Создание структуры проекта

Создайте файлы и папки:

```text
main.py
README.md
.gitignore
assets/screenshots/
docs/notes.md
```

Если папка `assets/screenshots/` пустая и не добавляется в Git, создайте внутри неё файл:

```text
assets/screenshots/.gitkeep
```

## Часть 3. Файл `main.py`

Откройте `main.py` и добавьте стартовый код.

Пример:

```python
def show_project_title():
    print("Git practice project started")


def show_student_info():
    student_name = "Фамилия Имя"
    group = "Название группы"
    print(f"Student: {student_name}")
    print(f"Group: {group}")


def show_git_topics():
    topics = [
        "README.md",
        ".gitignore",
        "commits",
        "branches",
        "merge",
        "fetch",
        "pull",
        "conflicts",
    ]

    print("Practice topics:")
    for topic in topics:
        print(f"- {topic}")


def main():
    show_project_title()
    show_student_info()
    show_git_topics()


if __name__ == "__main__":
    main()
```

Замените `Фамилия Имя` и `Название группы` на свои данные.

Проверьте запуск:

```bash
python main.py
```

или:

```bash
python3 main.py
```

## Часть 4. Файл `docs/notes.md`

Создайте файл:

```text
docs/notes.md
```

Добавьте в него текст:

```markdown
# Заметки по Git

Git помогает сохранять историю изменений проекта.

## Изученные действия

- git init
- git add
- git commit
- git push
- git branch
- git merge
- git fetch
- git pull
```

Если вы выполняете работу через интерфейс VS Code, команды в этом файле всё равно можно оставить как теоретическую памятку.

## Часть 5. Демонстрационные `.env` и `temp.log`

Создайте файл `.env`:

```env
DEMO_TOKEN=do_not_commit_this_token
DATABASE_URL=sqlite:///local.db
```

Создайте файл `temp.log`:

```text
[INFO] temporary log file
[DEBUG] this file must not be committed
```

Эти файлы нужны только для проверки `.gitignore`. Они не должны попасть в коммит и на GitHub.

Важно: не используйте реальные пароли, токены и ключи.

## Часть 6. Настройка `.gitignore`

Откройте `.gitignore` и добавьте:

```gitignore
# Virtual environments
venv/
.venv/

# Python cache
__pycache__/
*.pyc

# Environment variables and secrets
.env

# Logs
*.log

# Editor settings
.vscode/
.idea/

# System files
.DS_Store
Thumbs.db
```

Проверьте в Source Control:

- `.env` не должен отображаться как файл для коммита;
- `temp.log` не должен отображаться как файл для коммита;
- `main.py`, `README.md`, `.gitignore`, `docs/notes.md` должны отображаться как обычные изменения.

Эквивалент команд проверки:

```bash
git status
git status --ignored
```

Сделайте скриншот проверки `.gitignore`:

```text
assets/screenshots/03_gitignore_check.png
```

## Часть 7. Первый коммит

Первый коммит должен зафиксировать базовую структуру проекта.

Через VS Code:

1. Откройте Source Control.
2. Добавьте в Stage файлы:
   - `main.py`;
   - `README.md`;
   - `.gitignore`;
   - `docs/notes.md`;
   - `assets/screenshots/.gitkeep`, если он есть.
3. В поле `Message` напишите:

```text
base: create git practice project
```

4. Нажмите `Commit`.

Эквивалент команд:

```bash
git add main.py README.md .gitignore docs/notes.md assets/screenshots/.gitkeep
git commit -m "base: create git practice project"
```

Сделайте скриншот первого коммита:

```text
assets/screenshots/02_first_commit.png
```

## Часть 8. Публикация на GitHub

1. Войдите в GitHub-аккаунт через VS Code.
2. Откройте Source Control.
3. Нажмите `Publish Branch`.
4. Выберите GitHub.
5. Назовите репозиторий:

```text
git_practice_Фамилия_Группа
```

6. Выберите публичный или приватный режим по указанию преподавателя.
7. Дождитесь публикации.
8. Откройте репозиторий на GitHub.

Эквивалент команд:

```bash
git remote add origin ссылка_на_ваш_репозиторий
git push -u origin main
```

Сделайте скриншот GitHub-репозитория:

```text
assets/screenshots/04_github_repository.png
```

В отчёте обязательно укажите ссылку:

```text
Ссылка на GitHub: https://github.com/username/git_practice_Фамилия_Группа
```

## Часть 9. Оформление `README.md`

`README.md` должен быть не просто файлом задания, а отчётом о выполненной работе.

Обязательные разделы:

- название проекта;
- информация о студенте;
- цель работы;
- структура проекта;
- использованные Git-действия;
- таблица Git-действий и их смысла;
- описание работы с `.gitignore`;
- описание работы с веткой и merge;
- описание Fetch и Pull;
- описание конфликта и способа решения;
- скриншоты;
- вывод.

### Шаблон для отчёта

Можно использовать и заполнить этот шаблон:

````markdown
# Git Practice: Фамилия Имя

Учебный репозиторий для закрепления Git, GitHub, VS Code, README.md, .gitignore, веток, merge, fetch, pull и конфликтов.

## Информация о студенте

| Поле | Значение |
|---|---|
| ФИО | Фамилия Имя |
| Группа | Название группы |
| Дисциплина | Git и GitHub |
| Дата выполнения | ДД.ММ.ГГГГ |
| Ссылка на GitHub | https://github.com/username/repository |

## Цель работы

Закрепить полный цикл работы с Git и GitHub через VS Code.

## Структура проекта

```text
git_practice_Фамилия_Группа/
├── main.py
├── README.md
├── .gitignore
├── assets/
│   └── screenshots/
└── docs/
    └── notes.md
```

## Использованные Git-действия

- Clone Repository
- Initialize Repository
- Stage Changes
- Commit
- Publish Branch
- Push / Sync Changes
- Fetch
- Pull
- Create Branch
- Merge
- Resolve Conflict
- Git Graph

## Вывод

В ходе работы я закрепил(а) базовый цикл работы с Git и GitHub, научился(ась) оформлять README.md, настраивать .gitignore, работать с ветками, выполнять fetch/pull и разрешать конфликт изменений.
````

## Часть 10. Работа с отдельной веткой

Создайте отдельную ветку для изменения `README.md`.

Рекомендуемое имя ветки:

```text
feature/readme-update
```

Через VS Code:

1. Нажмите на название ветки в нижнем левом углу.
2. Выберите `Create new branch`.
3. Введите `feature/readme-update`.
4. Убедитесь, что VS Code переключился на новую ветку.

Эквивалент команды:

```bash
git switch -c feature/readme-update
```

Сделайте скриншот созданной ветки:

```text
assets/screenshots/05_branch_created.png
```

## Часть 11. Изменения в ветке

Находясь в ветке `feature/readme-update`, измените `README.md`.

Добавьте раздел:

```markdown
## Что я понял(а) про .gitignore

- `.gitignore` помогает не отправлять в GitHub временные и секретные файлы.
- Файл `.env` нельзя публиковать, потому что в нём могут быть токены и пароли.
- Логи `*.log` обычно не нужны в репозитории.
- Папки `venv/` и `.venv/` не добавляют в Git, потому что их можно создать заново.
- Перед коммитом нужно проверять Source Control.
```

Сделайте коммит в ветке.

Сообщение коммита:

```text
docs: update readme with gitignore notes
```

Эквивалент команд:

```bash
git add README.md
git commit -m "docs: update readme with gitignore notes"
```

## Часть 12. Merge ветки в `main`

1. Переключитесь на ветку `main`.
2. Выполните merge ветки `feature/readme-update` в `main`.
3. Проверьте, что новый раздел появился в `README.md`.
4. Отправьте изменения на GitHub через `Push` или `Sync Changes`.

Эквивалент команд:

```bash
git switch main
git merge feature/readme-update
git push
```

Сделайте скриншот результата merge или графа коммитов:

```text
assets/screenshots/06_merge_result.png
```

## Часть 13. Fetch, Pull и конфликт

В этой части нужно специально создать ситуацию, где GitHub и локальный проект изменили одну и ту же строку `README.md`.

### Шаг 1. Добавьте строку статуса локально

В верхней части `README.md` добавьте строку:

```text
Статус проекта: локальная версия до конфликта
```

Сделайте коммит и отправьте на GitHub.

Сообщение коммита:

```text
docs: add project status
```

### Шаг 2. Измените эту же строку через GitHub

1. Откройте `README.md` на GitHub.
2. Нажмите кнопку редактирования файла.
3. Измените строку статуса:

```text
Статус проекта: версия изменена через GitHub
```

4. Сделайте commit прямо на GitHub.

### Шаг 3. Локально измените эту же строку иначе

В VS Code измените эту же строку:

```text
Статус проекта: локальная версия изменена в VS Code
```

Сделайте локальный коммит:

```text
docs: update status locally
```

### Шаг 4. Выполните Fetch

В VS Code выполните `Fetch`.

После Fetch Git должен показать, что в удалённом репозитории есть изменения. Локальный файл при этом ещё не должен автоматически измениться.

Эквивалент команд:

```bash
git fetch
git status
```

Сделайте скриншот:

```text
assets/screenshots/07_fetch_status.png
```

### Шаг 5. Выполните Pull

В VS Code выполните `Pull`.

Так как одна и та же строка была изменена в двух местах, должен появиться конфликт.

В `README.md` могут появиться маркеры:

```text
<<<<<<< HEAD
Статус проекта: локальная версия изменена в VS Code
=======
Статус проекта: версия изменена через GitHub
>>>>>>> origin/main
```

Эквивалент команды:

```bash
git pull --no-rebase
```

Сделайте скриншот конфликта:

```text
assets/screenshots/08_pull_conflict.png
```

### Шаг 6. Разрешите конфликт

В VS Code выберите нужный вариант через кнопки:

- `Accept Current Change`;
- `Accept Incoming Change`;
- `Accept Both Changes`;
- ручное редактирование.

Итоговая строка может быть такой:

```text
Статус проекта: итоговая версия после разрешения конфликта
```

После исправления:

1. Удалите все служебные маркеры `<<<<<<<`, `=======`, `>>>>>>>`.
2. Сохраните файл.
3. Добавьте исправленный `README.md` в Stage.
4. Сделайте коммит:

```text
fix: resolve pull conflict in readme
```

5. Отправьте изменения на GitHub.

Сделайте скриншот исправленного файла:

```text
assets/screenshots/09_conflict_resolved.png
```

## Часть 14. Скриншоты

Все скриншоты должны лежать в папке:

```text
assets/screenshots/
```

Обязательные скриншоты:

| Файл | Что должно быть на скриншоте |
|---|---|
| `01_git_init.png` | Инициализация репозитория или открытый склонированный проект в VS Code |
| `02_first_commit.png` | Первый коммит в Source Control, Git Graph или истории |
| `03_gitignore_check.png` | Проверка, что `.env` и `*.log` не попадают в коммит |
| `04_github_repository.png` | Открытый репозиторий на GitHub после публикации |
| `05_branch_created.png` | Созданная ветка `feature/readme-update` |
| `06_merge_result.png` | Результат merge ветки в `main` |
| `07_fetch_status.png` | Выполнение Fetch или статус после Fetch |
| `08_pull_conflict.png` | Конфликт в `README.md` после Pull |
| `09_conflict_resolved.png` | Исправленный `README.md` без маркеров конфликта |
| `10_commit_history.png` | Финальная история коммитов в Git Graph или GitHub |

Названия файлов должны совпадать с таблицей. Если название отличается хотя бы на один символ, изображение может не отобразиться в `README.md`.

### Вставка скриншотов в README

Добавьте в `README.md` раздел:

```markdown
## Скриншоты выполнения работы

### 1. Инициализация репозитория

![01 - Инициализация репозитория](assets/screenshots/01_git_init.png)

### 2. Первый коммит

![02 - Первый коммит](assets/screenshots/02_first_commit.png)

### 3. Проверка .gitignore

![03 - Проверка gitignore](assets/screenshots/03_gitignore_check.png)

### 4. Репозиторий на GitHub

![04 - Репозиторий на GitHub](assets/screenshots/04_github_repository.png)

### 5. Создание ветки

![05 - Создание ветки](assets/screenshots/05_branch_created.png)

### 6. Merge ветки в main

![06 - Merge ветки](assets/screenshots/06_merge_result.png)

### 7. Git Fetch

![07 - Git Fetch](assets/screenshots/07_fetch_status.png)

### 8. Конфликт при Pull

![08 - Конфликт при Pull](assets/screenshots/08_pull_conflict.png)

### 9. Разрешение конфликта

![09 - Разрешение конфликта](assets/screenshots/09_conflict_resolved.png)

### 10. Финальная история коммитов

![10 - История коммитов](assets/screenshots/10_commit_history.png)
```

## Часть 15. Финальная история и последний коммит

Откройте Git Graph или историю коммитов на GitHub.

В истории должно быть не менее 8 осмысленных коммитов.

Сделайте финальный скриншот:

```text
assets/screenshots/10_commit_history.png
```

После добавления финального скриншота сделайте последний коммит:

```text
docs: add final commit history screenshot
```

Отправьте изменения на GitHub через `Push` или `Sync Changes`.

## Рекомендуемые названия коммитов

| Ситуация | Пример сообщения коммита |
|---|---|
| Создание базовой структуры проекта | `base: create git practice project` |
| Добавление структуры README | `docs: add readme structure` |
| Настройка `.gitignore` | `chore: configure gitignore` |
| Добавление заметок | `docs: add git notes` |
| Изменение README в ветке | `docs: update readme with gitignore notes` |
| Добавление статуса проекта | `docs: add project status` |
| Локальное изменение перед конфликтом | `docs: update status locally` |
| Разрешение конфликта | `fix: resolve pull conflict in readme` |
| Добавление скриншотов | `docs: add practice screenshots to readme` |
| Финальный скриншот истории | `docs: add final commit history screenshot` |

## Таблица Git-действий

Заполните эту таблицу в отчёте своими словами.

| Действие | Где выполнялось в VS Code | Смысл |
|---|---|---|
| Clone Repository | Command Palette | Копирует репозиторий с GitHub на компьютер |
| Initialize Repository | Source Control | Создаёт локальный Git-репозиторий |
| Stage Changes | Source Control | Подготавливает файлы к коммиту |
| Commit | Source Control | Сохраняет версию проекта в истории |
| Publish Branch | Source Control | Публикует проект или ветку на GitHub |
| Push | Source Control | Отправляет локальные коммиты на GitHub |
| Sync Changes | Source Control | Синхронизирует локальные и удалённые изменения |
| Fetch | Source Control | Проверяет изменения на GitHub без изменения локальных файлов |
| Pull | Source Control | Загружает и применяет изменения из GitHub |
| Create Branch | Нижняя панель VS Code или Git Graph | Создаёт отдельную ветку |
| Switch Branch | Нижняя панель VS Code или Git Graph | Переключает проект на другую ветку |
| Merge | Git Graph или Command Palette | Объединяет изменения из одной ветки с другой |
| Resolve Conflict | Редактор VS Code | Помогает выбрать или объединить конфликтующие изменения |
| Git Graph | Расширение Git Graph | Показывает историю коммитов и веток |

## Разница между Fetch и Pull

В отчёте обязательно объясните разницу.

Пример:

> Fetch проверяет и загружает информацию о новых коммитах из GitHub, но не меняет мои рабочие файлы. Pull загружает изменения и сразу применяет их к текущей ветке. Я проверил(а) это, когда изменил(а) `README.md` на GitHub, затем сделал(а) Fetch в VS Code, а после этого Pull.

## Конфликт и его решение

В отчёте обязательно опишите конфликт.

Пример:

> Я создал(а) конфликт в `README.md`: одна и та же строка статуса проекта была изменена на GitHub и локально в VS Code. После Pull в файле появились маркеры конфликта. Я выбрал(а) итоговый вариант строки, удалил(а) служебные маркеры, добавил(а) файл в Stage, сделал(а) коммит решения конфликта и отправил(а) изменения на GitHub.

## Финальная проверка перед сдачей

| Проверка | Да/нет |
|---|---|
| Репозиторий опубликован на GitHub | |
| Ссылка на GitHub добавлена в README | |
| README.md открывается на GitHub и выглядит аккуратно | |
| Все скриншоты отображаются в README.md | |
| `.gitignore` есть в репозитории | |
| `.env` не попал в GitHub | |
| `temp.log` не попал в GitHub | |
| Есть папка `docs/` и файл `docs/notes.md` | |
| Есть отдельная ветка `feature/readme-update` | |
| Ветка была слита в `main` через merge | |
| Выполнен Fetch | |
| Выполнен Pull | |
| Конфликт создан и разрешён или подробно описан | |
| В истории есть не менее 8 осмысленных коммитов | |
| Есть финальный вывод по работе | |

## Критерии оценивания

| Критерий | Баллы |
|---|---:|
| Репозиторий создан, опубликован, ссылка доступна | 10 |
| Корректная структура проекта | 10 |
| Правильно настроен `.gitignore`, секретные и временные файлы не попали в GitHub | 15 |
| `README.md` оформлен через Markdown и содержит все обязательные разделы | 15 |
| Все обязательные скриншоты вставлены и отображаются в `README.md` | 20 |
| Есть работа с веткой и merge в `main` | 10 |
| Показаны Fetch, Pull и разрешение конфликта | 15 |
| История коммитов осмысленная, не менее 8 коммитов | 5 |
| **Итого** | **100** |

Работа считается выполненной только при наличии ссылки на GitHub-репозиторий и отображающихся скриншотов в `README.md`.

## Короткая памятка по командам

Эта памятка нужна для понимания Git. Основная работа выполняется через VS Code.

```bash
git status                    # проверить состояние проекта
git add .                     # добавить изменения в staged
git commit -m "message"       # создать коммит
git push                      # отправить изменения на GitHub
git switch -c branch-name     # создать и перейти на ветку
git switch main               # перейти на main
git merge branch-name         # слить ветку в текущую ветку
git fetch                     # проверить изменения на GitHub без изменения файлов
git pull --no-rebase          # забрать изменения с GitHub через merge
git log --oneline --graph     # посмотреть историю коммитов
```
