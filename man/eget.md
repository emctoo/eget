---
title: eget
section: 1
header: Eget Manual
---

# NAME
  eget - easily install prebuilt binaries from GitHub

# SYNOPSIS
  eget `[--version] [--help] [OPTIONS] REPO`

# DESCRIPTION
  Eget is a tool for downloading and extracting prebuilt binaries from releases
  on GitHub. To use it, provide a repository and `eget` will search through the
  assets from the latest release in an attempt to find a suitable prebuilt
  binary for your system. If one is found, the asset will be downloaded and
  `eget` will extract the binary to the current directory. eget should only be
  used for installing simple, static prebuilt binaries, where the extracted
  binary is all that is needed for installation. For more complex installation,
  you may use the `--download-only` option, and perform extraction manually.

  The behavior of eget is configurable in a number of ways via options.
  Documentation for these options is provided below.

# OPTIONS
  `-t, --tag=`

:    Use the given tagged release instead of the latest release. Example: **`eget -t nightly zyedidia/micro`**.

  `--to=`

:    Extract the executable to the given directory. Example: **`eget zyedidia/micro --to /usr/local/bin`**.

  `-s, --system=`

:    Use the given system as the target instead of the host. Systems follow the notation 'OS/Arch', where OS is a valid OS (darwin, windows, linux, netbsd, openbsd, freebsd, android, illumos, solaris, plan9), and Arch is a valid architecture (amd64, 386, arm, arm64, riscv64). If the special value **all** is used, all possibilities are given and the user must select manually. Example: **`eget -s darwin/amd64 zyedidia/micro`**.

  `-f, --file=`

:    Extract the file with the given filename. You may want use this option to extract non-binary files. Example: **`eget -f LICENSE zyedidia/micro`**.

  `-q, --quiet`

:    Only print essential output.

  `--download-only`

:    Stop after downloading the asset. This prevents eget from performing extraction, allowing you to perform manual installation after the asset is downloaded.

  `--url`

:    Download using a direct URL rather than auto-detecting a release from GitHub. Example **`eget --url https://github.com/zyedidia/micro/releases/download/v2.0.10/micro-2.0.10-linux64.tar.gz`**.

  `--asset=`

:    Download a specific asset. Example: **`eget --asset nvim.appimage neovim/neovim`**.

  `--rename=`

:    Rename extracted file to given name. Example: **`eget --asset nvim.appimage --rename nvim neovim/neovim`**.

  `-x`

:    Force the extracted file to be executable. Example: **`eget -x --asset nvim.appimage neovim/neovim`**.

  `--sha256`

:    Show the SHA-256 hash of the downloaded asset. This can be used to verify that the asset is not corrupted.

  `-v, --version`

:    Show version information.

  `-h, --help`

:    Show a help message.

# BUGS

See GitHub Issues: <https://github.com/zyedidia/eget/issues>

# AUTHOR

Zachary Yedidia <zyedidia@gmail.com>