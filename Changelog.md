## 2018-01-29

* _(Spring Boot Java)_ function declarations are now being parsed into symbols for functions that directly inherit from `java.util.Function` ([#18](https://github.com/spring-projects/sts4/issues/18))
* _(Spring Boot Java)_ updated live hover mechanics to work with latest Spring Boot 2.0 snapshot versions 
* _(Spring Boot Java)_ improved warning message about missing tools.jar
* _(Spring Boot Java)_ live hovers now show up on class flies that are displayed as source
* _(Spring Boot Java)_ reduced number of threads used behind the scenes
* _(Spring Boot Java)_ reduced number of CPU cycles used by live hover mechanism
* _(Spring Boot Java)_ fixed a deadlock issue
* _(Spring Boot Java)_ fixed a problem with outdated symbols showing up after file deletion/rename
* _(Spring Boot Java, Spring Boot Properties)_ reduced memory footprint
* _(Spring Boot Properties)_ fixed an issue with wrong indentation after inserting property node
* _(Eclipse Integration)_ updated distribution to be based on early milestones of Eclipse Photon
* _(Eclipse Integration)_ improved goto symbol in file/workspace dialog
* _(Eclipse Integration)_ validation and quickfix support for ConfigurationProperties from STS3 added to STS4
* _(Eclipse Integration)_ fixed an issue with the Spring Starter wizard on Eclipse Photon
* _(Concourse)_ added support for cache attribute in tasks
* _(Concourse)_ added missing version attribute in image_resource
* _(Concourse)_ added support for cache attribute in tasks
* _(Concourse)_ added support for cache attribute in tasks
* _(Concourse)_ added support for cache attribute in tasks

## 2017-12-15

* _(all)_ issues solved when running on Windows ([#25](https://github.com/spring-projects/sts4/issues/25), [#26](https://github.com/spring-projects/sts4/issues/26), [#29](https://github.com/spring-projects/sts4/issues/29))
* _(Spring Boot Java)_ live hover information now works for inner classes
* _(Spring Boot Properties)_ boot property editing now activated for bootstrap*.yml files in VSCode automatically
* _(Concourse)_ getstep.version property in concourse pipeline now accepts a Map<String,String> ([#24](https://github.com/spring-projects/sts4/issues/24)) as well as special values 'every' and 'latest' ([#28](https://github.com/spring-projects/sts4/issues/28)). 

## 2017-12-04

* initial public beta launch
