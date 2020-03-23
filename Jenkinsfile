
pipeline {
    agent any
    tools{
        jdk 'JDK1.8'
        maven 'Maven3'
    }
    options {
        timestamps()
        buildDiscarder(logRotator(artifactDaysToKeepStr: '10', artifactNumToKeepStr: '10', daysToKeepStr: '10', numToKeepStr: '10')) 
    }
    stages {
        stage ('Display path of jeenkins'){
            steps {
        sh '''
        echo "This is declarative pipeline foor building pipeline jobs"
        echo "PATH = ${PATH}"
        ...
        }
    }
        stage ('Checkout thhe sorce code'){
            steps {
         checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '887948f7-3739-41e7-bf8c-971977673050', url: 'https://github.com/madhavsandireddi/sample-appservice.git']]])
     }

            }
stage ('Building the  source code using maven'){
        steps {
            sh 'mvn clean compile install'
        }
    }
 stage ('Archive artifacts for service app'){
        steps {
            archiveArtifacts '**/**/*.war'
    }
    }
    }
    }