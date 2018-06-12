pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "./gradlew clean build && cp build/libs/springboot-mongo-demo.jar docker/"
            }
        }
        stage('Creating Docker Image') {
            steps {
                dir('docker/') {
                sh 'sudo docker build --tag=spring-demo-1.0 .'
		}
            }
        }
        stage('Deploying on Kubernetes') {
            steps {
                sh 'kubectl create -f kubefiles/spring-demo-rc.yaml'
                }
	    }
        }
    }
}
