# chrome-extension-publisher

> CLI tool to validate and publish Chrome extensions to the Chrome Web Store.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## Install

```bash
npm install -g chrome-extension-publisher
```

Or use locally in a project:

```bash
npm install --save-dev chrome-extension-publisher
```

This installs the `ext-publish` command.

## Usage

```bash
ext-publish <command> [options]
```

### Commands

#### `validate <dir>` -- Validate an extension before upload

Checks that `manifest.json` exists and contains all required fields (`name`, `version`, `manifest_version`).

```bash
ext-publish validate ./dist

# Output:
# Manifest valid
#    Name: My Extension
#    Version: 1.2.0
#    Manifest: v3
```

#### `upload <zip>` -- Upload a packaged extension

Upload a `.zip` file to the Chrome Web Store.

```bash
ext-publish upload ./extension.zip
```

#### `publish <zip>` -- Upload and submit for review

Uploads the package and marks it for publishing after review.

```bash
ext-publish publish ./extension.zip
```

#### `status <ext-id>` -- Check publishing status

Query the current status of an extension by its ID.

```bash
ext-publish status abcdefghijklmnopqrstuvwxyz
```

#### `help` -- Show usage information

```bash
ext-publish help
```

## Configuration

### OAuth2 Credentials

The `upload` and `publish` commands require Chrome Web Store API credentials. Pass them as CLI flags:

```bash
ext-publish upload ./extension.zip \
  --client-id "your-client-id" \
  --client-secret "your-client-secret" \
  --refresh-token "your-refresh-token"
```

### Getting Credentials

1. Go to the [Google Cloud Console](https://console.cloud.google.com/)
2. Create a project and enable the Chrome Web Store API
3. Create OAuth2 credentials (Desktop application)
4. Generate a refresh token using the OAuth2 flow

## API

### CLI Options

| Option | Description |
| --- | --- |
| `--client-id` | OAuth2 client ID for Chrome Web Store API |
| `--client-secret` | OAuth2 client secret |
| `--refresh-token` | OAuth2 refresh token |

### Commands Reference

| Command | Arguments | Description |
| --- | --- | --- |
| `upload` | `<zip-path>` | Upload extension package to Chrome Web Store |
| `publish` | `<zip-path>` | Upload and submit for review |
| `status` | `<extension-id>` | Check publishing status of an extension |
| `validate` | `<directory>` | Validate manifest.json in the given directory |
| `help` | -- | Show usage information |

## License

MIT
