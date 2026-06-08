# Tech Stack

Approved technologies and pinned versions for this project. Use these versions
whenever generating build configuration, dependencies, or code. Do not introduce
other frameworks, libraries, or versions without updating this file first.

## Core

| Concern         | Technology      | Version            | Notes                                                                 |
|-----------------|-----------------|--------------------|-----------------------------------------------------------------------|
| Language / JDK  | Java (JDK)      | **21** (LTS)       | Compile and run on Java 21. Use language features through Java 21.     |
| Framework       | Spring Boot     | **3.5.x** (latest−1) | Spring Boot 4.0 is the current GA line; we stay one minor behind on 3.5.x for stability. |
| Database        | PostgreSQL      | **17.x**           | Primary relational datastore.                                         |
| DB migrations   | Flyway          | **11.x**           | All schema changes are versioned migrations under `db/migration`.     |
| Testing         | JUnit (Jupiter) | **5.x** (latest)   | JUnit 5 platform; see [.claude/rules/testing.md](../rules/testing.md). |

## Supporting

| Concern        | Technology              | Version              | Notes                                                      |
|----------------|-------------------------|----------------------|------------------------------------------------------------|
| Build tool     | Maven                   | 3.9.x (wrapper)      | Use the Maven Wrapper (`mvnw`) committed to the repo.      |
| JDBC driver    | PostgreSQL JDBC Driver  | Managed by Spring Boot | Version inherited from the Spring Boot BOM.              |
| Data access    | Spring Data JPA         | Managed by Spring Boot | Version inherited from the Spring Boot BOM.              |

## Version policy

- **Spring Boot** tracks **latest minus one minor line** — when a new minor/major
  becomes GA, the current pinned line becomes a candidate, not an automatic bump.
- **JDK** is fixed at the current LTS (**21**); do not target a newer JDK.
- **JUnit** tracks the **latest** stable 5.x release.
- Transitive versions (JDBC driver, Spring Data JPA, etc.) are managed by the
  Spring Boot dependency BOM — do not pin them explicitly unless overriding.
- Any change to a pinned version must be reflected here first, then in the build.
