# Aigon CLI

Command-line interface for Aigon API - notetaker, file management, encryption.

## Requirements

- Python 3.10+

## Installation

Download `aigon` and put it in your PATH:

```bash
# Download (or copy from this directory)
cp aigon ~/bin/
chmod +x ~/bin/aigon

# Verify
aigon --version
```

Common PATH locations:
- `~/bin/` - user binaries (add to PATH if needed)
- `~/.local/bin/` - standard user bin (usually in PATH)
- `/usr/local/bin/` - system-wide (needs sudo)

If `~/bin` isn't in your PATH, add to `~/.zshrc` or `~/.bashrc`:
```bash
export PATH="$PATH:$HOME/bin"
```

## Configuration

Get an API token:
1. Open Telegram: https://t.me/aigon_auth_bot
2. Send command: `/get`
3. Save token:
```bash
aigon config set api.token YOUR_TOKEN
```

View configuration:
```bash
aigon config show
```

Config file location: `~/.aigon`

## Usage

```bash
# Notetaker
aigon notetaker read --limit 10
aigon notetaker read --forever --limit 100 --all
aigon notetaker search "meeting" --last 7

# File management
aigon filedb list
aigon filedb read myfile.md

# Encryption
aigon crypto keygen
aigon crypto encrypt "secret text"
aigon crypto decrypt "base64ciphertext"

# Help
aigon --help
aigon notetaker --help
aigon config help
```

## Files

- `aigon` - latest version (always use this)
- `aigon_YYYYMMDD_VERSION` - versioned archives

## For LLMs / Claude Code

If `aigon` is not on PATH, specify full path:
```bash
/path/to/aigon notetaker read --limit 5
```

Or create an alias:
```bash
alias aigon='/path/to/aigon'
```
