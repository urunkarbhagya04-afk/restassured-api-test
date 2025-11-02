pipeline {
    agent any

    tools {
        jdk 'JDK17'
        maven 'Maven'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/urunkarbhagya04-afk/restassured-api-test.git'
            }
        }

        stage('Build & Test') {
            steps {
                echo '🧪 Running Maven tests...'
                sh 'mvn clean test'
            }
        }
    }

    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }
        success {
            echo '✅ Build and tests completed successfully!'
        }
        failure {
            echo '❌ Build failed. Check console output for details.'
        }
    }
}

