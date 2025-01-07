pipeline {
    agent any
    tools {
    maven 'M2_HOME'
    }

        stages {
        stage('checkout the project from github') {
            steps {
                git branch:'master',url:'https://github.com/udaygit123/Addressbookweb.git'
                 }
          }
          stage('compile maven project') {
               steps {
               sh 'mvn clean compile'
               }
           }
           stage('Test maven project') {
               steps {
               sh 'mvn clean test'
       }
       }
            stage('package maven project') {
                steps {
                sh 'mvn package'
                }
            }

       }
}
