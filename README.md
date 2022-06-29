[![Build Status](https://travis-ci.org/Mebus/restatic.svg?branch=master)](https://travis-ci.org/Mebus/restatic)

# Restatic - A Boring Open Source GUI for Restic

:warning: :warning: ***This is a fork and I'm currently working my way though the code.*** :warning: :warning:

![](https://i.imgur.com/T5lly19.png)

Restatic is an open source Linux / Windows GUI for [Restic](https://restic.net). It's currently in very early alpha status. 

## Main features

- Encrypted, deduplicated and compressed backups.
- Works with any local or remote Restic repo. 
- Add SSH keys and initialize repos directly from the GUI.
- Repo keys are securely stored in KWallet.
- Mount existing archives via FUSE.
- Manage multiple backup profiles with different source folders, destinations and settings.
- Prune and check backups periodically.
- Flexible scheduling for automatic background backups.
- View a list of archives and action logs.
- Exclude options/patterns.

## Installation and Download
Restatic should work on all platforms that support Qt and Restic. 

### Linux / Windows
First install Restic and its [dependencies](https://restic.net/).

Please make shure that the restic binary has been added to your path.

Then install Restatic from Pypi:

```
$ git clone https://github.com/Mebus/restatic
$ cd restatic
$ pip install .
```

After installation run it with the `restatic` command.
```
$ restatic
```

## Debugging and Bugs
Please report any errors you may encounter by [opening an issue](https://github.com/Mebus/restatic/issues) on Github. Please include steps to reproduce and all logging output. Logs can be found in these folders:

- Linux: `$HOME/.cache/Restatic/log`
- macOS: `$HOME/Library/Logs/Restatic`

## Development

Install the environment in development/editable mode while in the repo:

```
mkdir venv
virtualenv-3 venv
source venv/bin/activate
pip install -r requirements-dev.txt
pip install -e .
```

Then run as Python script:
```
$ python src/restatic
```

Install developer packages we use (pytest, tox, pyinstaller):
```
pip install -r requirements-dev.txt
```

Qt Creator is used to edit views. Install from [their site](https://www.qt.io/download) or using Homebrew and then open the .ui files in `restatic/UI`:

### Testing (work in progress)

Tests are in the folder `/tests`. Testing happens at the level of UI components. Calls to `restic` are mocked and can be replaced with some example json-output. To run tests:
```
$ pytest --forked
$ pytest --flake8
```

## Authors
 - (C) 2018 Manuel Riel for [BorgBase.com](https://www.borgbase.com)
 - (C) 2018 Mebus, https://github.com/Mebus/

## License and Credits
- Licensed under GPLv3. See LICENSE.txt for details.
- Uses the excellent [Restic](https://restic.net/)
- Based on [PyQt](https://riverbankcomputing.com/software/pyqt/intro) and [Qt](https://www.qt.io).
- Icons by [FontAwesome](https://fontawesome.com)
