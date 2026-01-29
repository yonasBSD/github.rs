<!--
SPDX-FileCopyrightText: 2025, 2026 yonasBSD

SPDX-License-Identifier: MIT
-->

# github-rs

![Linting workflow](https://github.com/yonasBSD/github-rs/actions/workflows/lint.yaml/badge.svg)
![testing workflow](https://github.com/yonasBSD/github-rs/actions/workflows/test-with-coverage.yaml/badge.svg)
![packaging](https://github.com/yonasBSD/github-rs/actions/workflows/release-packaging.yaml/badge.svg)
![cross-build](https://github.com/yonasBSD/github-rs/actions/workflows/cross-build.yaml/badge.svg)
[![codecov](https://codecov.io/gh/yonasBSD/github-rs/branch/main/graph/badge.svg?token=1R5SBEX51H)](https://codecov.io/gh/yonasBSD/github-rs)

<!--[![ghcr.io](https://img.shields.io/badge/ghcr.io-download-blue)](https://github.com/yonasBSD/github-rs/pkgs/container/github-rs)-->
<!--[![Docker Pulls](https://img.shields.io/docker/pulls/github-rs/example.svg)](https://hub.docker.com/r/github-rs/example)-->
<!--[![Quay.io](https://img.shields.io/badge/Quay.io-download-blue)](https://quay.io/repository/github-rs/example)-->

![Security Audit](https://github.com/yonasBSD/github-rs/actions/workflows/security.yaml/badge.svg)
![Scorecard Audit](https://github.com/yonasBSD/github-rs/actions/workflows/scorecard.yaml/badge.svg)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/1545c22f5f484e4ea9bf6ed4c58f0ee4)](https://app.codacy.com/gh/yonasBSD/github-rs/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=yonasBSD_github-rs&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=yonasBSD_github-rs)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=yonasBSD_github-rs&metric=security_rating)](https://sonarcloud.io/summary/new_code?id=yonasBSD_github-rs)
[![Vulnerabilities](https://sonarcloud.io/api/project_badges/measure?project=yonasBSD_github-rs&metric=vulnerabilities)](https://sonarcloud.io/summary/new_code?id=yonasBSD_github-rs)

![GitHub last commit](https://img.shields.io/github/last-commit/yonasBSD/github-rs)
[![Dependency Status](https://deps.rs/repo/github/yonasBSD/github-rs/status.svg)](https://deps.rs/repo/github/yonasBSD/github-rs)
[![GitHub Release](https://img.shields.io/github/release/yonasBSD/github-rs.svg)](https://github.com/yonasBSD/github-rs/releases/latest)
[![License](https://img.shields.io/github/license/yonasBSD/github-rs.svg)](https://github.com/yonasBSD/github-rs/blob/main/LICENSE.txt)

<!--[![Matrix Chat](https://img.shields.io/matrix/vaultwarden:matrix.org.svg?logo=matrix)](https://matrix.to/#/#vaultwarden:matrix.org)-->

A powerful Rust CLI tool to automatically update all your forked GitHub repositories, keeping them in sync with their upstream sources.

---

## 🎯 Overview

When you fork repositories on GitHub, they quickly become out of date as the upstream repositories receive new commits. `github-rs` solves this problem by automatically synchronizing all your forks with their upstream repositories, helping you maintain up-to-date copies and reduce merge conflicts.

## ✨ Features

- **Bulk Fork Updates**: Automatically update all your forked repositories in one command
- **Smart Synchronization**: Keeps your forks in sync with upstream changes
- **Conflict Detection**: Identifies potential merge conflicts before they become problems
- **Fast Performance**: Built in Rust for speed and reliability
- **GitHub API Integration**: Seamlessly integrates with GitHub's API
- **Minimal Configuration**: Simple setup with GitHub token authentication

## 📦 Installation

### From Source

```bash
git clone https://github.com/yonasBSD/github-rs.git
cd github-rs
cargo build --release
```

The binary will be available at `target/release/github-rs`.

### Using Cargo

```bash
cargo install --git https://github.com/yonasBSD/github-rs.git
```

## 🚀 Quick Start

1. **Generate a GitHub Personal Access Token**
   
   Create a token with `repo` scope at: https://github.com/settings/tokens

2. **Set Up Authentication**

   ```bash
   export GITHUB_TOKEN="your_token_here"
   ```

3. **Run the Tool**

   ```bash
   github-rs
   ```

   This will scan all your forked repositories and update them with the latest changes from their upstream sources.

## 💻 Usage

### Basic Usage

Update all your forked repositories:

```bash
github-rs
```

### Command Line Options

```bash
github-rs [OPTIONS]

Options:
  -h, --help           Print help information
  -V, --version        Print version information
```

## 🔧 Configuration

### Environment Variables

- `GITHUB_TOKEN` - Your GitHub personal access token (required)
- `GITHUB_USER` - Your GitHub username (optional, auto-detected from token)

### Token Permissions

Your GitHub token needs the following scopes:
- `repo` - Full control of private repositories
- `workflow` - Update GitHub Action workflows (if needed)

## 🏗️ How It Works

1. **Discovery**: Fetches all repositories you've forked on GitHub
2. **Analysis**: Identifies which forks are behind their upstream repositories
3. **Synchronization**: Merges upstream changes into your fork's default branch
4. **Report**: Provides a summary of updated repositories and any issues encountered

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

### Development Setup

```bash
# Clone the repository
git clone https://github.com/yonasBSD/github-rs.git
cd github-rs

# Install dependencies
cargo build

# Run tests
cargo test

# Run with cargo
cargo run
```

### Running Tests

```bash
# Run all tests
cargo test

# Run tests with coverage
cargo test --all-features

# Run linting
cargo clippy -- -D warnings

# Format code
cargo fmt
```

## 📋 Requirements

- Rust 1.70.0 or higher
- GitHub Personal Access Token with appropriate permissions
- Active internet connection

## 🔒 Security

- Never commit your GitHub token to version control
- Use environment variables or secure credential managers
- Review the [Security Policy](SECURITY.md) for reporting vulnerabilities

## 📄 License

This project is licensed under the terms specified in [LICENSE.md](LICENSE.md).

## 🙏 Acknowledgments

- Generated from [yonasBSD/rust-ci-github-actions-workflow](https://github.com/yonasBSD/rust-ci-github-actions-workflow)
- Built with the power of Rust 🦀
- Inspired by the need to keep countless forks synchronized

## 📊 Project Status

This project is actively maintained. Check the [Issues](https://github.com/yonasBSD/github-rs/issues) page for known problems and feature requests.

## 🔗 Related Projects

- [hub](https://hub.github.com/) - GitHub CLI wrapper
- [gh](https://cli.github.com/) - Official GitHub CLI
- [git-sync](https://github.com/kubernetes/git-sync) - Keep Git repos in sync

## 📞 Support

- 🐛 [Report a Bug](https://github.com/yonasBSD/github-rs/issues/new)
- 💡 [Request a Feature](https://github.com/yonasBSD/github-rs/issues/new)
- 📖 [Documentation](https://github.com/yonasBSD/github-rs)

## 📈 Changelog

See [CHANGELOG.md](CHANGELOG.md) for a list of changes and version history.

---

**Note**: This tool modifies your GitHub repositories. Always review changes before pushing to production environments. Consider testing on non-critical forks first.
