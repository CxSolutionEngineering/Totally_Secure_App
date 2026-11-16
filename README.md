# TotallySecureApp

TotallySecureApp is an intentionally vulnerable Java web application for security testing. It is built on Spring Boot and contains deliberate security flaws, so use it to exercise and evaluate security tooling such as static analysis (SAST), software composition analysis, and dynamic testing.

> **Warning:** This application is insecure by design. Never deploy it on a production system or expose it to an untrusted network. If you run it, do so in an isolated sandbox such as a VM or container.

## Origin

This project is a clone of [EasyBuggy Boot (easybuggy4sb)](https://github.com/k-tamura/easybuggy4sb), the Spring Boot edition of [EasyBuggy](https://github.com/k-tamura/easybuggy). EasyBuggy is a deliberately broken web application for understanding the behavior of bugs and vulnerabilities, such as memory leaks, deadlocks, JVM crashes, and SQL injection. See the [EasyBuggy Boot wiki](https://github.com/k-tamura/easybuggy4sb/wiki) for the original documentation.

## Vulnerabilities

The controllers under `src/main/java/org/t246osslab/easybuggy4sb/vulnerabilities` implement the following issues:

- SQL injection
- LDAP injection
- OGNL expression injection
- Code injection
- Mail header injection
- Null byte injection
- XML external entity (XXE) and XML entity expansion (XEE)
- Cross-site scripting (XSS)
- CSS injection
- Cross-site request forgery (CSRF)
- Clickjacking
- Open redirect
- Session fixation
- Brute force
- Unrestricted file upload (extension and size)
- Unintended file disclosure
- Verbose error messages
- Vulnerable OpenID Connect relying party

The application also includes the memory leak, deadlock, and JVM crash scenarios inherited from EasyBuggy, which can crash the JVM.

## Running the application

Running the application is optional, because source-code scanners need only the repository contents. If you do run it, use an isolated environment.

The project is a Maven project (see `pom.xml`). By default, the server listens on port 8080 and you can change this with the `port` property (`server.port=${port:8080}` in `src/main/resources/application.properties`).

## License and attribution

This repository does not include a license file. Refer to the [upstream EasyBuggy Boot repository](https://github.com/k-tamura/easybuggy4sb) for the licensing of the original code.
