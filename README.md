# BetterXcodeGitBlame

![Preview of how Xcode's blame view changes](https://raw.githubusercontent.com/chrisdanford/BetterXcodeGitBlame/master/docs/example.gif "Example of how Xcode's blame view changes")

*Warning*: This script modifies the conents of the Xcode package to wrap Xcode's internal version of git.

*Warning*: If you upgrade Xcode, you will need to re-run this script to restore functionality.

## Installation

```bash
bash <(curl -s https://raw.githubusercontent.com/chrisdanford/BetterXcodeGitBlame/master/install)
```

## Overview

Xcode's "blame" view is extremely handy.  For each line of a file, you can view the latest commit that modified that line.

However, Xcode exposes no options to control what flags are passed to the `git blame` command, and it's hard-coded to point to an internally-bundled version of git.

This installation script modified the Xcode-internal git to be wrapped by a shell script that passes some additional options for the `git blame` command:
- `-w` to ignore whitespace-only changes
- `-M` to ignore changes that only moved but didn't modify a line

## Advanced Usage
### Upgrading
Simply run the normal installation command, and installation will occur if the latest version is newer than the locally-installed version.

### Uninstallation
```bash
bash <(curl -s https://raw.githubusercontent.com/chrisdanford/BetterXcodeGitBlame/master/install) --uninstall
```

### Redistibuting

You may find it useful to redistribute this project and install it across multiple machines.  The `download` script and the `--local` flag to `install` aim to make this easy.

```bash
bash <(curl -s https://raw.githubusercontent.com/chrisdanford/BetterXcodeGitBlame/master/download) -- ./BetterXcodeGitBlame/

# install
./BetterXcodeGitBlame/install --local

# uninstall
./BetterXcodeGitBlame/install --uninstall
```

## Authors
- [Chris Danford](https://github.com/chrisdanford)

## License

Copyright 2018 Pinterest, Inc

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
