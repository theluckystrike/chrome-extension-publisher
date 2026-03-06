# Contributing to chrome-extension-publisher

Thanks for your interest in contributing. This document covers the essentials.

REPORTING ISSUES

Open an issue on GitHub with a clear title and description. Include steps to reproduce the problem, expected behavior, and actual behavior. Mention your Node.js version and operating system.

DEVELOPMENT WORKFLOW

1. Fork the repository
2. Clone your fork locally
3. Create a feature branch from `master`
4. Make your changes
5. Test your changes manually by running `node bin/publish.js help`
6. Commit with a clear message describing what changed and why
7. Push your branch and open a pull request against `master`

Keep pull requests focused on a single change. If you have multiple unrelated fixes, submit them as separate pull requests.

CODE STYLE

- Use plain Node.js conventions
- Prefer async/await over raw promises
- Keep functions small and focused
- Add comments only when the code is not self-explanatory

TESTING

Run the CLI locally to verify your changes:

```bash
node bin/publish.js help
node bin/publish.js validate ./path-to-extension
```

Automated tests run on every push and pull request via GitHub Actions.

LICENSE

By contributing, you agree that your contributions will be licensed under the MIT License that covers this project. See [LICENSE](LICENSE) for the full text.

---

Built by [Zovo](https://zovo.one)
