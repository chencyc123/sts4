STS4 automatically detects JVM processes for running boot applications on your local machine.

When a running app is detected, STS 4 automatically shows hints in the source code where data from the running app can be inspected. Then hovering over that area (with the mouse pointer), the data from the running app shows up.

For some types of information, STS 4 may also show a 'quick summary' as a codelens. Codelenses are only supported in Eclipse and Vscode at the moment, not in atom. For Eclipse this has to be enabled via *Preferences >> Language Servers >> Spring Language Servers >> Spring Boot Language Server*.

If there are multiple instances of the app running on your machine, the live data from all those instances will show up in the hover information.

[[/images/screenshot-live-hovers.png|live data from running apps as hover on source code]]

## Application Requirements

Live information is scraped from running apps using JMX to connect to [Spring Boot Actuator Endpoints](https://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-endpoints.html). This means that `spring-boot-actuator` must be added as a dependency to your application and endabled. The easiest way to accomplish this is to add the `spring-boot-actuator-starter` dependency to your application's `pom.xml` or `build.gradle` as explained [here](https://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-enabling.html).

## Live Information Details

This section provides an overview of the different types of live information that are currently
supported and how each of them can be accessed from the editor.

### Live Requestmappings

TODO fill this in
- the request mapping hovers + request mapping code lenses

### Live Bean Information

TODO fill this in:

- the bean wiring information that is shown and how that is being shown
- the bean wiring information that is shown as code lenses (with the limitation that this doesn't work in Eclipse and Atom yet)

### Conditional Beans Information

TODO fill this in
* `@ContidionalOn...`: shows information about the conditions and their evaluation at runtime

### Live Active Profiles Information

Hovering over a `@Profile` will show wich profiles are currently active in running boot applications. 
Additionally, the names of the profiles inside the annotation parameters will be highlighted, dependending on whether that specific profile is active.

[[/images/screenshot-live-hover-profiles.png|Profile Live Hover]]

## Remote Applications

TLDR; If an app is deployed to cloudfoundry using the STS 4 Eclipse Spring Boot Dashboard, JMX can be enabled when that app is depployed. Live hovers will work automaticlly for that remotely deployed application, for the workspace from which it was deployed.

### Details

Live information is scraped from actuator-enabled apps using JMX. For local apps a JMX connection can be estblished automatically and doesn't require any special actions to enable JMX. 

However, for remote apps the tools cannot automatically discover the process nor enable JMX support on the remote JVM. So besides needing to have actuator enabled (this is the same as for local apps) there are some additional requirements for remote apps:

- JMX must be explicitly enabled on the remote JVM when it is launched; by setting certain system properties. 
- The host and port on which the remote JMX service is running must be made accessible from the local machine somehow.
- The Editor must be explicitly configured to know where to find the remote JMX service.

There are two ways to satisfy these additional requirements. An easy automatic way (this only works for apps deployed directly from the workspace to cloudfoundry); and a more involve manual way.

### Automatic: App Deployed from Boot Dashboard

When deploying an app to Cloudfoundry there is an option near the bottom of the Deployment Dialog where you can enable JMX.

[[/images/screenshot-enable-jmx-deployment-option|Enable JMX Deployment Option]]

When that option is enabled:

- JMX is enabled on the deployed application by setting additional system properties via the `JAVA_OPTS` environment variable.
- When the app has fully started a local SSH tunnel is created, proxying the JMX service on a local port.
- The editor is configured to check that local port for live hover information.

This makes live hover information work for the remote application.

### Manual

You can also perform the above three steps manuall. This may, for example, be necessary if you don't deploy your application diretly from the workspace but use CI/CD pipeline for deployment. Here we explain the process for an app deployed to Cloudfoundry, but in principle this process can be adapted to any actuator-enabled spring-boot app, running anywhere.

**Step 1:** Enabling JMX.

This can be accomplished by adding system properties via the `JAVA_OPTS` environment variable. For example you could add this to your cf `manifest.yml`:

```
JAVA_OPTS: > 
  -Dcom.sun.management.jmxremote.ssl=false
  -Dcom.sun.management.jmxremote.authenticate=false 
  -Dcom.sun.management.jmxremote.port=33333 
  -Dcom.sun.management.jmxremote.rmi.port=33333 
  -Djava.rmi.server.hostname=localhost 
  -Dcom.sun.management.jmxremote.local.only=false

```

**Step 2:** Creating an SSH tunnel

You can use the CF CLI to create a tunnel to the deployed app. For example:

```
$ cf ssh my-app-name -L 33333:localhost:33333
```

This will create an SSH session and open a bash prompt connected to the remote app. As long as this session is left open JMX for that app can now be accessed on the local port (33333 in the example). You can verify that this worked correctly by attempting to connect to the remote with a tool like jconsole using command `jconsole localhost:33333`.

**Step 3: Configure the Editor

The final step differs slighty depending on the Editor you are using (Eclipse / Vscode / Atom). But each of the editors are configured by pasting an identical json snippet into a specific setting. The snippet should look something like the following:

```
[
    {
        "jmxurl" : "service:jmx:rmi://localhost:33333/jndi/rmi://localhost:33333/jmxrmi",
        "host" : "my-app-host-for-http.cfapps.io"
    }
]
```

Note that the snippet is a json *list*, so you can configure more than one remote app at the same time.

For *Eclipse*, paste this snippet into *Preferences >> Language Servers >> Spring Language Servers >> Spring Boot Language Server >> Remote Boot Apps*.

For *Vscode*, enter it as the value for the configuration key `boot-java.remote-apps` (in either user or workspace settings).

For *Atom*, TODO alex?

## Completely Disabling this Feature

A background thread is used to periodically scrape running processes for live information. This could negatively affect your machine's performance. This feature can be completely disabled: 

* Eclipse/Spring Tool Suite 4: via the preferences `Spring -> Spring Boot Language Server`
* Code: regular JSON preference mechanism using the key: `boot-java.boot-hints.on`.
* Atom: regular preference mechanism