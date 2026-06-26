# create-framework-x

A single bash script that scaffolds a new [Framework-X](https://github.com/clue/framework-x) PHP project in seconds.

## Prerequisites

- PHP (any recent version)
- [Composer](https://getcomposer.org/download/)

## Installation

Clone this repo and add it to your `$PATH`:

```bash
git clone https://github.com/yourusername/framework-x-cli.git
export PATH="$PATH:/path/to/framework-x-cli"
```

Or run it directly without installing:

```bash
bash /path/to/create-framework-x my-app
```

## Usage

```bash
create-framework-x my-app
```

This will:

1. Create a `my-app/` directory
2. Install `clue/framework-x` via Composer
3. Write a starter `public/index.php`
4. Start a dev server at **http://localhost:8000**

Press `Ctrl+C` to stop the server.

## What you get

```
my-app/
├── composer.json
├── composer.lock
├── vendor/
└── public/
    └── index.php
```

The starter app has two routes:

- `GET /` → `Hello wörld!`
- `GET /users/{name}` → `Hello {name}!`
