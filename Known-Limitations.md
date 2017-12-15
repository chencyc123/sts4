## Known limitations

* JDK9:
  * the Eclipse distribution comes with coding support for JDK9, but the Spring tooling in the background doesn't fully handle JDK9 source code yet
  * also running on top of a JDK9 (have JAVA_HOME set to a JDK9) can cause issues, we suggest to run on JDK8 for now.

* JDK8:
  * JDK 1.8.0_060 and above are required for some features of [Spring Boot Java Support](https://marketplace.visualstudio.com/items?itemName=Pivotal.vscode-boot-java)

* JDK required instead of a JRE
  * Some features of the tooling (e.g. the live hover information) require you to run the tooling on top of a JDK instead of a JRE. So please take care to configure your Spring Tools 4 Eclipse installation with a JDK instead of a JRE. You can find the instructions here: https://wiki.eclipse.org/Eclipse.ini
  * the same applies to the extensions for Visual Studio Code and Atom, so make sure you have your JAVA_HOME point to a JDK instead of a JRE.

* Windows
  * If "Live Boot Hints" not showing up when they are supposed to check if `<Uset-Temp-Folder>` has file `hsperf-<username>`. If yes, delete this file and restart your boot app and STS4 (Eclipse, VSCode or Atom).