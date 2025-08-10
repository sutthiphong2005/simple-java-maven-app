pipeline {
    agent {
        docker {
            image 'maven:4.0.0-eclipse-temurin-21'          
        }
    }
    
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
