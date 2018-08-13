## Public beta release

This guides you through the various installation steps for the STS4 components for the public beta release. All the variants require at least a JDK8, JDK9, or JDK10 to be installed on your system as a prerequisite.

## Spring Tool Suite 4 (as Eclipse-based distribution)

Download the full featured Spring Tool Suite 4 distribution that has everything pre-installed:

* [STS4.0 M14 (Public Beta) for Windows 64bit](http://download.springsource.com/milestone/STS4/4.0.0.M14/dist/e4.9/spring-tool-suite-4-4.0.0.M14-e4.9.0-win32.win32.x86_64.zip)
* [STS4.0 M14 (Public Beta) for macOS 64bit](http://download.springsource.com/milestone/STS4/4.0.0.M14/dist/e4.9/spring-tool-suite-4-4.0.0.M14-e4.9.0-macosx.cocoa.x86_64.dmg)
* [STS4.0 M14 (Public Beta) for Linux/GTK 64bit](http://download.springsource.com/milestone/STS4/4.0.0.M14/dist/e4.9/spring-tool-suite-4-4.0.0.M14-e4.9.0-linux.gtk.x86_64.tar.gz)

Alternatively, you can install STS4 components into an existing Eclipse install:

* Choose `Install New Software` in Eclipse and use this p2 repository URL:
  * Eclipse 2018-09 (4.9): http://download.springsource.com/release/TOOLS/sts4/update/latest/
* Select the main features you wish to install and proceed.

**If you would like to try STS4 features inside of an existing STS 3.9.x installation, please open the
Spring Dashboard in STS 3.9.x, go to the Extension Install page, and select the STS4 Early Access Preview item.**

It is possible to install dev builds of these packages as from here:
* http://dist.springsource.com/snapshot/STS4/nightly-distributions.html

## Visual Studio Code

Download and install Visual Studio Code:

* [Visual Studio Code](https://code.visualstudio.com/)

Install from the Visual Studio Marketplace:
* [Java Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack)
* [Spring Boot Extension Pack](https://marketplace.visualstudio.com/items?itemName=Pivotal.vscode-boot-dev-pack)

It is possible to install dev builds of these packages as follows:
* Grab the latest VSIX packages from here: http://dist.springsource.com/snapshot/STS4/nightly-distributions.html
* Select `Command Palette...` from the `View` (or Press Cmd-Shift-P)
* Search for `Install from VSIX` and execute that
* Select the downloaded VSIX file
* Re-open the VSCode window after successful install

## Atom

Download and Install Atom 1.21 or 1.22.beta.2
* [Atom](http://atom.io)

Atom packages can be installed through `Atom -> Preferences` - on `Settings` window, select `Install`. Atom packages may prompt you to install missing prerequisite Atom packages (i.e. `ide-ui` and/or `ide-java`). It's recommended that you chose to install them.

Install the following from the Spring Team ([spring-projects](https://github.com/spring-projects)):
- **boot-java**
- **boot-properties**

Optionally :
- **bosh-yaml**
- **concourse-pipeline-yaml**
- **cf-manifest-yaml**

It is possible to install dev builds of these packages as follows:
* Grab the latest Atom packages from here: http://dist.springsource.com/snapshot/STS4/nightly-distributions.html
* Unpack each Atom package into a different folder
* An Atom package is similar to NPM package and has `package.json` file in it. Run `apm link .` CLI command from each Atom package folder - the folder should have `package.json` file in it (or `apm-beta link .` for Atom beta version)
* Either open Atom or execute `Reload Window` command if it's opened (`Packages -> Command Palette -> Toggle`)
* Verify that package is installed in `Atom -> Preferences` `Packages` tab, i.e. listed in the list of installed packages
