pipeline {
    agent {
                tools { 
        maven 'maven' 
        jdk 'jdk'  
    }
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
                     docker.build("arif/test")
                }
            }
        }
       
    }
}

