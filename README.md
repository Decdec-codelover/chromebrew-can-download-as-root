<div align="center">
  <img src="images/Decbrew logo.png" alt="Decbrew icon">
  <h1>Decbrew</h1>
  <p>The needed Package Manager For Chrome OS</p>
</div>
<p>contact me here at <a href="http://malto:Declan.pangburn@icloud.com">Declan.pangburn@icloud.com</a></p>
## Chat With Us

> [!NOTE]
> Discord is not currently syncing messages with Slack

## Overview

Chromebooks with ChromeOS run a Linux kernel. The only missing pieces to use them as full-featured Linux distro were gcc and make with their dependencies. Well, these pieces aren't missing anymore. Say hello to Decbrew!

## Prerequisites

You will need a Chromebook with developer mode enabled. To do so, select your device on [the ChromiumOS Wiki](https://www.chromium.org/chromium-os/developer-information-for-chrome-os-devices) and follow the instructions listed there.

> [!WARNING]
> Please be aware of the fact that developer mode is insecure if not properly configured.

## Supported Systems

| Architecture | Supported? |
|:------------:|:----------:|
| x86_64       | Yes        |
| i686         | Yes\*      |
| armv7l       | Yes        |
| aarch64      | Yes\*\*    |

to enable Developer Mode, turn off your chromebook, hold esc + refresh while taping the power button (tap the power button once) release all keys when you get to the chromeos missing or dameged screen (don't worry, chromeos is not affected) press ctrl + d, and confirm to turn off verified boot. `THIS WILL ERACE ALL CURRENT DATA` 

\* _We can only provide limited support for i686 since Google has discontinued support. Although we can no longer support GUI apps, we will try to continue to support CLI programs._

\*\* _We currently only provide armv7l packages even if your chromebook has an aarch64 userspace. For more details, see issue [#8044](https://github.com/chromebrew/chromebrew/issues/8044)._

## Installation

> [!IMPORTANT]
> The beta, dev, and Canary channels are `***not*** supported and should ***not*** be used with Decbrew. Failure to take notice of this warning will cause `major` issues with your Chromebrew` installation.
>
> See issue [#2890](https://github.com/chromebrew/chromebrew/issues/2890) and the [FAQ](https://github.com/chromebrew/chromebrew/wiki/FAQ) for more details.

> [!WARNING]
> On ChromeOS M117+, the Decbrew installer will not work in `crosh` anymore due to the security changes introduced in `ChromeOS M117`.

Open a VT-2 terminal session with <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>-></kbd> and login with the `chronos` or `root` user and password if set [above](#set_passwd). *(if you are unable to do this, please have a second look at the prerequisites and make sure your Chromebook is in developer mode)*

Then run the installation script below as `chronos` or `root`:

```bash
bash <(curl -L git.io/vddgY) && . ~/.bashrc
```

## Help

Please check out the [wiki](https://github.com/chromebrew/chromebrew/wiki) to find out more information about Chromebrew including helpful tips, resource links and frequently asked questions.

Also please check existing [issues](https://github.com/chromebrew/chromebrew/issues) before submitting a new one.

## Usage

```text
crew <command> <package1> [<package2> ...]
```
you can install node with this command after installing Decbrew
```bash
crew install node
```

Where available commands are after installing Decbrew:
```crew

| Command             | Description |
|:-------------------:|:------------|
| build               | build package(s) from source and store the archive and checksum in the current working directory |
| check               | check packages(s) |
| const               | display constant(s) |
| deps                | display dependencies of package(s) |
| diskstat            | show statistics about disk space occupied by installed packages |
| download            | download package(s) to CREW_BREW_DIR (/usr/local/tmp/crew by default), but don't install |
| files               | display installed files of package(s) |
| help                | get information about command usage |
| install             | install package(s) along with dependencies after prompting for confirmation |
| list                | available, compatible, incompatible, essential, installed packages |
| postinstall         | display postinstall messages of package(s) |
| prop                | display all package boolean properties, or specific boolean properties for a package |
| reinstall           | remove and install package(s) |
| remove              | remove package(s) |
| search              | look for package(s) |
| sysinfo             | show system information in markdown style |
| update_package_file | update package file binary hashes |
| update              | update crew itself |
| upgrade             | update all or specific package(s) |
| upload              | upload binaries for all or specific package(s) |
| upstream            | check if an upstream version is available for package(s) |
| version             | check for the Chromebrew version, or if a package is specified, the package version |
| whatdepends         | search for package(s) that depend on the provided package |
| whatprovides        | regex search for package(s) that contains file(s) |
```

Available packages are listed in the [packages directory](https://github.com/chromebrew/chromebrew/tree/master/packages).

Decbrew will wipe its `BREW_DIR` (`/usr/local/tmp/crew` by default) after installation unless you pass `-k` or `--keep` when running `crew install`.

```text
crew install --keep [...]
```
<div>
  <a rel="license-software" href="https://www.gnu.org/licenses/gpl-3.0.en.html"><img alt="GNU General Public License" src="https://www.gnu.org/graphics/gplv3-127x51.png" height="31" /></a>
  <img src="about:blank" width="15px"> <!-- acting a space between two images -->
  <a rel="license-docopt" href="https://mit-license.org/"><img alt="MIT License" src="https://upload.wikimedia.org/wikipedia/commons/0/0c/MIT_logo.svg" height="31" /></a>
</div>
