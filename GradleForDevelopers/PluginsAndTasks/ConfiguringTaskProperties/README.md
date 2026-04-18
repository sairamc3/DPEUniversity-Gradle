# Configuring task properties

# [←](../../../README.md)

## LifeCycle tasks

- Tasks that have no action, just dependent tasks
- i.e, alias for **running a group of tasks**
- Example:
  - build
  - check

## Example

```kotlin
// build.gradle.kts
tasks.named<JavaCompile>("compileJava") {
    this.options.isDebug = false
}
```

- This is to set a property during a particular task
- The property which we can set can actually be searched through official documentation

# [←](../../../README.md)