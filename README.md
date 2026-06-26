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

**Option 2 — Add to PATH**

```bash
git clone https://github.com/yourusername/framework-x-cli.git
```

Add to your `~/.zshrc` (or `~/.bashrc`):

```bash
export PATH="$PATH:/path/to/framework-x-cli"
```

Then reload your shell:

```bash
source ~/.zshrc
```

**Option 3 — Symlink into `/usr/local/bin`**

```bash
ln -s /path/to/framework-x-cli/create-framework-x /usr/local/bin/create-framework-x
```

## Usage

```bash
create-framework-x my-app
```

This will:

1. Create a `my-app/` directory
2. Write `composer.json` with Framework-X and PHPUnit
3. Run `composer install`
4. Write the starter app and tests
5. Start a dev server at **http://localhost:8000**

Press `Ctrl+C` to stop the server.

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
│   └── UserController.php
├── tests/
│   ├── HelloControllerTest.php
│   └── UserControllerTest.php
└── vendor/
```

The starter app has two routes:

- `GET /` → `Hello wörld!`
- `GET /users/{name}` → `Hello {name}!`

## Running tests

```bash
cd my-app
vendor/bin/phpunit
```
