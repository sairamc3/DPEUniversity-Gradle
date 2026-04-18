# Overview

## Dependency types and repositories

- **Dependency**: Library needed by a Gradle project
- Types
  - Modules
    - Can have several releases
    - Typically downloaded from repositories
  - Other Gradle project
  - File(not recommended)

## Repository

- Hosts a set of modules
  - Each module can have several releases

```kotlin
repositories {
    mavenCentral()
    maven {
        url = uri("https://..")
    }
}
```
## Module Dependency

- Module is a piece of software that evolves over time
- Typically, has multiple releases

```kotlin
dependencies {
    implementation("com.google.guava:guava:30.1.1-jre")
}
```

- `implementation` -> Configuration
- `com.google.guava:guava` -> Module ID (It's a combination of `groupId`:`artifactId`)
- `30.1.1-jre` -> version

## Dependency configurations

- Dependencies can be grouped together depending on the purpose
  - Compile dependencies
  - Runtime dependencies
  - Test dependencies
- Purposes
  - For compiling source
  - Needed during test runtime
  - For compiling tests
  - Needed during runtime

```kotlin
dependencies {
    // Use JUnit Jupiter for testing.
    testImplementation(libs.junit.jupiter)

    testRuntimeOnly("org.junit.platform:junit-platform-launcher")

    // This dependency is used by the application.
    implementation(libs.guava)
}
```
- For some predefined module ID's and versions, you can check the file `libs.versions.toml` inside the `gradle` directory
- You can check the dependencies as a group by running the gradle command
```bash
./gradlew :app:dep
```

## Dependency configuration types

- **Bucket** vs **Resolved**
  - **Bucket**: Direct dependencies that you define
  - **Resolved**: Also include transitive dependencies
    - Tasks usually use resolved dependency configurations

> when you run `dependency` task, it runs only on the current project and not in the sub-projects. There are many tasks similar to this.