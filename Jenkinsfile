pipeline {
    agent {
        docker {
            image 'maven:4-eclipse-temurin-21'       
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
