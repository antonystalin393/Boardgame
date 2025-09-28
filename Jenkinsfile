pipeline {
    agent any

    tools {
        jdk 'jdk17'
        maven 'maven3'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo 'this is palani from webhooktrigger'
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'main', 
                    credentialsId: 'git-credentials', 
                    url: 'https://github.com/srpalani93/Boardgame.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile -DskipTests=true'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package -DskipTests=true'
            }
        }
    }

    post {
        success {
            echo '✅ Build completed successfully!'
        }
        failure {
            echo '❌ Build failed!'
        }
        always{
            echo 'my first build always fails'
        }
    }
}
