This section explains the relationship between STS3 and Spring Tools 4 for Eclipse (aka STS4).

## STS3 and STS4 share some features

The default Spring Tools 4 distribution for Eclipse (aka STS4) comes with several components pre-installed that you are well familiar with from using STS3. Those components/features are:

- Boot Dashboard
- Snippet Completion Proposals for Request Mappings
- Spring Properties and YAML file editing support (although the Spring Tools 4 version is slightly different)
- Conversion of Spring Properties file to YAML file
- Spring Starter wizard (https://start.spring.io)
- Import Getting Started Content wizard (https://spring.io/guides)
- Quick Search

## STS3 features not present in STS4, but have a (better) successor in Spring Tools 4

#### Request Mappings View
Open Symbol in Workspace features replaces it. Once the Open Symbol in Workspace dialog is opened type `@/` to see all Request Mappings in the workspace.

#### Live Beans Graph View
There is no graph for the Live Beans, but there is information about Live Beans available in a different form:
- Live Bean data is available via Boot highlights, hovers and Code Lenses in the source code
- List of Live beans data is shown in the Beans tab in the Properties View for a selected running Boot application

## STS3 features that are NOT present in Spring Tools 4

Since Spring Tools 4 is re-implemented from scratch, the tooling had a sharp focus for the initial release. Spring Tools 4 focus on supporting Spring developers using Spring Boot and annotation-style Spring programming. Therefore, the following features of STS3 ARE NOT supported in Spring Tools 4 anymore:

- Spring XML config support (including auto-completion for bean IDs, bean classes, etc.)#
- Spring XML config validations

## Combining STS3 and STS4

In case you would like to continue to use specific features of STS3 that are not part of STS4 yet and use the new Spring Tools 4 at the same time, you can apply two different strategies:

- use separate workspaces and continue to use STS3 for specific workspaces while using STS4 for new workspaces
- install STS3 components into an STS4 installation

### Installing STS3 into STS4

You can install the old STS3 tooling into an existing Spring Tools 4 distribution and use both side-by-side in the same workspace. This is not strongly recommended, but possible and supported.

In order to achieve that, you can use a fresh Spring Tools 4 distribution for Eclipse and go to the Eclipse Marketplace to install the "STS3 Add-On Extension" item. It will install all the well-known STS3 components into your Spring Tools 4 installation.

__This works for the Eclipse-based distribution of the Spring Tools 4 only. There is no way to install or use STS3 components in Visual Studio Code or Atom.__
