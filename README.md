# create-framework-x

A single bash script that scaffolds a new [Framework-X](https://github.com/clue/framework-x) PHP project in seconds.

## Prerequisites

- PHP (any recent version)
- [Composer](https://getcomposer.org/download/)

## Installation

**Option 1 — Run directly (no install needed)**

```bash
bash /path/to/create-framework-x my-app
```

**Option 2 — Symlink into `/usr/local/bin`**

```bash
ln -s /path/to/framework-x-cli/create-framework-x /usr/local/bin/create-framework-x
```

## Usage

```bash
# Basic
create-framework-x my-app

# With Docker
create-framework-x my-app --with-docker
```

Basic scaffolds and starts a dev server at **http://localhost:8000**. With `--with-docker` it also generates a `Dockerfile` and `docker-compose.yml`, then runs `docker compose up --build` on **http://localhost:8080**.

Press `Ctrl+C` to stop.

## What you get

```
my-app/
├── composer.json
├── composer.lock
├── phpunit.xml
├── public/
│   └── index.php
├── src/
│   ├── HelloController.php
│   ├── UserController.php
│   └── CreateUserController.php
├── tests/
│   ├── HelloControllerTest.php
│   ├── UserControllerTest.php
│   └── CreateUserControllerTest.php
└── vendor/
```

With `--with-docker`:

```
my-app/
├── Dockerfile
├── docker-compose.yml
└── .dockerignore
```

## Routes

| Method | Path | Description | Example response |
|--------|------|-------------|-----------------|
| `GET` | `/` | Hello world | `Hello wörld!` |
| `GET` | `/users/{name}` | Greet by name | `Hello Alice!` |
| `POST` | `/users` | Create user (JSON body) | `Hello Alice!` (201) |

```bash
curl http://localhost:8000/
curl http://localhost:8000/users/Alice
curl -X POST http://localhost:8000/users \
  -H 'Content-Type: application/json' \
  -d '{"name":"Alice"}'
```

## Running tests

```bash
cd my-app
vendor/bin/phpunit
```
