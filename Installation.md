This guides you through the various installation steps for the STS4 components on the different supported platforms (Eclipse, Visual Studio Code and Atom). All the variants require at least a JDK8, JDK9, or JDK10 to be installed on your system as a prerequisite.

## Spring Tool Suite 4 (the Eclipse-based distribution)

Download the full featured Spring Tool Suite 4 distribution that has everything pre-installed:

* [STS4.0 M14 (Public Beta) for Windows 64bit](http://download.springsource.com/milestone/STS4/4.0.0.M14/dist/e4.9/spring-tool-suite-4-4.0.0.M14-e4.9.0-win32.win32.x86_64.zip)
* [STS4.0 M14 (Public Beta) for macOS 64bit](http://download.springsource.com/milestone/STS4/4.0.0.M14/dist/e4.9/spring-tool-suite-4-4.0.0.M14-e4.9.0-macosx.cocoa.x86_64.dmg)
* [STS4.0 M14 (Public Beta) for Linux/GTK 64bit](http://download.springsource.com/milestone/STS4/4.0.0.M14/dist/e4.9/spring-tool-suite-4-4.0.0.M14-e4.9.0-linux.gtk.x86_64.tar.gz)

Alternatively, you can install STS4 components into an existing Eclipse install. You need the latest Eclipse 2018-09 release as a prerequisite in this case (download Eclipse 2018-09 from here: https://www.eclipse.org/downloads/packages/release/2018-09/m2).

* Choose `Install New Software` in Eclipse and use this p2 repository URL:
  * http://download.springsource.com/release/TOOLS/sts4/update/latest/
* Select the main features you wish to install and proceed.

**If you would like to try STS4 features inside of an existing STS 3.9.x installation, please open the
Spring Dashboard in STS 3.9.x, go to the Extension Install page, and select the STS4 Early Access Preview item.**

## Visual Studio Code

Download and install Visual Studio Code:

* [Visual Studio Code](https://code.visualstudio.com/)

Install from the Visual Studio Marketplace:
* [Java Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack)
* [Spring Boot Extension Pack](https://marketplace.visualstudio.com/items?itemName=Pivotal.vscode-boot-dev-pack)

More detailed instructions on installing extension from Visual Studio Marketplace can be found [here](https://code.visualstudio.com/docs/editor/extension-gallery)

## Atom

Download and Install latest Atom (any version >= 1.22)
* [Atom](http://atom.io)

Atom packages can be installed through `Atom -> Preferences` - on `Settings` window, select `Install`. Atom packages may prompt you to install missing prerequisite Atom packages (i.e. `ide-ui` and/or `ide-java`). It's recommended that you choose to install them.

Install the following from the Spring Team ([spring-projects](https://github.com/spring-projects)):
- **spring-boot**
- **bosh-yaml**
- **concourse-pipeline-yaml**
- **cf-manifest-yaml**