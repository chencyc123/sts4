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
  * If "Live Boot Hints" not showing up when they are supposed to check if `<User-Temp-Folder>` has file `hsperf-<username>`. If yes, delete this file and restart your boot app and STS4 (Eclipse, VSCode or Atom).

* Lombok
  * The Lombok installer doesn't know about the changed name of the STS4 executable and therefore doesn't find it. Nevertheless you can install Lombok manually by modifying the SpringTools4.ini file yourself.

* Live Hovers not showing up
  * make sure the Spring Boot Actuators are on the classpath (add the Maven dependency, if necessary)
  * make sure your project is either Boot 1.5.x release or Boot 2.0.SNAPSHOT or RELEASE. Boot 2.0 MILESTONES are explicitly not supported.
  * make sure you run on a JDK, not a JRE (see above)
  * there are some network configuration cases that prevent the language server from connecting to the running Spring Boot application via JMX. In that case, add `-Djava.rmi.server.hostname=localhost` to the VM arguments when starting up your Spring Boot app.
  * On Windows... it is fairly common for the folder at `%TMP%\hsperf-%USERNAM%` to get wrong permissions, especially if you recently installed / reinstalled or updated your JDK. To fix this, simply delete the folder and restart your Boot app and STS 4 (Eclipse, VSCode or Atom). The next java process you start should recreate the folder with correct permissions.