# chrome-extension-publisher

[![npm version](https://img.shields.io/npm/v/chrome-extension-publisher)](https://npmjs.com/package/chrome-extension-publisher)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue.svg)](https://www.typescriptlang.org/)
[![Discord](https://img.shields.io/badge/Discord-Zovo-blueviolet.svg?logo=discord)](https://discord.gg/zovo)
[![Website](https://img.shields.io/badge/Website-zovo.one-blue)](https://zovo.one)
[![GitHub Stars](https://img.shields.io/github/stars/theluckystrike/chrome-extension-publisher?style=social)](https://github.com/theluckystrike/chrome-extension-publisher)

> CLI tool to validate and publish Chrome extensions to the Chrome Web Store.

Part of the [Zovo](https://zovo.one) developer tools family.

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

## See Also

- [chrome-extension-cli](https://github.com/theluckystrike/chrome-extension-cli) - The CLI for your next Chrome Extension
- [chrome-extension-starter-mv3](https://github.com/theluckystrike/chrome-extension-starter-mv3) - Production-ready Chrome Extension starter template
- [crx-manifest-validator](https://github.com/theluckystrike/crx-manifest-validator) - CLI + library to validate Chrome extension manifest.json files

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

Built by [Zovo](https://zovo.one)
