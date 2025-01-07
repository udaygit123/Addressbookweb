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
            stage('Deploy on contanier'){
                steps{
                deploy adapters: [tomcat9(credentialsId: '9c723133-b099-424b-8bf6-87a8555c6175', path: '', url: 'http://54.224.11.0:8081/')], contextPath: null, war: '**/*.war'
        }
       }
}}
