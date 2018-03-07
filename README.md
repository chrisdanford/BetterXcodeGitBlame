# BetterXcodeGitBlame

![Preview of how Xcode's blame view changes](https://raw.githubusercontent.com/chrisdanford/BetterXcodeGitBlame/master/docs/example.gif "Example of how Xcode's blame view changes")

## Installation

*Warning*: This script modifies the conents of the Xcode package to wrap Xcode's internal version of git.  If you upgrade Xcode, you will need to re-run this script to restore functionality.

```bash
sudo bash <(curl -s https://raw.githubusercontent.com/chrisdanford/BetterXcodeGitBlame/master/install)
```

## Overview

Xcode's "blame" view is extremely handy.  For each line of a file, you can view the latest commit that modified that line.

However, Xcode exposes no options to control what flags are passed to the `git blame` command, and it's hard-coded to point to an internally-bundled version of git.

This installation script modified the Xcode-internal version to be wrapped by a shell script that passes some additional options to the `git blame` command:
- `-w` to ignore whitespace-only changes
- `-M` to ignore changes that only moved but didn't modify a line

## Uninstallation

```bash
sudo mv -f /Applications/Xcode.app/Contents/Developer/usr/bin/xcode-git /Applications/Xcode.app/Contents/Developer/usr/bin/git
```

## Authors
- [Chris Danford](https://github.com/chrisdanford)

## License

Copyright 2016-2018 Pinterest, Inc

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
