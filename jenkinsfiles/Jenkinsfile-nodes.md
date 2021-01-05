### This is used to build java script app
**Prerequsites**
- node plugin is required
```
pipeline {
    agent any
    environment{
        NODEJS_HOME = "${tool 'node'}"
        PATH = "${env.NODEJS_HOME}/bin:${env.PATH}"
    }
    stages{
        stage("sample"){
            steps{
                buildJavascriptApp deploy: false, {
                    send type: "email", message: "Build succeeded"
                }
            }
        }
    }
}
```
