
pipeline {
    agent any
    tools{
        jdk 'JDK1.8'
        maven 'Maven3'
    }
    options {
        timestamps()
        properties
    }
    stages {
        stage ('Display path of jeenkins')
        sh '''
        echo "This is declarative pipeline foor building pipeline jobs"
        echo "PATH = ${PATH}"
        ...
        }
    }
}
stage ('Checkout thhe sorce code')
