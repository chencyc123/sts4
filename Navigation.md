# Navigating the source code - Go to symbol in file/workspace
Easy navigation to Spring-specific elements of your source code.

[[/images/screenshot-navigation.png|Go to Symbol in workspace]]

## Shortcuts
* Eclipse: Cmd-6 (symbols in file), Cmd-6 again (symbols in workspace)
* Code: Cmd-Shift-O (symbols in file), Cmd-T (symbols in workspace)
* Atom: not available yet (symbols in file show up in outline view)

## Examples
* `@/` shows all defined request mappings (mapped path, request method, source location)
* `@+` shows all defined beans (bean name, bean type, source location)
* `@>` shows all functions (prototype implementation)
* `@` shows all Spring annotations in the code

# Quick-access for running apps

Easy navigation to the provided request mappings of running apps.

[[/images/screenshot-live-apps-quick-access.png|accessing running apps quickly]]

## Shortcuts
* Eclipse: Cmd-6 (symbols in file), Cmd-6 again (symbols in workspace)
* Code: Cmd-Shift-O (symbols in file), Cmd-T (symbols in workspace)
* Atom: not available yet (symbols in file show up in outline view)

## Examples
* `//` shows all request mappings of all running Spring Boot apps and opens a browser for the selected endpoint
