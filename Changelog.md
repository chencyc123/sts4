## 2018-02-22

_Attention:_ We merged the two different extensions for Spring Boot (for Java code and for properties) into a single extension for the various platforms (Eclipse, VSCode, Atom). This might require that you manually uninstall the old extensions and install the new ones. Automatic updates don't work here. For the Eclipse case, you might want to start with a fresh STS4 M9 distribution and go from there to avoid manual uninstall/install steps.

* _(Spring Boot)_ support added for Spring Data repositories, they show up as bean symbols now
* _(Spring Boot)_ fixed a bug that caused an exception when using content-assist for a non-Spring-Boot java project
* _(Spring Boot, VSCode)_ support for navigation added to live injection reports, they allow you to directly navigate to the source code of the bean type and the resource where the bean got defined. Limitation: this works for VSCode only at the moment, support for Eclipse and Atom still in progress
* _(Spring Boot, Eclipse integration)_ fixed a bug that caused content-assist to be turned off in the java editor
* _(Concourse)_ Concourse CI Pipeline Editor reports errors on valid `pipeline.yml` fixed (([#41](https://github.com/spring-projects/sts4/issues/41)))
* _(general improvements)_ improved the way the JDK to run the language server is found together with an improved error message if no JDK can be found
* _(general improvements, Eclipse integration)_ log output from language server processes are now streamed to the Console view, this can be disabled via the `Language Servers STS4` preference page
* _(general improvements, Eclipse integration)_ individual language servers can now be easily enabled/disabled (via the `Language Servers` preference page
* _(general improvements, Eclipse integration)_ bug fix to avoid multiple language server processes being started
* _(general improvements, Eclipse integration)_ bug fix to not block the Java editor from opening while starting up the language server process
* _(general improvements, Eclipse integration)_ bug fix to prevent exception in the IDE when initial project got deleted





## 2018-01-30

* _(Spring Boot Java)_ function declarations are now being parsed into symbols for functions that directly inherit from `java.util.Function` ([#18](https://github.com/spring-projects/sts4/issues/18))
* _(Spring Boot Java)_ updated live hover mechanics to work with latest Spring Boot 2.0 snapshot versions 
* _(Spring Boot Java)_ improved the way the JDK (to run the language server) is found
* _(Spring Boot Java)_ improved warning message about missing tools.jar
* _(Spring Boot Java)_ live hovers now show up on class flies that are displayed as source
* _(Spring Boot Java)_ fixed a problem with outdated symbols showing up after file deletion/rename
* _(Spring Boot Java)_ fixed a deadlock issue
* _(Spring Boot Java)_ reduced number of threads used behind the scenes
* _(Spring Boot Java)_ reduced number of CPU cycles used by live hover mechanism
* _(Spring Boot Java, Spring Boot Properties)_ reduced memory footprint
* _(Spring Boot Properties)_ fixed an issue with wrong indentation after inserting property node
* _(Eclipse Integration)_ updated distribution to be based on early milestones of Eclipse Photon
* _(Eclipse Integration)_ improved goto symbol in file/workspace dialog
* _(Eclipse Integration)_ validation and quickfix support for ConfigurationProperties from STS3 added to STS4
* _(Eclipse Integration)_ fixed an issue with the Spring Starter wizard on Eclipse Photon
* _(Concourse)_ added support for cache attribute in tasks
* _(Concourse)_ added missing version attribute in image_resource

## 2017-12-15

* _(all)_ issues solved when running on Windows ([#25](https://github.com/spring-projects/sts4/issues/25), [#26](https://github.com/spring-projects/sts4/issues/26), [#29](https://github.com/spring-projects/sts4/issues/29))
* _(Spring Boot Java)_ live hover information now works for inner classes
* _(Spring Boot Properties)_ boot property editing now activated for bootstrap*.yml files in VSCode automatically
* _(Concourse)_ getstep.version property in concourse pipeline now accepts a Map<String,String> ([#24](https://github.com/spring-projects/sts4/issues/24)) as well as special values 'every' and 'latest' ([#28](https://github.com/spring-projects/sts4/issues/28)). 

## 2017-12-04

* initial public beta launch
