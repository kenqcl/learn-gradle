# Build Java Application

### Use java plugin
```gradle
apply plugin: 'java'
```

### Customize Jar
```gradle
jar {
    archiveName = 'hello-gradle.jar'

    manifest {
        attributes (
            'Main-Class': 'HelloGradle',
            'Implementation-Title': project.name,
            'Developer': 'Ken QCL'
        )
    }
}
```
