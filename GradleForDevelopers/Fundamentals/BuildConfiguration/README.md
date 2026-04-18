# Build Configuration

Topics covered include:

- Configuration Layout
  - Settings file
    - It will be present in the root directory
    - It contains
      - Root project name
      - List of sub projects
      - Some common dependencies in the sub-projects (There is other way to do it, like having a common sub-project)
  - Build files
    - it will be written in sub-projects or in root directory if there are no sub-projects
    - it contains
      - plugins
      - dependencies
      - tasks
      - source code
> The configuration can be written in `groovy` or `kotlin`. `Kotlin` is preferred since it's new and has more IDE support. 
- Using gradle init to create configuration for a new project

### Groovy

```groovy
// settings.gradle
rootProject.name = 'demo'
include('app')
```

```groovy
// app/build.gradle
plugins {
    id 'application'
}
repositories {
    mavenCentral()
}

dependencies {
    testImplementation 'org.junit.jupiter:junit-jupiter:5.8.1'
    implementation 'com.google.guava:guava:30.1.1-jre'
}
```
### Kotlin

```kotlin
// settings.gradle.kts
rootProject.name = "demo"
include("app")
```
```kotlin
// app/build.gradle.kts
plugins {
    application
}
repositories {
    mavenCentral()
}

dependencies {
    testImplementation ("org.junit.jupiter:junit-jupiter:5.8.1")
    implementation ("com.google.guava:guava:30.1.1-jre")
}
```

> You can use `gradle init` command to create configuration layout for a new project


