## Known limitations

* Multi-root workspaces not yet supported
  * in VSCode, you can open multiple folders (so-called roots) in your workspace
  * this is not yet supported by the Spring Boot extension for VSCode
  * if you have a multi-module maven project, for example, you can open the root folder of your projects (instead of each project individually) and the Spring Boot extension will recognize the individual projects inside and provide support for them

* Scalability (specific to running in Eclipse):
  * the tooling is not yet optimized to work well with larger workspaces, especially for many open files from many different projects. This limitation is specific to the Eclipse/Spring Tool Suite 4 environment.

* JDK9:
  * the Eclipse distribution comes with coding support for JDK9, but the Spring tooling in the background doesn't fully handle JDK9 source code yet
  * also running on top of a JDK9 (have JAVA_HOME set to a JDK9) can cause issues, we suggest to run on JDK8 for now.

