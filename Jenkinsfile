pipeline {
    agent {
        docker {
            image 'maven:3.9-eclipse-temurin-24'
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
