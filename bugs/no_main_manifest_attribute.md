# no main manifest attribute in /app.jar

<details>
<summary>Index</summary>

- [no main manifest attribute in /app.jar](#no-main-manifest-attribute-in-appjar)
  - [Description](#description)
  - [Environment](#environment)
  - [Expected](#expected)
  - [Reason](#reason)
  - [Solve](#solve)

</details>

Tags: `docker`, `spring boot`, `gradle`

---

## Description

After building a Spring Boot application into a Docker image, the resulting Docker container is continuously restarting.
The container logs repeatedly display the following error message:

```
no main manifest attribute in /app.jar
```

## Environment

- MacOS: 14.6.1
- Docker Engine: 26.1.3

## Expected

SpringBoot is running on Docker.

## Reason

Invalid setting for bootJar.

```
tasks.bootJar { enabled = false }
```

## Solve

```
tasks.bootJar { enabled = true }
```
