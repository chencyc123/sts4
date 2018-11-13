### What will happen to the old STS 3.9.x tooling?
We will continue to ship updates for STS 3.9.x as a full distribution until mid of 2019 and will update the distribution to the upcoming Eclipse releases (2018-09, 2018-12, and beyond). In case you still need important parts of the old tooling in Eclipse that haven’t been supported in Spring Tools 4 for Eclipse, you will be able to install those parts as add-on features into the Spring Tools 4 Eclipse distribution and those parts will continue to receive maintenance updates until mid of 2019. After mid of 2019, the old STS 3.9.x tooling will receive no maintenance updates anymore.

### Are the Spring Tools 4 ready for Boot 2.1 and Spring Framework 5.1?
Yes, the Spring Tools 4 are ready for usage with various Spring Boot versions (including 1.5.x, 2.0.x and 2.1.x) as well as the latest Spring Framework versions (including 4.x and 5.x).

### Do the Spring Tools 4 include Java language support?
The ready-to-use Spring Tools 4 distribution on top of Eclipse includes the standard Java language tooling of Eclipse out-of-the-box. For Visual Studio Code, you should install the Java Extension Pack, which is a combination of the regular Java language tooling (provided from RedHat and Eclipse) and the launching, testing, and debugging support for Java for Visual Studio Code (from Microsoft). For Atom, there is also a Java extension around (that is based on the same code as the Java support for Visual Studio Code).

### Do the Spring Tools 4 support JDK9 and JDK10?
Yes. You can use JDK 8/9/10 to run your Spring Tools 4 as well as use those language JDK and corresponding language versions in your projects.

### Do the Spring Tools 4 support Lombok?
Yes, you can use Lombok in your projects when using the Spring Tools 4 in the various environments.

### Can I install and use Spring Tools 4 in IntelliJ IDEA?
No. We implemented a prototype to integrate the Spring Tools 4 with IntelliJ IDEA, but the third-party support for the language server protocol for IntelliJ isn’t mature, stable, and feature-rich enough to implement a meaningful version of the Spring Tools 4 for IntelliJ yet. However, there is awesome support for Spring available out-of-the-box in the IntelliJ Ultimate Edition that you can use instead if you prefer IntelliJ.

### Which other IDEs and editors will be supported in the future?
We don’t have exact plans yet, but we constantly monitoring the language server community for new and emerging clients and environments that might be good candidates for the Spring Tools 4. Eclipse Theia is one of the projects we are taking into account at the moment, for example.

### Why does STS start additional background processes?
The Spring Tools 4 run as extensions for VSCode, Atom, and Eclipse as so called "language-servers" in their own processes. Those processes are created as soon as the client (the editor or IDE) detects a situation where the extension can be useful and kicks-off that additional process. This has a number of benefits (a crashing extension can't crash the editor or the IDE).

The total number of processes that are being created depends on the client. VSCode usually starts just one language server process per workspace window for each language server type. The Eclipse integration behaves in a similar way. The processes can be found via `jps`, since they are all JVM processes. The name of the process will be something like '${server-type}-language-server-${version}.jar'.

### I can't find a server adapter for Apache Tomcat anymore. What happened?
If you install a fresh and ready-to-use STS 4.0.1 distribution, the Apache Tomcat server adapters are included by default again. If you have an older version of STS4 installed, it doesn't contain those adapters out of the box, since we tried to reduce the overall size of the distribution for various reasons (reduced startup time, reduced size, etc.). If you want to get the Apache Tomcat server adaptors back, you can install the `JST Server Adaptor` features from the main Eclipse 2018-09 p2 repository via Install `New Software`, select the main Eclipse update site (the right one depends on the base Eclipse version that you have, but it will show up in the drop-down list for you, either the Eclipse Photon one or the Eclipse 2018-09 one), scroll down the list, expand the `Web` category, and select the `JST Server Adaptor` features.

### Where is my nice editor for JSP files gone?
As with the Apache Tomcat server adapters, we don't include everything by default in the distribution anymore, especially those pieces that we think the majority of our users don't need. But our assumptions might be wrong from time to time, so please continue to let us know what else you are missing. The JSP editing support is one of those features. But you can get it back into your STS4 via `Install New Software`, select the 2018-09 p2 repository, and check the `Eclipse Java Web Developer Tools`, they will bring you the JSP editing back.
