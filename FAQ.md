## Why does STS start additional background processes?

The Spring Tools 4 run as extensions for VSCode, Atom, and Eclipse as so called "language-servers" in their own processes. Those processes are created as soon as the client (the editor or IDE) detects a situation where the extension can be useful and kicks-off that additional process. This has a number of benefits (a crashing extension can't crash the editor or the IDE).

The total number of processes that are being created depends on the client. VSCode usually starts just one language server process per workspace window for each language server type. The Eclipse integration behaves in a similar way. The processes can be found via `jps`, since they are all JVM processes. The name of the process will be something like '${server-type}-language-server-${version}.jar'.
