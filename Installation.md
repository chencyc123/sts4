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

* Download the VSIX package from here: http://dist.springsource.com/snapshot/STS4/nightly-distributions.html
  * **Spring Boot Java Language Server**: Provides support for working with java-based Spring Boot applications

  * Additional extensions for Visual Studio Code:
    * Spring Boot Property Language Server: Provides support for editing Spring Boot property and yml files
    * Cloud Foundry Manifest Language Server: basic editing support for Cloud Foundry manifest files (manifest.yml)
    * Concourse CI Language Server: basic editing support for pipeline and task definitions for the Concourse CI system
    * Bosh Language Server: basic editing support for BOSH deployment manifest files
* Select `Command Palette...` from the `View` (or Press Cmd-Shift-P)
* Search for `Install from VSIX` and execute that
* Select the downloaded `vscode-boot-java...vsix` file
* Re-open the VSCode window after successful install

## Atom

Download and Install Atom 1.21 or 1.22.beta.2
* [Atom](http://atom.io)

Atom packages can be installed through `Atom -> Preferences` - on `Settings` window, select `Install`.

Then from the Spring Team:
- boot-java
- boot-properties

Optionally:
- bosh-yaml
- concourse-pipeline-yaml
- cf-manifest-yaml

It is possible to install dev builds of these packages as follows:
* Grab the latest Atom packages from here: http://dist.springsource.com/snapshot/STS4/nightly-distributions.html
* Unpack each Atom package into a different folder
* An Atom package is similar to NPM package and has `package.json` file in it. Run `apm link .` CLI command from each Atom package folder - the folder should have `package.json` file in it (or `apm-beta link .` for Atom beta version)
* Either open Atom or execute `Reload Window` command if it's opened (`Packages -> Command Palette -> Toggle`)
* Verify that package is installed in `Atom -> Preferences` `Packages` tab, i.e. listed in the list of installed packages
