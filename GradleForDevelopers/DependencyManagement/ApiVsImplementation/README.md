# API vs Implementation

## [🏠](../../../README.md)

## Most common dependency configurations

| Purpose              | Reasoning                                                        |
|----------------------|------------------------------------------------------------------|
| `testImplemetnation` | Required to compile and run tests, eg. junit libraries           |
| `runtimeOnly`        | Required when running applications, eg. specific logging library |
| `implementation`     | Internally used                                                  |
| `api`                | Public facing specification                                      |


## Implementation

| Project          | Downstream Project   |
|------------------|----------------------|
| compileClasspath | ~~compileClasspath~~ |
| rutimeClasspath  | runtimeClasspath     |


## API

| Project          | Downstream Project |
|------------------|--------------------|
| compileClasspath | compileClasspath   |
| rutimeClasspath  | runtimeClasspath   |


- API dependencies leak to downstream project `compileClasspath`
- API dependency configuration only available for library projects

## [🏠](../../../README.md)