# Version Catalog

## [🏠](../../../README.md)

- You can mention the dependency in one place and can reference in `settings.gradle.kts`
- The actual version can be specified in `libs`

---
libs
```properties
guava="com.google.guava:guava:30.1.1-jre"
```

Build File 1
```kotlin
implementation(libs.guava)
```

Build File 2
```kotlin
implementation(libs.guava)
```
- The default location for the version catalog is `gradle/libs.versions.toml`
```toml
[versions]
guava = "33.5.0-jre"
junit-jupiter = "6.0.1"

[libraries]
guava = { module = "com.google.guava:guava", version.ref = "guava" }
junit-jupiter = { module = "org.junit.jupiter:junit-jupiter", version.ref = "junit-jupiter" }
```
---
There is something called as 'bundles'

`gradle/libs.versions.toml`
```toml
[bundles]
mockito=[ "mockito-core", "mockito-junit-jupiter"]
```

`build.gradle.kts`
```kotlin
testImplementation(libs.bundles.mockito)
```
---
Similar to that we can do for `plugins`

## [🏠](../../../README.md)