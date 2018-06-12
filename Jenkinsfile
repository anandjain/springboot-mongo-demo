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
        stage('Deploy') 
            steps {
                dir('/home/ubuntu/anand_git/springboot-mongo-demo/docker/') {
                sh 'docker build --tag=spring-demo-1.0 .'
            }
        }
    }
}
