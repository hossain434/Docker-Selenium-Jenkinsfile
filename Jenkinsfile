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
                bat 'mvn clean package -DskipTests'
            }
        }
        stage('Build Image') {
            steps {
                script bat {
                      // grid/test => organization/application - it could be anything
                      
                      app = docker.build("grid/test")
                }
            }
        }
        
    }
}
