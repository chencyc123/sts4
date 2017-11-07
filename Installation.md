## Pre-beta internal release

This guides you through the various installation steps for the STS4 components for the internal pre-beta release. Therefore the following links point to internal CI builds, not finally released artifacts.

## Eclipse

* [Download the Spring Tool Suite 4 distribution](http://dist.springsource.com/snapshot/STS4/nightly-distributions.html), that has everything pre-installed.
* Or install into an existing Eclipse installation using:
  * for Eclipse Oxygen.1a: http://dist.springsource.com/snapshot/TOOLS/sts4/nightly/e4.7 (`Install New Software`, then enter this URL, and select the appropriate features)

**We don't recommend to install STS4 into an existing STS 3.9.x installation!!!**

## Visual Studio Code

Install from the Visual Studio Marketplace:
* [Java Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack)

Download the VSIX package (and install it into VSCode) from here:
* Spring Boot Java Language Server: http://dist.springsource.com/snapshot/STS4/nightly-distributions.html

## Atom

Download and Install Atom 1.21 or 1.22.beta.2
* [Atom](http://atom.io)

Download and Install Atom package from here:
* Page listing all packages: http://dist.springsource.com/snapshot/STS4/nightly-distributions.html
* Unpack the Atom package
* Atom package is similar to NPM package and has `package.json` file in it. Run `apm link .` CLI command from the Atom package folder (or `apm-beta link .` for Atom beta version)
* Either open Atom or execute `Reload Window` command if it's opened (`Packages -> Command Palette -> Toggle`)
* Verify that package is installed in `Atom -> Preferences` `Packages` tab, i.e. listed in the list of installed packages
