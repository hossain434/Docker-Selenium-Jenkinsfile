pipeline {
  
    agent {
        node {
            label 'docker' && 'maven'
        }
    }
                tools { 
        maven 'maven' 
        jdk 'jdk' 
        docker 'docker'          
    
    }
    stages {    
        stage('Build Jar') {
            steps {
                bat 'mvn clean package -DskipTests'
            }
        }
        stage('Build Image') {
            steps {
                script {
                      // grid/test => organization/application - it could be anything
                      
                    def  app = docker.build("grid/test")
                  app.push()
                }
            }
        }
        
    }
}
