
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
              //sh 'mvn clean package  -DskipTests'
            }
        }
    }
}

