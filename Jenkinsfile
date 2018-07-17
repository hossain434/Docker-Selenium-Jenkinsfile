
def app

pipeline {

    agent any
            tools { 
        maven 'Maven 3.3.9' 
        jdk 'jdk8' 
   
    
    }
    stages {    
        stage('Build Jar') {
            steps {
                bat 'mvn clean package -DskipTests'
            }
        }
        
    stage('Build image') {

        /* This builds the actual image; synonymous to
         * docker build on the command line */

        app = docker.build("arif/test")
    }

        stage('Push Image') {

                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                        app.push("${BUILD_NUMBER}")
                        app.push("latest")
                    }
                }
            }
        }        
