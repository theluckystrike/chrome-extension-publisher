# chrome-extension-publisher

[![npm version](https://img.shields.io/npm/v/chrome-extension-publisher)](https://npmjs.com/package/chrome-extension-publisher)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/theluckystrike/chrome-extension-publisher?style=social)](https://github.com/theluckystrike/chrome-extension-publisher)

CLI tool for validating and publishing Chrome extensions to the Chrome Web Store. Provides four commands to validate manifest files, upload zip packages, publish extensions, and check publishing status.

Part of the [Zovo](https://zovo.one) developer tools family.

INSTALL

```bash
npm install -g chrome-extension-publisher
```

Or add it to a project as a dev dependency:

```bash
npm install --save-dev chrome-extension-publisher
```

This makes the `ext-publish` command available.

USAGE

```bash
ext-publish <command> [options]
```

COMMANDS

`validate <dir>` validates a Chrome extension directory by checking that `manifest.json` exists and contains the required fields: `name`, `version`, and `manifest_version`.

```bash
ext-publish validate ./dist

# Manifest valid
#    Name: My Extension
#    Version: 1.2.0
#    Manifest: v3
```

`upload <zip>` uploads a zipped extension package to the Chrome Web Store. Requires OAuth2 credentials.

```bash
ext-publish upload ./extension.zip
```

`publish <zip>` uploads the package and submits it for review in a single step.

```bash
ext-publish publish ./extension.zip
```

`status <ext-id>` checks the current publishing status of an extension by its Web Store ID.

```bash
ext-publish status abcdefghijklmnopqrstuvwxyz
```

`help` prints usage information and available options.

```bash
ext-publish help
```

OAUTH2 CREDENTIALS

The `upload` and `publish` commands require Chrome Web Store API credentials passed as CLI flags:

```bash
ext-publish upload ./extension.zip \
  --client-id "your-client-id" \
  --client-secret "your-client-secret" \
  --refresh-token "your-refresh-token"
```

To obtain credentials:

1. Open the [Google Cloud Console](https://console.cloud.google.com/)
2. Create a project and enable the Chrome Web Store API
3. Create OAuth2 credentials for a Desktop application
4. Generate a refresh token using the OAuth2 flow

CLI OPTIONS

| Flag | Purpose |
| --- | --- |
| `--client-id` | OAuth2 client ID for Chrome Web Store API |
| `--client-secret` | OAuth2 client secret |
| `--refresh-token` | OAuth2 refresh token |

CONTRIBUTING

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on reporting issues, development workflow, and submitting pull requests.

LICENSE

MIT. See [LICENSE](LICENSE) for the full text.

---

Built by [Zovo](https://zovo.one)
