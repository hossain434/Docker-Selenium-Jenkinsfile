pipeline {
    agent {
        node {
            label 'docker' && 'maven'
        }
    }
    stages {    
        stage('Build Jar') {
            steps {
               def mvnhome= tool name: 'maven', type: 'maven'
                bat "%{mvnhome}/bin/mvn clean package -DskipTests"
            }
        }
        stage('Build Image') {
            steps {
                script {
                      // grid/test => organization/application - it could be anything
                      app = docker.build("grid/test")
                }
            }
        }
        stage('Push Image') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                        app.push("${BUILD_NUMBER}")
                        app.push("latest")
                    }
                }
            }
        }        
    }
}
