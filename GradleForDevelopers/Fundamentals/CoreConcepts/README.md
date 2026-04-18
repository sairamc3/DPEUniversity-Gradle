# Introduction to Gradle for Developers

# [←](../../../README.md)

## Core Concepts
- Build Configuration
- Plugins & tasks
- Dependency Management

## Dependency Management

```mermaid
flowchart RL
    A[Your Code ] --> B[Dependencies]
    B --> C[Repositories]
    D[Transitive Dependencies] --> C[Repositories]
    B --> D
```

The code you right should be 
- Compiled
- Tested
- published

```mermaid
flowchart RL
    A[Your Code ] --> B[Dependencies]
    B --> C[Repositories]
    D[Transitive Dependencies] --> C[Repositories]
    B --> D
    
    subgraph Tasks 
        E[Compiling] --> F[Testing]
        F --> G[Publishing]
    end
    
    A --> Tasks
    Tasks --> C
```

## Gradle Build Tool Core Concepts

* Build Configuration
* Tasks
* Dependency Management
* Build Lifecycle

### Concepts

- it's an open-source build automation tool
- Automate tasks:
  - compiling
  - testing
  - publishing
- Comprehensive and flexible dependency management
  - Consistent and reproducible builds

#  [←](../../../README.md)