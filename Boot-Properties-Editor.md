This describes the Eclipse-based editor support for editing Spring Boot properties files in either `.properties` 
or `.yml` format.

Note that similar support is also provided for vscode and atom. For documentation on vscode/atom support 
please refer to [vscode marketplace entry](https://marketplace.visualstudio.com/items?itemName=Pivotal.vscode-spring-boot) or [atom package repository entry](https://atom.io/packages/spring-boot) instead.

# Usage:

The Boot properties/yml editor will automatically be used when you edit files with name `application.yml` or `application.properties`. Due to limitations in Eclipse's content-type framework, files with other names like `application-production.properties` will not be automatically opened with the Spring Boot Properties Editor.

There is a somewhat clunky workaround for this limitation:

- Open Eclipse Preferences and Search for **Content Types**.
- Select the **Spring Properties File** or **Spring Yaml Properties File** content type.
- In the **File Associations** section click the **Add** button.
- Enter the name of your file **without path** exactly (glob patterns or paths are not supported). For example `application-custom-profile.properties`.
- Click **Apply and Close** button.

[[/images/editor-customize-content-type.png|Customize Editor Content Types]]

From now on files with the name `application-custom-profile.properties` will be opened with
the Spring Boot Editor.

# Functionality

STS analyzes your project's classpath and parses and indexes any [Spring Boot
Properties Metadata](https://docs.spring.io/spring-boot/docs/current/reference/html/configuration-metadata.html) it finds. Both Maven and Gradle projects are supported.

The data in the index is used to provide validation, code completions and information
hovers while editing Spring Boot Properties in either `.properties` or `.yml` format.

## Validation

![application-yaml-validation][yaml-validation]
![application-properties-validation][properties-validation]

## Code Completions

![application-yaml-completions][yaml-completion]

[[/images/editor-boot-properties-validation.png|properties-completion]

## Information Hovers

![application-yaml-hovers][yaml-hovers]

## Issues and Feature Requests

Please report bugs, issues and feature requests on the [Github STS4 issue tracker](https://github.com/spring-projects/sts4/issues). 

# Releases:

Released versions of this extension can be installed directly from the vscode marketplace.

There are also development snapshots available with the latest fixes and improvements as a `.vsix` file 
that can be donwloaded from 
[here](http://dist.springsource.com/snapshot/STS4/nightly-distributions.html). To install it
open vscode, press `CTRL-SHIFT-P` and search for VSIX, then select `Extension: Install from VSIX`

[yaml-completion]: https://github.com/spring-projects/sts4/raw/5360ae4fabf9245da58f5897c54e9a14786d0622/vscode-extensions/vscode-boot-properties/readme-imgs/yaml-completion.png
[properties-completion]: https://github.com/spring-projects/sts4/raw/5360ae4fabf9245da58f5897c54e9a14786d0622/vscode-extensions/vscode-boot-properties/readme-imgs/properties-completion.png
[yaml-validation]: https://github.com/spring-projects/sts4/raw/5360ae4fabf9245da58f5897c54e9a14786d0622/vscode-extensions/vscode-boot-properties/readme-imgs/yaml-validation.png
[properties-validation]: https://github.com/spring-projects/sts4/raw/5360ae4fabf9245da58f5897c54e9a14786d0622/vscode-extensions/vscode-boot-properties/readme-imgs/properties-validation.png
[yaml-hovers]: https://github.com/spring-projects/sts4/raw/1d731ed1ad5c8defcca4e4abb3cf5f2d89daba43/vscode-extensions/vscode-boot-properties/readme-imgs/yaml-hover.png
[java-code-completion]: https://github.com/spring-projects/sts4/raw/facac2003191bc29bf79049aa02a091457ffbe47/vscode-extensions/vscode-spring-boot/readme-imgs/java-code-completion.png
[java-live-apps-quick-access]: https://github.com/spring-projects/sts4/raw/facac2003191bc29bf79049aa02a091457ffbe47/vscode-extensions/vscode-spring-boot/readme-imgs/java-live-apps-quick-access.png
[java-live-hovers]: https://github.com/spring-projects/sts4/raw/facac2003191bc29bf79049aa02a091457ffbe47/vscode-extensions/vscode-spring-boot/readme-imgs/java-live-hovers.png
[java-navigation]: https://github.com/spring-projects/sts4/raw/facac2003191bc29bf79049aa02a091457ffbe47/vscode-extensions/vscode-spring-boot/readme-imgs/java-navigation.png
