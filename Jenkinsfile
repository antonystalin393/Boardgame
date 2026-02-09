pipeline {
    agent any
    
    tools {
        jdk 'jdk11'
        maven 'maven3.6'
    }
    
    stages {   
        stage('Compile') {
            steps {
            sh 'mvn compile'
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        
        stage('CONFIGURE') {
            steps {
                sh 'mvn deploy'
            }
        }
    }
}
