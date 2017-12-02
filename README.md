# Learn Gradle


## Gradle Tips

### Init new project
```bash
gradle init
```

### Set project description
```gradle
description = "Testing Gradle"

task showx << {
    println "Hello ${project.name.toUpperCase()}"
    println "$project.description"
}
```
### Change project name
Project name is in ```settings.gradle``` file

### Task dependency
```gradle
task clean {
    doLast {
        println "Do clean up"
    }
}

task compile <<{
    println "Do compile"
}
compile.dependsOn 'clean'
```
or
```gradle
task ("compile", dependsOn: 'clean') <<{
    println "Do compile"
}
```
> Note: '<<' will deprecate in Gradle 5.0. Use **doLast** instead.

### Exec command
```gradle
task dox(type: Exec) {
    commandLine 'date'
    // commondLine 'cmd', 'ver'
}
```
> Note: Only one command will be excuted

### Copy files
```gradle
task copyf(type: Copy){
    from './data.txt'
    from '../README.md'
    into 'dist'
}
```

### Delete files
```gradle
task clean(type: Delete) {
    delete 'dist', 'build'
}
```
