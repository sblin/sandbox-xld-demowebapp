pipeline {
    agent any
    stages {
        stage('Starting') {
            steps {
                echo "Starting DemoWebApp pipeline for version ${params.VERSION}"
            }    
        }
        stage('Compiling with maven') {
            tools {
                jdk "JDK11"
            }
            steps {
                sh "mvn clean package"
            }
        }
        stage('Pushing to Deploy') {
            steps {
                sh "./xlw apply xl-deploy --xl-deploy-url http://localhost:4516 -f xebialabs/xebialabs.yaml --values appversion=${params.VERSION}"
            }
        }
    }
}