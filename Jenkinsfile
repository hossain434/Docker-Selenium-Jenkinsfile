// Below Script for Windows

/*
pipeline {
  
    agent {
        node {
            label 'docker' && 'maven'
        }
    }
                tools { 
        maven 'maven' 
        jdk 'jdk'         
    
    }
    stages {    
        stage('Build Jar') {
            steps {
                bat 'mvn clean package  -DskipTests'
            }
        }
    }
}
*/

// Below Script for LINUX
pipeline {
    agent {
        node {
            label 'docker' && 'maven'
        }
    }
                      tools { 
        maven 'maven' 
        jdk 'jdk'         
    
    }
    stages {    
        stage('Build Jar') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
        stage('Build Image') {
            steps {
                script {
                      // arif/test => organization/application - it could be anything
                      app = docker.build("arif/test")
                }
            }
        }       
    }
}
