pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                docker { image 'maven:3.8.3-jdk-11-alpine'
                        reuseNode true}
            }
            steps {
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage('Test') {
            agent {
                docker { image 'maven:3.8.3-jdk-11-alpine'
                         reuseNode true }
            }
            steps {
                sh 'mvn test'
            }
        }
    }
}