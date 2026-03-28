# SE Toolkit — Question Bank Answers

## Git & Workflow

### Q1. Describe the Git workflow we followed during the labs from start to finish. Explain what happens at each stage.

**English:**
The Git workflow we followed is based on GitHub Flow:

1. **Create a Lab Task issue** — Create an issue using the Lab Task issue form to describe what you'll work on.
2. **Switch to the main branch** — Ensure you're on the `main` branch.
3. **Pull changes from origin** — Get the latest changes from your remote repository.
4. **Pull changes from upstream** — Get the latest changes from the instructors' repository.
5. **Create a task branch** — Create a new branch from `main` for your specific task.
6. **Edit files** — Make your changes in VS Code.
7. **Commit changes** — Commit with conventional commit messages (e.g., `feat:`, `fix:`, `docs:`).
8. **Push commits** — Publish the branch and push your commits.
9. **Create a PR** — Create a pull request from your task branch to `main` in your fork.
10. **Get a PR review** — Request review, address comments, get approval.
11. **Merge the PR** — Merge the pull request into `main`.
12. **Clean up** — Close the issue and delete the task branch.

**Русский:**
Git-воркфлоу, который мы использовали, основан на GitHub Flow:

1. **Создать issue для задачи** — Создать issue, используя форму Lab Task, чтобы описать, над чем вы будете работать.
2. **Переключиться на ветку main** — Убедиться, что вы находитесь в ветке `main`.
3. **Загрузить изменения из origin** — Получить последние изменения из вашего удалённого репозитория.
4. **Загрузить изменения из upstream** — Получить последние изменения из репозитория преподавателей.
5. **Создать ветку задачи** — Создать новую ветку из `main` для вашей конкретной задачи.
6. **Редактировать файлы** — Внести изменения в VS Code.
7. **Закоммитить изменения** — Сделать коммит с использованием conventional commit сообщений (например, `feat:`, `fix:`, `docs:`).
8. **Запушить коммиты** — Опубликовать ветку и отправить коммиты.
9. **Создать PR** — Создать pull request из вашей ветки задачи в `main` в вашем форке.
10. **Получить ревью PR** — Запросить ревью, исправить замечания, получить одобрение.
11. **Слить PR** — Влить pull request в `main`.
12. **Очистка** — Закрыть issue и удалить ветку задачи.

---

### Q2. You and a teammate both edited the same line in README.md on separate branches. What will this lead to? Describe step-by-step how you resolve it.

**English:**
This will lead to a **merge conflict** when one of you tries to merge your branch into `main` after the other has already merged theirs. Git cannot automatically decide which version to keep.

**Resolution steps:**
1. **Pull the latest changes** from `main` to your branch: `git pull origin main`
2. **Git will mark the conflict** in README.md with conflict markers:
   ```
   <<<<<<< HEAD
   Your version of the line
   =======
   Teammate's version of the line
   >>>>>>> main
   ```
3. **Open the file in VS Code** — it will highlight the conflict.
4. **Choose which version to keep** (or combine both versions meaningfully).
5. **Remove all conflict markers** (`<<<<<<<`, `=======`, `>>>>>>>`).
6. **Save the file** and stage the changes: `git add README.md`
7. **Commit the merge resolution**: `git commit -m "fix: resolve merge conflict in README.md"`
8. **Push your changes**: `git push origin <your-branch>`

**Русский:**
Это приведёт к **конфликту слияния**, когда один из вас попытается влить свою ветку в `main` после того, как другой уже влил свою. Git не может автоматически решить, какую версию оставить.

**Шаги разрешения:**
1. **Загрузить последние изменения** из `main` в вашу ветку: `git pull origin main`
2. **Git пометит конфликт** в README.md маркерами конфликта:
   ```
   <<<<<<< HEAD
   Ваша версия строки
   =======
   Версия строки товарища по команде
   >>>>>>> main
   ```
3. **Открыть файл в VS Code** — он подсветит конфликт.
4. **Выбрать, какую версию оставить** (или осмысленно объединить обе версии).
5. **Удалить все маркеры конфликта** (`<<<<<<<`, `=======`, `>>>>>>>`).
6. **Сохранить файл** и добавить изменения в staging: `git add README.md`
7. **Закоммитить разрешение слияния**: `git commit -m "fix: resolve merge conflict in README.md"`
8. **Запушить изменения**: `git push origin <your-branch>`

---

### Q3. What is a conventional commit message? Give an example of a correct conventional commit for a bug fix to the /items endpoint.

**English:**
A **conventional commit message** follows the Conventional Commits specification, which provides a standardized format for commit messages. The format is:

```
<type>: <description>

[optional body]
```

Common types:
- `feat:` — new functionality
- `fix:` — bug fixes
- `docs:` — documentation changes
- `refactor:` — code changes without behavior changes

**Example for a bug fix to /items endpoint:**
```
fix: handle null values in /items endpoint response
```

**Русский:**
**Conventional commit сообщение** следует спецификации Conventional Commits, которая предоставляет стандартизированный формат для сообщений коммитов. Формат:

```
<тип>: <описание>

[необязательное тело]
```

Общие типы:
- `feat:` — новый функционал
- `fix:` — исправления ошибок
- `docs:` — изменения документации
- `refactor:` — изменения кода без изменения поведения

**Пример для исправления ошибки в эндпоинте /items:**
```
fix: handle null values in /items endpoint response
```

---

## HTTP & REST API

### Q4. Describe the main parts of an HTTP request and an HTTP response.

**English:**
**HTTP Request parts:**
1. **Request line** — contains the HTTP method (GET, POST, PUT, DELETE), the path/URL, and HTTP version
2. **Headers** — key-value pairs providing metadata (e.g., `Content-Type`, `Authorization`, `Accept`)
3. **Body/Payload** (optional) — data sent with the request (used in POST, PUT requests)

**HTTP Response parts:**
1. **Status line** — contains HTTP version, status code, and status message (e.g., `HTTP/1.1 200 OK`)
2. **Headers** — metadata about the response (e.g., `Content-Type`, `Content-Length`)
3. **Body** — the actual response content (HTML, JSON, etc.)

**Русский:**
**Части HTTP запроса:**
1. **Строка запроса** — содержит HTTP метод (GET, POST, PUT, DELETE), путь/URL и версию HTTP
2. **Заголовки** — пары ключ-значение, предоставляющие метаданные (например, `Content-Type`, `Authorization`, `Accept`)
3. **Тело/Payload** (опционально) — данные, отправляемые с запросом (используется в POST, PUT запросах)

**Части HTTP ответа:**
1. **Строка статуса** — содержит версию HTTP, код статуса и сообщение (например, `HTTP/1.1 200 OK`)
2. **Заголовки** — метаданные об ответе (например, `Content-Type`, `Content-Length`)
3. **Тело** — фактическое содержимое ответа (HTML, JSON и т.д.)

---

### Q5. A client calls an API and receives HTTP 200, 401, 403, 404, 500, 502. Explain what each status code usually means, and what kind of problem (if any) you would suspect first in each case.

**English:**
| Status Code | Meaning | First Suspected Problem |
|-------------|---------|------------------------|
| **200 OK** | Request succeeded | No problem — success |
| **401 Unauthorized** | Authentication required or invalid credentials | Missing/invalid API key in `Authorization` header |
| **403 Forbidden** | Authenticated but no permission | User lacks permission for this resource |
| **404 Not Found** | Resource doesn't exist | Wrong URL/path or resource was deleted |
| **500 Internal Server Error** | Unexpected server error | Bug in server code, unhandled exception |
| **502 Bad Gateway** | Invalid response from upstream server | Backend service is down or misconfigured proxy |

**Русский:**
| Код статуса | Значение | Первая предполагаемая проблема |
|-------------|---------|-------------------------------|
| **200 OK** | Запрос успешен | Нет проблемы — успех |
| **401 Unauthorized** | Требуется аутентификация или неверные учётные данные | Отсутствует/неверный API ключ в заголовке `Authorization` |
| **403 Forbidden** | Аутентифицирован, но нет разрешения | У пользователя нет разрешения на этот ресурс |
| **404 Not Found** | Ресурс не существует | Неверный URL/путь или ресурс был удалён |
| **500 Internal Server Error** | Неожиданная ошибка сервера | Ошибка в коде сервера, необработанное исключение |
| **502 Bad Gateway** | Неверный ответ от вышестоящего сервера | Backend-сервис не работает или неверно настроен прокси |

---

### Q6. You open Swagger UI for an unfamiliar API. What specific information can you extract from it about a specific endpoint?

**English:**
From Swagger UI for a specific endpoint, you can extract:

1. **HTTP method** — GET, POST, PUT, DELETE, etc.
2. **Path/URL** — the endpoint path (e.g., `/items/{id}`)
3. **Description** — what the endpoint does
4. **Parameters** — path parameters, query parameters, their types and whether they're required
5. **Request body schema** — the expected JSON structure for POST/PUT requests
6. **Response schemas** — the structure of successful and error responses
7. **Status codes** — possible response codes (200, 201, 400, 401, 404, etc.)
8. **Authentication requirements** — whether API key or other auth is needed
9. **Example values** — sample requests and responses
10. **Try it out** — ability to test the endpoint directly from the UI

**Русский:**
Из Swagger UI для конкретного эндпоинта можно извлечь:

1. **HTTP метод** — GET, POST, PUT, DELETE и т.д.
2. **Путь/URL** — путь эндпоинта (например, `/items/{id}`)
3. **Описание** — что делает эндпоинт
4. **Параметры** — параметры пути, параметры запроса, их типы и обязательность
5. **Схема тела запроса** — ожидаемая JSON структура для POST/PUT запросов
6. **Схемы ответов** — структура успешных и ошибочных ответов
7. **Коды статуса** — возможные коды ответов (200, 201, 400, 401, 404 и т.д.)
8. **Требования аутентификации** — требуется ли API ключ или другая аутентификация
9. **Примеры значений** — образцы запросов и ответов
10. **Try it out** — возможность протестировать эндпоинт прямо из UI

---

### Q7. What is the relationship between a database schema, a model object, and business logic?

**English:**
**Database schema** — Defines the structure of the database: tables, columns, data types, constraints, and relationships between tables. It's the blueprint of how data is stored.

**Model object** — A code representation (class/structure) of a database table row. Models map database rows to objects in your programming language. For example, a `Learner` model represents a row in the `learners` table.

**Business logic** — The rules and operations that govern how the application works. Business logic uses model objects to read, create, update, and delete data according to application rules.

**Relationship:**
- The **schema** defines how data is physically stored in the database
- **Models** provide an in-memory representation of that data in code
- **Business logic** operates on models to implement application behavior

Example: The `items` table (schema) → `Item` class (model) → `get_item_by_id()` function (business logic)

**Русский:**
**Схема базы данных** — Определяет структуру базы данных: таблицы, столбцы, типы данных, ограничения и связи между таблицами. Это чертёж того, как хранятся данные.

**Объект модели** — Кодовое представление (класс/структура) строки таблицы базы данных. Модели отображают строки базы данных на объекты в вашем языке программирования. Например, модель `Learner` представляет строку в таблице `learners`.

**Бизнес-логика** — Правила и операции, определяющие работу приложения. Бизнес-логика использует объекты моделей для чтения, создания, обновления и удаления данных согласно правилам приложения.

**Связь:**
- **Схема** определяет, как данные физически хранятся в базе данных
- **Модели** предоставляют представление этих данных в памяти в коде
- **Бизнес-логика** работает с моделями для реализации поведения приложения

Пример: Таблица `items` (схема) → класс `Item` (модель) → функция `get_item_by_id()` (бизнес-логика)

---

## Security & Authentication

### Q8. Compare API-key authentication and username/password authentication. How does each work, what is each commonly used for, and what are the main tradeoffs?

**English:**
| Aspect | API-key Authentication | Username/Password Authentication |
|--------|----------------------|----------------------------------|
| **How it works** | Client sends a secret key in `Authorization: Bearer <key>` header | Client sends username and password (usually in login endpoint) |
| **Commonly used for** | Service-to-service communication, simple APIs, development environments | User-facing applications, systems with multiple users and roles |
| **Tradeoffs — API-key** | ✅ Simple to implement and use<br>❌ Shared secret (no user differentiation)<br>❌ Hard to rotate keys<br>❌ No built-in expiration | |
| **Tradeoffs — Username/Password** | | ✅ Supports user accounts and roles<br>✅ Better for production systems<br>❌ More complex (sessions, password hashing)<br>❌ Requires password management |

**From wiki:** API-key authentication is a simple shared key mechanism. It has no user accounts, roles, or permissions. It is sufficient for protecting a development API but not for production systems with many users.

**Русский:**
| Аспект | Аутентификация по API-ключу | Аутентификация по имени пользователя/паролю |
|--------|----------------------------|-------------------------------------------|
| **Как работает** | Клиент отправляет секретный ключ в заголовке `Authorization: Bearer <key>` | Клиент отправляет имя пользователя и пароль (обычно в эндпоинт входа) |
| **Обычно используется для** | Коммуникации между сервисами, простых API, сред разработки | Приложений для пользователей, систем с множеством пользователей и ролей |
| **Компромиссы — API-ключ** | ✅ Простота реализации и использования<br>❌ Общий секрет (нет различия пользователей)<br>❌ Сложно ротировать ключи<br>❌ Нет встроенного истечения срока | |
| **Компромиссы — Имя/Пароль** | | ✅ Поддерживает учётные записи и роли<br>✅ Лучше для продакшн-систем<br>❌ Сложнее (сессии, хеширование паролей)<br>❌ Требует управления паролями |

**Из wiki:** Аутентификация по API-ключу — это простой механизм общего ключа. У него нет учётных записей пользователей, ролей или разрешений. Это достаточно для защиты API разработки, но не для продакшн-систем с множеством пользователей.

---

### Q9. Explain the difference between authentication and authorization.

**English:**
**Authentication** — The process of verifying **who you are**. It confirms the identity of a client making a request. Example: Checking if an API key is valid.

**Authorization** — The process of determining **what you're allowed to do**. It checks whether an authenticated client has permission to access a specific endpoint or resource. Example: A user may be authenticated but not have admin privileges.

**Key difference:**
- Authentication = Identity verification ("Are you who you claim to be?")
- Authorization = Permission verification ("Are you allowed to do this?")

**HTTP status codes:**
- `401 Unauthorized` — Not authenticated (missing or invalid credentials)
- `403 Forbidden` — Authenticated but not authorized (no permission for this resource)

**Русский:**
**Аутентификация** — Процесс проверки **кто вы**. Подтверждает личность клиента, делающего запрос. Пример: Проверка действительности API-ключа.

**Авторизация** — Процесс определения **что вам разрешено делать**. Проверяет, имеет ли аутентифицированный клиент разрешение на доступ к конкретному эндпоинту или ресурсу. Пример: Пользователь может быть аутентифицирован, но не иметь прав администратора.

**Ключевое различие:**
- Аутентификация = Проверка личности ("Вы тот, за кого себя выдаёте?")
- Авторизация = Проверка разрешений ("Вам разрешено это делать?")

**HTTP коды статуса:**
- `401 Unauthorized` — Не аутентифицирован (отсутствуют или неверны учётные данные)
- `403 Forbidden` — Аутентифицирован, но не авторизован (нет разрешения на этот ресурс)

---

### Q10. You SSH into your VM and need to harden it. Name at least four security measures you would apply and explain why each matters.

**English:**
1. **Set up `ufw` (Uncomplicated Firewall)**
   - Allow only necessary ports (SSH port 22, gateway port)
   - Deny all other incoming traffic by default
   - **Why:** Reduces attack surface by blocking unauthorized access to services

2. **Set up `fail2ban`**
   - Blocks IP addresses that make too many failed login attempts
   - Rate-limits repeated SSH connection attempts
   - **Why:** Prevents brute-force attacks on SSH and other services

3. **Disable password authentication for SSH** (use SSH keys only)
   - Configure `/etc/ssh/sshd_config` to use key-based authentication
   - **Why:** SSH keys are much more secure than passwords

4. **Keep system updated**
   - Regularly run `sudo apt update && sudo apt upgrade`
   - **Why:** Patches security vulnerabilities in system packages

5. **Use non-root user with sudo**
   - Don't login as root directly
   - Use `sudo` for elevated permissions
   - **Why:** Limits damage from accidental commands or compromised accounts

**Русский:**
1. **Настроить `ufw` (Uncomplicated Firewall)**
   - Разрешить только необходимые порты (SSH порт 22, порт шлюза)
   - По умолчанию запретить весь остальной входящий трафик
   - **Зачем:** Уменьшает поверхность атаки, блокируя несанкционированный доступ к сервисам

2. **Настроить `fail2ban`**
   - Блокирует IP-адреса, которые делают слишком много неудачных попыток входа
   - Ограничивает повторные попытки подключения SSH
   - **Зачем:** Предотвращает brute-force атаки на SSH и другие сервисы

3. **Отключить аутентификацию по паролю для SSH** (использовать только SSH-ключи)
   - Настроить `/etc/ssh/sshd_config` для использования аутентификации по ключам
   - **Зачем:** SSH-ключи намного безопаснее паролей

4. **Держать систему обновлённой**
   - Регулярно запускать `sudo apt update && sudo apt upgrade`
   - **Зачем:** Исправляет уязвимости безопасности в системных пакетах

5. **Использовать нерутового пользователя с sudo**
   - Не входить напрямую как root
   - Использовать `sudo` для повышенных разрешений
   - **Зачем:** Ограничивает ущерб от случайных команд или скомпрометированных учётных записей

---

## Docker & Deployment

### Q11. What is Docker, and how is running an application with Docker different from running it directly with `uv` in a local Python environment?

**English:**
**Docker** is a platform for building and running containers. A container is an isolated runtime for an application and its dependencies.

**Docker vs `uv` local environment:**

| Aspect | Docker | `uv` local Python environment |
|--------|--------|------------------------------|
| **Isolation** | Complete isolation (own filesystem, processes, network) | Shares host OS, only Python packages isolated |
| **Portability** | Same image runs identically on any machine with Docker | Depends on local OS, Python version, system libraries |
| **Dependencies** | Packages OS files, runtime, libraries, application code | Only manages Python packages |
| **Consistency** | Runs consistently across machines | May differ between machines |
| **Multiple services** | Can run multiple services side-by-side with explicit ports/networks | Requires manual setup for multiple services |

**From wiki:** Running an image creates a container. The same image runs identically on any machine with Docker installed. Containers have their own filesystem, processes, and network — they cannot affect other containers or the host machine.

**Русский:**
**Docker** — это платформа для создания и запуска контейнеров. Контейнер — это изолированная среда выполнения для приложения и его зависимостей.

**Docker vs локальное окружение Python с `uv`:**

| Аспект | Docker | Локальное окружение Python с `uv` |
|--------|--------|------------------------------|
| **Изоляция** | Полная изоляция (собственная файловая система, процессы, сеть) | Разделяет хост-ОС, изолированы только Python-пакеты |
| **Портативность** | Один и тот же образ работает одинаково на любой машине с Docker | Зависит от локальной ОС, версии Python, системных библиотек |
| **Зависимости** | Упаковывает файлы ОС, среду выполнения, библиотеки, код приложения | Управляет только Python-пакетами |
| **Консистентность** | Работает одинаково на разных машинах | Может отличаться на разных машинах |
| **Несколько сервисов** | Может запускать несколько сервисов рядом с явными портами/сетями | Требует ручной настройки для нескольких сервисов |

**Из wiki:** Запуск образа создаёт контейнер. Один и тот же образ работает одинаково на любой машине с установленным Docker. Контейнеры имеют собственную файловую систему, процессы и сеть — они не могут влиять на другие контейнеры или хост-машину.

---

### Q12. Explain the difference between a `Dockerfile` and a `docker-compose.yml` file. What problem does each solve, and how do they relate to each other?

**English:**
**Dockerfile:**
- **Purpose:** Defines how to build a single Docker image
- **Contains:** Base image, dependencies, copy commands, build steps, entry point
- **Solves:** How to package one application into a container
- **Example:** `backend/Dockerfile` specifies how to build the backend image

**docker-compose.yml:**
- **Purpose:** Defines how to run multiple containers as a single application
- **Contains:** Service definitions, networks, volumes, dependencies between services
- **Solves:** How to orchestrate multiple services (backend, database, frontend, etc.)
- **Example:** Root `docker-compose.yml` defines `backend`, `postgres`, `caddy`, `pgadmin` services

**Relationship:**
- A `docker-compose.yml` can reference a `Dockerfile` (using `build: ./backend`)
- Or it can use pre-built images (using `image: postgres:15`)
- `Dockerfile` builds one image; `docker-compose.yml` orchestrates multiple containers

**From wiki:** `Docker Compose` runs multi-container apps from a `docker-compose.yml` file. A service is a named entry under `services:` that defines how to build or pull an image and run it as a container.

**Русский:**
**Dockerfile:**
- **Назначение:** Определяет, как собрать один Docker-образ
- **Содержит:** Базовый образ, зависимости, команды копирования, шаги сборки, точку входа
- **Решает:** Как упаковать одно приложение в контейнер
- **Пример:** `backend/Dockerfile` указывает, как собрать образ backend

**docker-compose.yml:**
- **Назначение:** Определяет, как запускать несколько контейнеров как единое приложение
- **Содержит:** Определения сервисов, сети, тома, зависимости между сервисами
- **Решает:** Как оркестрировать несколько сервисов (backend, база данных, frontend и т.д.)
- **Пример:** Корневой `docker-compose.yml` определяет сервисы `backend`, `postgres`, `caddy`, `pgadmin`

**Связь:**
- `docker-compose.yml` может ссылаться на `Dockerfile` (используя `build: ./backend`)
- Или может использовать готовые образы (используя `image: postgres:15`)
- `Dockerfile` собирает один образ; `docker-compose.yml` оркестрирует несколько контейнеров

**Из wiki:** `Docker Compose` запускает многоконтейнерные приложения из файла `docker-compose.yml`. Сервис — это именованная запись под `services:`, которая определяет, как собрать или получить образ и запустить его как контейнер.

---

### Q13. How does Docker layer caching work in principle, and why can Dockerfile order make rebuilds slow?

**English:**
**Docker layer caching principle:**
- Each instruction in a Dockerfile (`FROM`, `RUN`, `COPY`, etc.) creates a new layer
- Layers are cached based on their content and the instruction
- When rebuilding, Docker reuses cached layers if the instruction and its context haven't changed
- Cache is invalidated from the first changed layer onwards

**Why Dockerfile order matters:**
- **Frequently changing layers should be at the bottom** — if you put `COPY . .` early, any file change invalidates all subsequent layers
- **Stable layers should be at the top** — base image, system dependencies that rarely change
- **Bad order example:**
  ```dockerfile
  COPY . .  # Changes every time any file changes
  RUN pip install -r requirements.txt  # Never cached because COPY above changed
  ```
- **Good order example:**
  ```dockerfile
  COPY requirements.txt .  # Only changes when requirements change
  RUN pip install -r requirements.txt  # Cached until requirements.txt changes
  COPY . .  # Application code changes, but dependencies already cached
  ```

**Русский:**
**Принцип кеширования слоёв Docker:**
- Каждая инструкция в Dockerfile (`FROM`, `RUN`, `COPY` и т.д.) создаёт новый слой
- Слои кешируются на основе их содержимого и инструкции
- При пересборке Docker переиспользует кешированные слои, если инструкция и её контекст не изменились
- Кеш аннулируется начиная с первого изменённого слоя

**Почему порядок Dockerfile важен:**
- **Часто изменяющиеся слои должны быть внизу** — если вы разместите `COPY . .` рано, любое изменение файла аннулирует все последующие слои
- **Стабильные слои должны быть вверху** — базовый образ, системные зависимости, которые редко меняются
- **Плохой пример порядка:**
  ```dockerfile
  COPY . .  # Изменяется каждый раз при любом изменении файла
  RUN pip install -r requirements.txt  # Никогда не кешируется, потому что COPY выше изменился
  ```
- **Хороший пример порядка:**
  ```dockerfile
  COPY requirements.txt .  # Изменяется только при изменении requirements
  RUN pip install -r requirements.txt  # Кешируется до изменения requirements.txt
  COPY . .  # Код приложения меняется, но зависимости уже закешированы
  ```

---

### Q14. What is Docker build context, and how can a bad build context make images larger or builds slower?

**English:**
**Docker build context:**
- The build context is the set of files in the specified directory that Docker sends to the Docker daemon during build
- It's defined by the path you specify in `docker build <path>`
- All files in the context are sent before the build starts

**How bad build context causes problems:**

1. **Larger images:**
   - Including unnecessary files (node_modules, .git, __pycache__, large data files) in the context
   - These files may be copied into the image even if not needed
   - Solution: Use `.dockerignore` to exclude unnecessary files

2. **Slower builds:**
   - Large context takes longer to send to Docker daemon
   - Every file change in the context can invalidate cache
   - Solution: Keep context small, use `.dockerignore`

**Example `.dockerignore`:**
```
.git
node_modules
__pycache__
*.pyc
.env
*.log
```

**Русский:**
**Контекст сборки Docker:**
- Контекст сборки — это набор файлов в указанной директории, которые Docker отправляет демону Docker во время сборки
- Он определяется путём, который вы указываете в `docker build <path>`
- Все файлы в контексте отправляются перед началом сборки

**Как плохой контекст сборки вызывает проблемы:**

1. **Большие образы:**
   - Включение ненужных файлов (node_modules, .git, __pycache__, большие файлы данных) в контекст
   - Эти файлы могут быть скопированы в образ, даже если не нужны
   - Решение: Использовать `.dockerignore` для исключения ненужных файлов

2. **Медленные сборки:**
   - Большой контекст дольше отправляется демону Docker
   - Каждое изменение файла в контексте может аннулировать кеш
   - Решение: Держать контекст маленьким, использовать `.dockerignore`

**Пример `.dockerignore`:**
```
.git
node_modules
__pycache__
*.pyc
.env
*.log
```

---

## Testing

### Q15. What is the difference between a unit test and an end-to-end (E2E) test? Describe what kinds of bugs each is designed to catch. Give one advantage and one disadvantage of each.

**English:**
| Aspect | Unit Test | End-to-End (E2E) Test |
|--------|-----------|----------------------|
| **Scope** | Tests individual function/module in isolation | Tests the full system working together |
| **Bugs caught** | Logic errors in specific functions, edge cases, input validation | Integration bugs, API contract violations, deployment issues |
| **Dependencies** | No external dependencies (mocked/stubbed) | Real services (database, API, network) |
| **Speed** | Fast (milliseconds) | Slow (seconds to minutes) |
| **Advantage** | Fast execution, precise failure location | Catches real-world integration issues |
| **Disadvantage** | May miss integration problems | Slower, harder to debug, flaky |

**From wiki:**
- **Unit test:** Verifies that an individual function or module works correctly in isolation. Unit tests are fast because they don't depend on external services.
- **E2E test:** Verifies that the full system works correctly by sending real HTTP requests to the deployed application and checking the responses. E2E tests are slower because they depend on running services.

**Русский:**
| Аспект | Юнит-тест | End-to-End (E2E) тест |
|--------|-----------|----------------------|
| **Объём** | Тестирует отдельную функцию/модуль в изоляции | Тестирует полную систему, работающую вместе |
| **Отлавливаемые ошибки** | Ошибки логики в конкретных функциях, граничные случаи, валидация ввода | Ошибки интеграции, нарушения контракта API, проблемы развёртывания |
| **Зависимости** | Нет внешних зависимостей (моки/заглушки) | Реальные сервисы (база данных, API, сеть) |
| **Скорость** | Быстро (миллисекунды) | Медленно (секунды-минуты) |
| **Преимущество** | Быстрое выполнение, точное местоположение сбоя | Отлавливает проблемы интеграции в реальном мире |
| **Недостаток** | Может пропустить проблемы интеграции | Медленнее, сложнее отладка, нестабильные |

**Из wiki:**
- **Юнит-тест:** Проверяет, что отдельная функция или модуль работает корректно в изоляции. Юнит-тесты быстрые, потому что не зависят от внешних сервисов.
- **E2E-тест:** Проверяет, что полная система работает корректно, отправляя реальные HTTP-запросы к развёрнутому приложению и проверяя ответы. E2E-тесты медленнее, потому что зависят от работающих сервисов.

---

### Q16. Define boundary-value analysis. For a function `get_grade(score: int)` that returns "F" for 0–49, "C" for 50–74, "B" for 75–89, and "A" for 90–100, list the specific boundary values you would test.

**English:**
**Boundary-value analysis** is a testing technique that focuses on the edges of input ranges — values like 0, 1, an empty list, or the maximum allowed size. Bugs often occur at these boundaries because of off-by-one errors, missing edge-case handling, or incorrect comparison operators.

**For `get_grade(score: int)`:**

| Grade | Range | Boundary values to test |
|-------|-------|------------------------|
| F | 0–49 | **-1** (invalid), **0** (min), **49** (max F), **50** (min C) |
| C | 50–74 | **49** (max F), **50** (min C), **74** (max C), **75** (min B) |
| B | 75–89 | **74** (max C), **75** (min B), **89** (max B), **90** (min A) |
| A | 90–100 | **89** (max B), **90** (min A), **100** (max), **101** (invalid) |

**Specific test values:** -1, 0, 49, 50, 74, 75, 89, 90, 100, 101

**From wiki:** When writing tests, check both sides of each boundary: the value just inside the valid range and the value just outside it.

**Русский:**
**Граничный анализ** — это техника тестирования, которая фокусируется на краях диапазонов ввода — значениях вроде 0, 1, пустого списка или максимального допустимого размера. Ошибки часто возникают на этих границах из-за ошибок на единицу (off-by-one), отсутствия обработки граничных случаев или неверных операторов сравнения.

**Для `get_grade(score: int)`:**

| Оценка | Диапазон | Граничные значения для тестирования |
|--------|---------|-------------------------------------|
| F | 0–49 | **-1** (неверно), **0** (мин), **49** (макс F), **50** (мин C) |
| C | 50–74 | **49** (макс F), **50** (мин C), **74** (макс C), **75** (мин B) |
| B | 75–89 | **74** (макс C), **75** (мин B), **89** (макс B), **90** (мин A) |
| A | 90–100 | **89** (макс B), **90** (мин A), **100** (макс), **101** (неверно) |

**Конкретные тестовые значения:** -1, 0, 49, 50, 74, 75, 89, 90, 100, 101

**Из wiki:** При написании тестов проверяйте обе стороны каждой границы: значение прямо внутри допустимого диапазона и значение прямо за его пределами.

---

## Data Pipelines

### Q17. Explain what an ETL pipeline is (what each letter stands for and means). In the context of syncing data from an external API to a local PostgreSQL database, give a concrete example of what happens in each stage.

**English:**
**ETL** stands for:
- **E**xtract — Get data from source systems
- **T**ransform — Convert data to the target format
- **L**oad — Write data to the destination

**Concrete example (syncing from Autochecker API to PostgreSQL):**

1. **Extract:**
   - Make HTTP requests to the Autochecker API endpoints
   - Fetch data about submissions, scores, learners, tasks
   - Example: `GET /api/submissions` returns JSON with submission records

2. **Transform:**
   - Parse JSON responses
   - Validate data types and required fields
   - Convert data to match PostgreSQL schema (e.g., parse dates, normalize field names)
   - Handle duplicates (upsert logic)
   - Example: Convert timestamp string to PostgreSQL `TIMESTAMP` type

3. **Load:**
   - Insert or update records in PostgreSQL tables (`submissions`, `learners`, `items`, etc.)
   - Use transactions to ensure data consistency
   - Track loaded records count (new_records, total_records)
   - Example: `INSERT INTO submissions (...) ON CONFLICT (id) DO UPDATE SET ...`

**From wiki:** In Lab 8, the ETL pipeline is triggered by `POST /pipeline/sync` endpoint and populates the database with data from the Autochecker API.

**Русский:**
**ETL** расшифровывается как:
- **E**xtract (Извлечение) — Получение данных из исходных систем
- **T**ransform (Трансформация) — Преобразование данных в целевой формат
- **L**oad (Загрузка) — Запись данных в место назначения

**Конкретный пример (синхронизация из Autochecker API в PostgreSQL):**

1. **Извлечение:**
   - Сделать HTTP-запросы к эндпоинтам Autochecker API
   - Получить данные о submission, оценках, студентах, задачах
   - Пример: `GET /api/submissions` возвращает JSON с записями submission

2. **Трансформация:**
   - Разобрать JSON-ответы
   - Проверить типы данных и обязательные поля
   - Преобразовать данные для соответствия схеме PostgreSQL (например, разобрать даты, нормализовать имена полей)
   - Обработать дубликаты (логика upsert)
   - Пример: Преобразовать строку timestamp в тип PostgreSQL `TIMESTAMP`

3. **Загрузка:**
   - Вставить или обновить записи в таблицах PostgreSQL (`submissions`, `learners`, `items` и т.д.)
   - Использовать транзакции для обеспечения согласованности данных
   - Отслеживать количество загруженных записей (new_records, total_records)
   - Пример: `INSERT INTO submissions (...) ON CONFLICT (id) DO UPDATE SET ...`

**Из wiki:** В Lab 8 ETL-пайплайн запускается эндпоинтом `POST /pipeline/sync` и заполняет базу данных данными из Autochecker API.

---

## LLM Agents & Tool Use

### Q18. Describe the agentic loop step by step, from user input to final answer. Include what happens when the LLM requests a tool call.

**English:**
**The agentic loop:**

1. **User input** — User sends a question or request to the agent
2. **Context preparation** — Agent gathers relevant context (files, conversation history, system prompt)
3. **LLM inference** — Agent sends the prompt to the LLM with available tool descriptions
4. **LLM decision:**
   - **If LLM has enough information:** Returns final answer directly
   - **If LLM needs more information:** Returns a tool call request (which tool to call and with what arguments)
5. **Tool execution (if requested):**
   - Agent executes the requested tool (e.g., read_file, search, run_command)
   - Tool returns output (file contents, search results, command output)
6. **Observation** — Agent adds tool output to the conversation as an observation
7. **Loop back to step 3** — LLM receives the observation and decides:
   - Make another tool call
   - Provide final answer
8. **Final answer** — LLM generates the final response to the user

**From wiki:** The LLM reads tool descriptions to decide which to call. When the LLM requests a tool call, the agent executes it and returns the result as an observation.

**Русский:**
**Агентный цикл:**

1. **Ввод пользователя** — Пользователь отправляет вопрос или запрос агенту
2. **Подготовка контекста** — Агент собирает релевантный контекст (файлы, историю разговора, системный промпт)
3. **Инференс LLM** — Агент отправляет промпт в LLM с описаниями доступных инструментов
4. **Решение LLM:**
   - **Если у LLM достаточно информации:** Возвращает окончательный ответ напрямую
   - **Если LLM нужно больше информации:** Возвращает запрос вызова инструмента (какой инструмент вызвать и с какими аргументами)
5. **Выполнение инструмента (если запрошено):**
   - Агент выполняет запрошенный инструмент (например, read_file, search, run_command)
   - Инструмент возвращает вывод (содержимое файла, результаты поиска, вывод команды)
6. **Наблюдение** — Агент добавляет вывод инструмента в разговор как наблюдение
7. **Возврат к шагу 3** — LLM получает наблюдение и решает:
   - Сделать ещё один вызов инструмента
   - Предоставить окончательный ответ
8. **Окончательный ответ** — LLM генерирует финальный ответ пользователю

**Из wiki:** LLM читает описания инструментов, чтобы решить, какой вызвать. Когда LLM запрашивает вызов инструмента, агент выполняет его и возвращает результат как наблюдение.

---

### Q19. If an agent read too little code and gave an incorrect answer about the API, what went wrong in its tool-use strategy?

**English:**
**What went wrong:**

1. **Insufficient context engineering** — The agent didn't include enough relevant files in the context
2. **Poor tool selection** — The agent chose not to use file-reading tools when it should have
3. **Incomplete tool descriptions** — The tool descriptions in the system prompt may not clearly indicate when to use each tool
4. **Premature conclusion** — The LLM made assumptions without gathering enough evidence

**The root cause:** The agent's tool-use strategy failed because:
- It didn't recognize that it needed more information about the API
- It didn't use available tools (like `read_file`, `grep_search`) to gather that information
- The context window may have been too small or poorly managed

**From wiki:** Context engineering is the practice of deliberately choosing what information to include in the context to get better results from an LLM. When using a coding agent, you control the context by referencing specific files, pasting error messages, and providing acceptance criteria.

**Solution:** Improve tool descriptions to make it clearer when the LLM should read code, or provide more explicit instructions in the system prompt about gathering context before answering.

**Русский:**
**Что пошло не так:**

1. **Недостаточное проектирование контекста** — Агент не включил достаточно релевантных файлов в контекст
2. **Плохой выбор инструмента** — Агент решил не использовать инструменты чтения файлов, когда должен был
3. **Неполные описания инструментов** — Описания инструментов в системном промпте могут неясно указывать, когда использовать каждый инструмент
4. **Преждевременный вывод** — LLM сделал предположения без сбора достаточных доказательств

**Коренная причина:** Стратегия использования инструментов агентом провалилась, потому что:
- Он не распознал, что ему нужно больше информации об API
- Он не использовал доступные инструменты (такие как `read_file`, `grep_search`) для сбора этой информации
- Окно контекста могло быть слишком маленьким или плохо управляемым

**Из wiki:** Проектирование контекста — это практика преднамеренного выбора того, какую информацию включить в контекст для получения лучших результатов от LLM. При использовании кодирующего агента вы контролируете контекст, ссылаясь на конкретные файлы, вставляя сообщения об ошибках и предоставляя критерии приёмки.

**Решение:** Улучшить описания инструментов, чтобы сделать более ясным, когда LLM должен читать код, или предоставить более явные инструкции в системном промпте о сборе контекста перед ответом.

---

## Bot Architecture & Integration

### Q20. How to separate Telegram transport code from business logic so the bot can be tested without Telegram?

**English:**
**Separation strategy:**

1. **Create handler functions** — Pure functions that take input (command/text) and return text response
   - No Telegram dependencies
   - Can be called from `--test` mode, unit tests, or Telegram

2. **Separate layers:**
   ```
   bot.py (Telegram transport)
       ↓
   handlers/ (business logic)
       ↓
   services/ (API client, LLM client)
   ```

3. **Test mode in bot.py:**
   ```python
   if __name__ == "__main__":
       if "--test" in sys.argv:
           # Run handlers directly without Telegram
           command = sys.argv[sys.argv.index("--test") + 1]
           result = handle_command(command)
           print(result)
       else:
           # Run Telegram bot
           run_telegram_bot()
   ```

4. **Handler example:**
   ```python
   # handlers/commands.py
   def handle_start() -> str:
       return "Welcome! Use /help for commands."
   
   def handle_health() -> str:
       return "Backend: OK, Database: OK"
   ```

**From wiki:** A handler is a function that takes input and returns text. It doesn't depend on Telegram. You can call it from `--test` mode, from tests, or from Telegram — same function. This is called **separation of concerns**.

**Русский:**
**Стратегия разделения:**

1. **Создать функции-обработчики** — Чистые функции, которые принимают ввод (команда/текст) и возвращают текстовый ответ
   - Нет зависимостей от Telegram
   - Можно вызывать из режима `--test`, юнит-тестов или Telegram

2. **Разделить слои:**
   ```
   bot.py (транспорт Telegram)
       ↓
   handlers/ (бизнес-логика)
       ↓
   services/ (API-клиент, LLM-клиент)
   ```

3. **Режим тестирования в bot.py:**
   ```python
   if __name__ == "__main__":
       if "--test" in sys.argv:
           # Запустить обработчики напрямую без Telegram
           command = sys.argv[sys.argv.index("--test") + 1]
           result = handle_command(command)
           print(result)
       else:
           # Запустить Telegram-бот
           run_telegram_bot()
   ```

4. **Пример обработчика:**
   ```python
   # handlers/commands.py
   def handle_start() -> str:
       return "Добро пожаловать! Используйте /help для команд."
   
   def handle_health() -> str:
       return "Backend: OK, Database: OK"
   ```

**Из wiki:** Обработчик — это функция, которая принимает ввод и возвращает текст. Он не зависит от Telegram. Вы можете вызвать его из режима `--test`, из тестов или из Telegram — одна и та же функция. Это называется **разделение ответственности**.

---

### Q21. Compare LLM-based intent routing with traditional command parsing. Give one advantage and one disadvantage of each.

**English:**
| Aspect | LLM-based Intent Routing | Traditional Command Parsing |
|--------|-------------------------|----------------------------|
| **How it works** | LLM reads user input and tool descriptions, decides which tool to call | Regex or keyword matching to identify commands |
| **Advantage** | Handles natural language, typos, variations ("show scores", "what are my scores", "scores please") | Fast, predictable, no LLM cost |
| **Disadvantage** | Slower, costs tokens, can be unpredictable | Rigid — exact command syntax required |

**LLM-based routing:**
- **Advantage:** Users can ask questions in natural language; the LLM understands intent even with variations
- **Disadvantage:** Requires LLM API calls (cost, latency), may call wrong tools if descriptions are unclear

**Traditional parsing:**
- **Advantage:** Instant response, no external dependencies, completely predictable
- **Disadvantage:** Users must know exact commands; "show my score" fails if only `/scores` is recognized

**From wiki:** Don't use regex or keyword matching to decide which tool to call. If the LLM isn't calling tools, the fix is in the system prompt or tool descriptions — not in code-based routing. Replacing LLM routing with regex defeats the entire point of the task.

**Русский:**
| Аспект | Маршрутизация намерений на основе LLM | Традиционный парсинг команд |
|--------|--------------------------------------|----------------------------|
| **Как работает** | LLM читает ввод пользователя и описания инструментов, решает, какой инструмент вызвать | Regex или сопоставление ключевых слов для идентификации команд |
| **Преимущество** | Обрабатывает естественный язык, опечатки, вариации ("показать оценки", "какие у меня оценки", "оценки пожалуйста") | Быстро, предсказуемо, нет стоимости LLM |
| **Недостаток** | Медленнее, стоит токенов, может быть непредсказуемо | Жёстко — требуется точный синтаксис команды |

**Маршрутизация на основе LLM:**
- **Преимущество:** Пользователи могут задавать вопросы на естественном языке; LLM понимает намерение даже с вариациями
- **Недостаток:** Требует вызовов LLM API (стоимость, задержка), может вызывать не те инструменты, если описания неясны

**Традиционный парсинг:**
- **Преимущество:** Мгновенный ответ, нет внешних зависимостей, полностью предсказуемо
- **Недостаток:** Пользователи должны знать точные команды; "показать мою оценку" не сработает, если распознан только `/scores`

**Из wiki:** Не используйте regex или сопоставление ключевых слов для решения, какой инструмент вызвать. Если LLM не вызывает инструменты, исправление — в системном промпте или описаниях инструментов, а не в маршрутизации на основе кода. Замена LLM-маршрутизации на regex противоречит всей сути задачи.

---

## System Design

### Q22. Draw and describe the architecture of the LMS system we built during the labs. Include all components, how they communicate and are deployed.

**English:**
**LMS System Architecture:**

```
┌─────────────────────────────────────────────────────────────────┐
│                         USER DEVICES                            │
│    ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐   │
│    │   Browser   │  │  Telegram   │  │   Swagger UI        │   │
│    │  (Flutter)  │  │    Bot      │  │   (/docs)           │   │
│    └──────┬──────┘  └──────┬──────┘  └──────────┬──────────┘   │
│           │                │                     │              │
│           └────────────────┼─────────────────────┘              │
│                            │                                    │
│                    HTTP/HTTPS                                    │
│                    (Port 42002)                                  │
└────────────────────────────┼────────────────────────────────────┘
                             │
                    ┌────────▼────────┐
                    │     CADDY       │
                    │   (Gateway)     │
                    │  Reverse Proxy  │
                    └────────┬────────┘
                             │
         ┌───────────────────┼───────────────────┐
         │                   │                   │
         ▼                   ▼                   ▼
┌────────────────┐  ┌────────────────┐  ┌────────────────┐
│    BACKEND     │  │    POSTGRES    │  │    PGADMIN     │
│   (FastAPI)    │  │   (Database)   │  │   (Admin UI)   │
│   Port 8000    │  │   Port 5432    │  │   Port 5050    │
│                │  │                │  │                │
│ - /items       │  │ - items        │  │ - Manage DB    │
│ - /learners    │  │ - learners     │  │ - View tables  │
│ - /interactions│  │ - interactions │  │                │
│ - /pipeline    │  │ - submissions  │  │                │
│ - /analytics   │  │ - scores       │  │                │
└───────┬────────┘  └────────────────┘  └────────────────┘
        │
        │ ETL Pipeline
        │ (POST /pipeline/sync)
        │
        ▼
┌─────────────────────────────────────────────────────────────────┐
│                    EXTERNAL SERVICES                            │
│    ┌─────────────────────┐  ┌─────────────────────┐            │
│    │  Autochecker API    │  │   LLM Provider API  │            │
│    │  (External LMS)     │  │   (OpenAI-compatible)│           │
│    └─────────────────────┘  └─────────────────────┘            │
└─────────────────────────────────────────────────────────────────┘

                    DEPLOYMENT: Docker VM
                    ┌───────────────────────┐
                    │   docker-compose.yml  │
                    │   - backend service   │
                    │   - postgres service  │
                    │   - caddy service     │
                    │   - pgadmin service   │
                    └───────────────────────┘
```

**Components:**

1. **Caddy (Gateway)** — Single entry point, reverse proxy
   - Listens on port 42002
   - Routes API requests to backend
   - Serves static frontend files
   - Routes `/utils/pgadmin*` to pgAdmin

2. **Backend (FastAPI)** — Application logic
   - REST API endpoints (`/items`, `/learners`, `/interactions`, `/pipeline`, `/analytics`)
   - ETL pipeline for data sync
   - Authentication via API key

3. **PostgreSQL** — Database
   - Stores items, learners, interactions, submissions, scores
   - Persistent volume for data

4. **pgAdmin** — Database administration
   - Web UI for database management
   - Accessible via `/utils/pgadmin`

5. **Frontend (Flutter Web)** — User interface
   - Dashboard with analytics
   - Authentication with LMS API key

6. **Telegram Bot (Optional)** — Alternative interface
   - Connects via WebSocket to Nanobot agent
   - Uses same backend API

**Communication:**
- All internal communication via Docker network (service names)
- External access through Caddy gateway only
- Backend ↔ PostgreSQL: SQL queries
- Backend ↔ Autochecker API: HTTP requests (ETL)
- Frontend/Bot ↔ Backend: HTTP/HTTPS via Caddy

**Deployment:**
- All services run as Docker containers on a VM
- Managed via `docker-compose.yml`
- Environment variables in `.env.docker.secret`
- VM hardened with `ufw` firewall and `fail2ban`

**From wiki:** The gateway is the single entry point to the LMS system. `Docker Compose` creates a network where services can reach each other by service name. The ETL pipeline syncs data from Autochecker API to PostgreSQL.

**Русский:**
**Архитектура системы LMS:**

```
┌─────────────────────────────────────────────────────────────────┐
│                         УСТРОЙСТВА ПОЛЬЗОВАТЕЛЕЙ                │
│    ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐   │
│    │   Браузер   │  │  Telegram   │  │   Swagger UI        │   │
│    │  (Flutter)  │  │    Бот      │  │   (/docs)           │   │
│    └──────┬──────┘  └──────┬──────┘  └──────────┬──────────┘   │
│           │                │                     │              │
│           └────────────────┼─────────────────────┘              │
│                            │                                    │
│                    HTTP/HTTPS                                    │
│                    (Порт 42002)                                  │
└────────────────────────────┼────────────────────────────────────┘
                             │
                    ┌────────▼────────┐
                    │     CADDY       │
                    │   (Шлюз)        │
                    │  Обратный прокси│
                    └────────┬────────┘
                             │
         ┌───────────────────┼───────────────────┐
         │                   │                   │
         ▼                   ▼                   ▼
┌────────────────┐  ┌────────────────┐  ┌────────────────┐
│    BACKEND     │  │    POSTGRES    │  │    PGADMIN     │
│   (FastAPI)    │  │   (База данных)│  │   (Админ UI)   │
│   Порт 8000    │  │   Порт 5432    │  │   Порт 5050    │
│                │  │                │  │                │
│ - /items       │  │ - items        │  │ - Управление БД│
│ - /learners    │  │ - learners     │  │ - Просмотр     │
│ - /interactions│  │ - interactions │  │   таблиц       │
│ - /pipeline    │  │ - submissions  │  │                │
│ - /analytics   │  │ - scores       │  │                │
└───────┬────────┘  └────────────────┘  └────────────────┘
        │
        │ ETL Pipeline
        │ (POST /pipeline/sync)
        │
        ▼
┌─────────────────────────────────────────────────────────────────┐
│                    ВНЕШНИЕ СЕРВИСЫ                              │
│    ┌─────────────────────┐  ┌─────────────────────┐            │
│    │  Autochecker API    │  │   LLM Provider API  │            │
│    │  (Внешняя LMS)      │  │   (OpenAI-совмест.) │            │
│    └─────────────────────┘  └─────────────────────┘            │
└─────────────────────────────────────────────────────────────────┘

                    РАЗВЁРТЫВАНИЕ: Docker VM
                    ┌───────────────────────┐
                    │   docker-compose.yml  │
                    │   - backend service   │
                    │   - postgres service  │
                    │   - caddy service     │
                    │   - pgadmin service   │
                    └───────────────────────┘
```

**Компоненты:**

1. **Caddy (Шлюз)** — Единая точка входа, обратный прокси
   - Слушает порт 42002
   - Маршрутизирует API-запросы в backend
   - Обслуживает статические файлы frontend
   - Маршрутизирует `/utils/pgadmin*` в pgAdmin

2. **Backend (FastAPI)** — Логика приложения
   - REST API эндпоинты (`/items`, `/learners`, `/interactions`, `/pipeline`, `/analytics`)
   - ETL pipeline для синхронизации данных
   - Аутентификация через API-ключ

3. **PostgreSQL** — База данных
   - Хранит items, learners, interactions, submissions, scores
   - Постоянный том для данных

4. **pgAdmin** — Администрирование БД
   - Веб-интерфейс для управления БД
   - Доступ через `/utils/pgadmin`

5. **Frontend (Flutter Web)** — Пользовательский интерфейс
   - Dashboard с аналитикой
   - Аутентификация с LMS API key

6. **Telegram Bot (Опционально)** — Альтернативный интерфейс
   - Подключается через WebSocket к агенту Nanobot
   - Использует тот же backend API

**Коммуникация:**
- Вся внутренняя коммуникация через Docker сеть (имена сервисов)
- Внешний доступ только через шлюз Caddy
- Backend ↔ PostgreSQL: SQL-запросы
- Backend ↔ Autochecker API: HTTP-запросы (ETL)
- Frontend/Bot ↔ Backend: HTTP/HTTPS через Caddy

**Развёртывание:**
- Все сервисы работают как Docker-контейнеры на VM
- Управляются через `docker-compose.yml`
- Переменные окружения в `.env.docker.secret`
- VM укреплена с `ufw` firewall и `fail2ban`

**Из wiki:** Шлюз — это единая точка входа в систему LMS. `Docker Compose` создаёт сеть, где сервисы могут достигать друг друга по имени сервиса. ETL pipeline синхронизирует данные из Autochecker API в PostgreSQL.

---

## Sources

All answers are based on the project's wiki documentation located in the `wiki/` folder, including:

- `git-workflow.md`, `git.md`
- `http.md`, `rest-api.md`, `http-auth.md`
- `security.md`, `vm-hardening.md`, `ssh.md`, `linux-administration.md`
- `docker.md`, `docker-compose.md`, `docker-compose-yml.md`
- `quality-assurance.md`
- `lms-api-deployment.md`, `postgresql.md`, `lms-api.md`, `gateway.md`
- `llm.md`, `coding-agents.md`
- `bot.md`, `client-telegram-bot.md`
- `architecture.md`, `swagger.md`, `database-modeling.md`
