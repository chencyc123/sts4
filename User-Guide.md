## Navigating the source code - Go to symbol in file/workspace
Easy navigation to Spring-specific elements of your source code.

(screenshot)

### Shortcuts
* Eclipse: Cmd-6 (symbols in file), Cmd-6 again (symbols in workspace)
* Code: Cmd-Shift-O (symbols in file), Cmd-T (symbols in workspace)
* Atom: not available yet (symbols in file show up in outline view)

### Examples
* `@/` shows all defined request mappings (mapped path, request method, source location)
* `@+` shows all defined beans (bean name, bean type, source location)
* `@>` shows all functions (prototype implementation)
* `@` shows all Spring annotations in the code

## Quick-access for running apps
Easy navigation to the provided request mappings of running apps.

(screenshot)

### Shortcuts
* Eclipse: Cmd-6 (symbols in file), Cmd-6 again (symbols in workspace)
* Code: Cmd-Shift-O (symbols in file), Cmd-T (symbols in workspace)
* Atom: not available yet (symbols in file show up in outline view)

### Examples
* `//` shows all request mappings of all running Spring Boot apps and opens a browser for the selected endpoint

## Live application information hovers
Show information from running Spring Boot apps on your machine in the source code. This allows you to run the Spring Boot app locally on your machine and visualizes information from those running apps in your source code.

### Visualization
Once the tooling detects a running Spring Boot app on your local machine, it automatically shows hints in the source code where data from the running app can be inspected. Then hovering over that area (with the mouse pointer), the data from the running app shows up.

If there are multiple instances of the app running on your machine, the live data from all those instances will show up in the hover information.

(screenshot)

### Examples
* `@Profile`: shows information about the active profiles on the running apps
* `@Component`, `@Bean`, `@Autowired`: shows detailed information about the beans and their wiring from the live app
* `@ContidionalOn...`: shows information about the conditions and their evaluation at runtime

### Configuration
You can enable/disable this feature:
* Eclipse/Spring Tool Suite 4: via the preferences `Spring -> Spring Boot Language Server`
* Code: regular JSON preference mechanism using the key: `boot-java.boot-hints.on`.
* Atom: regular preference mechanism

## Code templates
Write Spring code with templates, available via regular code completion.

### Examples
* `@GetMapping`
* `@PostMapping`
* `@PutMapping`
* `@RequestMapping`

## Enhanced code completions
Additional code completions for Spring-specific annotations

(screenshot)

### Examples
* `@Value`: code completion for Spring Boot property keys
* `@Scope`: code completion for standard scope names

## Boot dashboard
Well known from previous generations of the Spring Tool Suite, the Spring Tool Suite 4 also contains the boot dashboard for quickly running, re-starting, tagging, and inspecting Spring Boot projects in your workspace.

(screenshot)

Please note, that this is available for Eclipse only, not yet for Visual Studio Code or Atom.

## Additional enhanced editing support
In addition to pure Spring Boot app code, the tools also come with enhanced editing support for:
* Cloud Foundry Manifest files
* Concourse CI pipeline definitions
* BOSH deployment manifests
