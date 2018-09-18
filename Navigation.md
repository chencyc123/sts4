# Go to symbol in file/workspace

Easy navigation to Spring-specific elements of your source code.

[[/images/workspace-symbols-eclipse.png|Go to Symbol in workspace]]

## Shortcuts
* Eclipse: Cmd-6 (symbols in file), Cmd-6 again (symbols in workspace)
* Code: Cmd-Shift-O (symbols in file), Cmd-T (symbols in workspace)
* Atom: not available yet (symbols in file show up in outline view)

## Annotations

## Beans

## Request Mappings

## Functions


## Examples
* `@/` shows all defined request mappings (mapped path, request method, source location)
* `@+` shows all defined beans (bean name, bean type, source location)
* `@>` shows all functions (prototype implementation)
* `@` shows all Spring annotations in the code
* `//` shows all request mappings of all running Spring Boot apps and opens a browser for the selected endpoint

[[/images/screenshot-live-apps-quick-access.png|accessing running apps quickly]]

