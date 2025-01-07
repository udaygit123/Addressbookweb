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
            deploy adapters: [tomcat9(credentialsId: 'b68d4c00-4355-4209-87eb-1d8c189034e0', path: '', url: 'http://54.81.178.92:8081/')], contextPath: null, war: '**/*.war'
           
       }
}
}}
