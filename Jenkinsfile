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
    }
}
