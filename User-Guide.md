## Code templates
Write Spring code with templates, available via regular code completion.

### Examples
* `@GetMapping`
* `@PostMapping`
* `@PutMapping`
* `@RequestMapping`

## Smart code completions
Additional code completions for Spring-specific annotations

[[/images/screenshot-code-completion.png|Smart code completion for boot properties]]

### Examples
* `@Value`: code completion for Spring Boot property keys
* `@Scope`: code completion for standard scope names

## Boot dashboard
Well known from previous generations of the Spring Tool Suite, the Spring Tool Suite 4 also contains the boot dashboard for quickly running, re-starting, tagging, and inspecting Spring Boot projects in your workspace.

[[/images/screenshot-dashboard.png|Boot Dashboard in Eclipse]]

Please note, that this is available for Eclipse only, not yet for Visual Studio Code or Atom.

## Additional enhanced editing support
In addition to pure Spring Boot app code, the tools also come with enhanced editing support for:
* Cloud Foundry Manifest files
* Concourse CI pipeline definitions
* BOSH deployment manifests

## Additional notes about background processes
The Spring Tools 4 run as extensions for VSCode, Atom, and Eclipse as so called "language-servers" in their own processes. Those processes are created as soon as the client (the editor or IDE) detects a situation where the extension can be useful and kicks-off that additional process. This has a number of benefits (a crashing extension can't crash the editor or the IDE).

The total number of processes that are being created depends on the client. VSCode usually starts just one language server process per workspace window for each language server type. The Eclipse integration behaves in a similar way. The processes can be found via `jps`, since they are all JVM processes, usually called `JarLauncher` (since we deploy and start them as Spring Boot Fat-JAR libs).
