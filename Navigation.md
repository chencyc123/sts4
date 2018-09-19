# Go to symbol in file/workspace

Easy navigation to Spring-specific elements of your source code.

[[/images/symbols-nav-eclipse.png|Go to Symbol in Workspace]]

## Shortcuts
* Eclipse: Cmd-6 (symbols in file), Cmd-6 again (symbols in workspace)
* Code: Cmd-Shift-O (symbols in file), Cmd-T (symbols in workspace)
* Atom: not available yet (symbols in file show up in outline view)

Use Ctrl on windows/linux in place of Cmd key.

## Annotations
All Spring annotations from the source code in the workspace are in the list of symbols. They are prefixed with `@` as the other Spring symbols. It is best to type a specific annotation such as `@Autowired` in the search box to narrow down the list of symbols to specific type of annotation being searched for.
The annotation synbol entry in the list consits of:
- Annotation label (i.e. `@Autowired`, `@Qualifier` etc.)
- Path to the resource containing the annotation symbol

[[/images/annotation-symbol-nav-eclipse.png|Annotation symbol from list of symbols]]

Clicking on the annotation entry in the list navigates to the position in the source code resource where the annotation is located

## Beans
All Beans symbols are prefixed with `@+`. Typing `@+` is the search box lists only Bean symbols defined in the source code.

A common bean entry defined with an annotation consists of:
- Bean ID
- Annotation label including annotation "Meta Inheritance Relationship", i.e. any Controller is a Component
- Path to the resource containing the bean definition

[[/images/bean-symbol-nav-eclipse.png|Bean symbol from list of symbols]]

There are bean definitions without annotations such as Spring Data Repository beans. These consist of:
- Bean ID
- Type of model objects stored by the repository and Java type of the repository
- Path to the resource containing the bean definition

[[/images/repo-bean-symbol-nav-eclipse.png|Repository bean symbol from list of symbols]]

Clicking on the bean entry in the list navigates to the position in the source code resource where the bean is defined.

## Request Mappings
All Request Mapping symbols are prefixed with `@/`. Typing `@/` in the search box lists only Request Mapping symbols.

A common Request Mapping symbol entry consists of:
- Path of the Request Mapping
- Type of the RequestMapping or content type or other auxiliary data if applicable
- Path to the resource containing the bean definition

[[/images/rm-symbol-nav-eclipse.png|Request Mapping symbol from list of symbols]]

Clicking on the Request Mapping entry in the list navigates to the position in the source code resource where the Request Mapping is defined.

## Functions (experimental)

* `@>` shows the functional beans (see the [[Spring Cloud Function|https://cloud.spring.io/spring-cloud-function/]] project)

## Examples
* `@/` shows all defined request mappings (mapped path, request method, source location)
* `@+` shows all defined beans (bean name, bean type, source location)
* `@>` shows all functions (prototype implementation)
* `@` shows all Spring annotations in the code
* `//` shows all request mappings of all running Spring Boot apps and opens a browser for the selected endpoint

[[/images/live-rm-symbol-nav-eclipse.png|Live Request Mapping symbols]]

