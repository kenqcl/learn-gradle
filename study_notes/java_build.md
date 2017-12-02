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

### Change directory layout
```gradle
apply plugin: 'java'

sourceSets {
    main {
        java {
            srcDir 'source/java'
        }
    }

    test {
        java {
            srcDirs ['source/test', 'source/integration']
        }
    }
}
```

