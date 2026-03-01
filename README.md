# chrome-extension-publisher

CLI tool to automate Chrome Web Store publishing.

## Install

```bash
npm install -g chrome-extension-publisher
```

## Usage

```bash
# Validate before publishing
ext-publish validate ./my-extension

# Upload to Web Store
ext-publish upload ./extension.zip
```

## Setup OAuth2

1. Go to Chrome Web Store Developer Dashboard
2. Create OAuth2 credentials
3. Set environment variables:
```bash
export EXT_CLIENT_ID="your-client-id"
export EXT_CLIENT_SECRET="your-secret"
export EXT_REFRESH_TOKEN="your-token"
```

## License

MIT
