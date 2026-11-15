# Java JSP Web Application

A guided Java web project demonstrating a JSP page, a servlet application descriptor, Maven WAR packaging and automated artifact validation. The build is portable: it uses public Maven dependencies and needs no AWS account.

| Resource | Purpose |
| --- | --- |
| [Application page](src/main/webapp/index.jsp) | Minimal, semantic HTML served as a JSP |
| [Build configuration](pom.xml) | Java 17 and explicit compiler/WAR plugin versions |
| [Architecture and operating boundaries](docs/ARCHITECTURE.md) | Build flow, runtime requirements and verification limits |
| [Learning provenance](docs/PROVENANCE.md) | NextWork learning origin, original project evidence and later maintenance |
| [CodeBuild configuration](buildspec.yml) | Optional AWS build instructions; infrastructure is configured separately |

## Build

With JDK 17+ and Maven 3.9.x installed:

```sh
mvn --batch-mode --no-transfer-progress clean verify
jar tf target/java-jsp-web-application.war
```

The output is **`target/java-jsp-web-application.war`**. The GitHub workflow checks that it contains `index.jsp` and `WEB-INF/web.xml`.

## Run

Deploy the complete WAR to a separately configured, compatible JSP/servlet container and open that application's context URL. This repository supplies the web application archive, not a container installer or an AWS deployment. Review container compatibility and configuration before use.

The current page is stateless and contains static learning content. No application API, database, authentication service, cloud provisioning or production availability claim is included. A successful build verifies packaging; it does not establish a working deployment.

## Optional private Maven mirror

Default builds do not use [settings.xml](settings.xml). If you intentionally use a private mirror, configure your own `CODEARTIFACT_MAVEN_URL` and `CODEARTIFACT_AUTH_TOKEN`, then supply `-s settings.xml`. Keep token values outside the repository.

## Learning and year

This project began through NextWork's guided Java/AWS learning work. The professional project name describes the code retained here; it does not remove that learning attribution. [Provenance](docs/PROVENANCE.md) separates the original exercise from later build and presentation maintenance.

The `2025` repository suffix records its creation year: **12 March 2025**. Naming and documentation maintenance is dated **15 November 2026**.
