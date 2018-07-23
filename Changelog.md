## 2018-07-23 (M13)

* _(Spring Boot)_ early prototype for detecting changed bean definitions in live-running (and restarted) boot applications
* _(Spring Boot)_ @Inject annotation now supported for live hovers
* _(Spring Boot)_ added option to match live running apps and workspace projects manually
* _(Spring Boot)_ improved JMX connector reuse (internal optimization)
* _(Concourse)_ fixed: Add support for missing attributes to `GitGetParams`, `GitPutParams`, `Job` and `Step` schemas ([#64](https://github.com/spring-projects/sts4/issues/64)), ([#65](https://github.com/spring-projects/sts4/issues/65))
* _(Concourse)_ fixed: Concourse VSCode Extension: Does not recognize GCS buckets in semver resource ([#60](https://github.com/spring-projects/sts4/issues/60))
* _(Eclipse)_ distribution updated to final Eclipse Photon release
* _(Eclipse)_ added action to close language server log console
* _(Eclipse)_ single non-signed bundle is now signed as well
* _(Eclipse)_ New Spring Starter wizard and Edit Spring Starters wizard both now display information for disabled starter modules (explains why they are disabled)
* _(Eclipse)_ fixed: Edit Starters doesn't properly handle removal of all dependencies ([#52](https://github.com/spring-projects/sts4/issues/52))
* _(Eclipse)_ fixed: Edit Starters doesn't handle cross selections well ([#52](https://github.com/spring-projects/sts4/issues/52))
* _(Eclipse)_ fixed: old language server starts up again even if not directly used
* _(Atom)_ fixed: Function.extractParams is deprecated ([#61](https://github.com/spring-projects/sts4/issues/61))
* _(Atom)_ fallback project resolution works now when running on JDK9 and beyond

## 2018-06-14 (M12)

* _(Spring Boot)_ live hovers now updated in all open editors, not just the active one
* _(Spring Boot)_ more detailed context shown in hover documentation when editing property files ([#265](https://github.com/spring-projects/spring-ide/issues/265))
* _(Spring Boot)_ performance improvement: project symbols now show up a lot faster for the open editors/projects (in a multi-root folder workspace)
* _(Spring Boot)_ bugfix: JDK9 and JDK10 projects supported now even if main editor and/or language server runs on JDK8
* _(Spring Boot)_ bugfix: various NPEs in Spring indexer fixed
* _(Spring Boot)_ bugfix: webflux route document highlights message show up for property files
* _(Concourse)_ add support for new attributes of DockerImageSource (aws_session_token, max_concurrent_downloads, max_concurrent_uploads) and DockerImagePutParams (additional_tags, cache_from, load_bases, target_name) ([#56](https://github.com/spring-projects/sts4/issues/56))
* _(Concourse)_ bugfix: quick fixes work again
* _(Eclipse)_ default editors for Boot properties (application.properties and application.yml files) now based on the generic editor and the language server support - the old editors are still around, but will be removed in future versions of STS4
* _(Eclipse)_ bugfix: filter in wizard to import Spring guides works again
* _(Eclipse)_ bugfix: fixed change event with bad version exception

## 2018-05-14 (M11)

* _(Spring Boot)_ major performance improvements and footprint reductions (due to a groundbreaking change to how projects are being resolved, this is now delegated to the surrounding Java tooling)
* _(Spring Boot)_ support for JDK10 added
* _(Spring Boot)_ bugfix - custom JMX domains now supported for live hovers ([#44](https://github.com/spring-projects/sts4/issues/44))
* _(Spring Boot)_ bugfix - live hovers now show up for all open editors (not limited to the one with focus anymore)
* _(Eclipse)_ STS4 builds on Eclipse are now based on the latest Eclipse Photon (4.8) milestone builds only, there are no 4.7-compatible builds available anymore
* _(Eclipse)_ code lenses for webflux handler methods for mapped route visualization work now in Eclipse
* _(Eclipse)_ keybindings added to Sprig Boot Dashboard
* _(Eclipse)_ property editors now show line/column numbers in status bar
* _(Eclipse)_ bugfix - debugging apps on Cloud Foundry via Boot Dashboard works again 
* _(all)_ JVM used to run the language servers can now be specified via custom settings ([#51](https://github.com/spring-projects/sts4/issues/51))

## 2018-03-15 (M10)

* _(Spring Boot)_ support added for request-mapping-like symbols for webflux router definitions
* _(Spring Boot)_ code lenses for webflux handler methods implemented that visualize the mapped route (VSCode only at the moment)
* _(Spring Boot)_ document highlight support added for webflux router definitions that highlight parts of the routes that belong together
* _(Spring Boot)_ request mapping symbols now include accept and content type defintions
* _(Spring Boot)_ support for direct navigation from live injection reports to source code added for Eclipse
* _(Spring Boot)_ abstract @Bean-annotated methods are now ignored when creating symbols for bean definitions
* _(Spring Boot)_ URLs from hovers (like request mapping URLs from running boot apps) now open in an internal browser that has a navigation and an address bar
* _(Spring Boot)_ bugfix for NPE that happened occasionally when creating a new Java file
* _(Concourse)_ added support for symbols for groups
* _(Concourse)_ updated URLs in documentation to point to new Concourse domain
* _(Atom integration)_ improved JDK/JRE identification mechanism
* _(all)_ language server processes now show up with their real name when using `jps` instead of just `JarLauncher`

## 2018-02-23 (M9)

__Attention:__ We merged the two different extensions for Spring Boot (for Java code and for properties) into a single extension for the various platforms (Eclipse, VSCode, Atom). This might require that you manually uninstall the old extensions and install the new ones. Automatic updates don't work here. For the Eclipse case, you might want to start with a fresh STS4 M9 distribution and go from there to avoid manual uninstall/install steps.

* _(Spring Boot)_ support added for Spring Data repositories, they show up as bean symbols now
* _(Spring Boot)_ fixed a bug that caused an exception when using content-assist for a non-Spring-Boot java project
* _(Spring Boot, VSCode)_ support for navigation added to live injection reports, they allow you to directly navigate to the source code of the bean type and the resource where the bean got defined. Limitation: this works for VSCode only at the moment, support for Eclipse and Atom still in progress
* _(Spring Boot, Eclipse integration)_ fixed a bug that caused content-assist to be turned off in the java editor
* _(Concourse)_ Concourse CI Pipeline Editor reports errors on valid `pipeline.yml` fixed (([#41](https://github.com/spring-projects/sts4/issues/41)))
* _(Eclipse integration)_ log output from language server processes are now streamed to the Console view, this can be disabled via the `Language Servers STS4` preference page
* _(Eclipse integration)_ individual language servers can now be easily enabled/disabled (via the `Language Servers` preference page)
* _(Eclipse integration)_ bug fix to avoid multiple language server processes being started
* _(Eclipse integration)_ bug fix to not block the Java editor from opening while starting up the language server process
* _(Eclipse integration)_ bug fix to prevent exception in the IDE when initial project got deleted
* improved the way the JDK to run the language server is found together with an improved error message if no JDK can be found

## 2018-01-30 (M8)

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

## 2017-12-15 (M7)

* _(all)_ issues solved when running on Windows ([#25](https://github.com/spring-projects/sts4/issues/25), [#26](https://github.com/spring-projects/sts4/issues/26), [#29](https://github.com/spring-projects/sts4/issues/29))
* _(Spring Boot Java)_ live hover information now works for inner classes
* _(Spring Boot Properties)_ boot property editing now activated for bootstrap*.yml files in VSCode automatically
* _(Concourse)_ getstep.version property in concourse pipeline now accepts a Map<String,String> ([#24](https://github.com/spring-projects/sts4/issues/24)) as well as special values 'every' and 'latest' ([#28](https://github.com/spring-projects/sts4/issues/28)). 

## 2017-12-04

* initial public beta launch