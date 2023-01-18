# Prebuilt OpenSSL 3 Libs for MacOS (arm64 & x86_64)

[Download](https://github.com/0blu/prebuilt-openssl3-for-macos/releases)

## Setup Self-Hosted-Runner

If you want to build it for yourself, you want:
- `brew` for AppleSilicon (arm64) builds
- `axbrew` for Intel (x86_64) builds

Run this to get it
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

echo '# Set PATH, MANPATH, etc., for Homebrew.' >> ~/.zprofile
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"

/usr/sbin/softwareupdate --install-rosetta --agree-to-license

cd ~/Downloads
mkdir homebrew
curl -L https://github.com/Homebrew/brew/tarball/master | tar xz --strip 1 -C homebrew

sudo mv homebrew /usr/local/homebrew

echo -e '#!/bin/zsh\narch -x86_64 /usr/local/homebrew/bin/brew $@' > axbrew
chmod a+x axbrew
sudo mv axbrew /usr/local/bin/axbrew
```

⚠️ **only when all environment variables are set start the GitHub Action Runner Daemon**
