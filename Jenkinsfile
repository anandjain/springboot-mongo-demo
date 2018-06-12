pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "./gradlew clean build && cp build/libs/springboot-mongo-demo.jar docker/"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                sh 'cd  springboot-mongo-demo/docker/ && docker build --tag=spring-demo-1.0 .'
            }
        }
    }
}
