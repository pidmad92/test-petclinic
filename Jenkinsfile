pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'jagent-maven:3.8.3-jdk11'
                    reuseNode true
                }
            }
            steps {
                sh 'mvn --version'
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage('Test') {
            agent {
                docker {
                    image 'jagent-maven:3.8.3-jdk11'
                    reuseNode true
                }
            }
            steps {
                sh 'mvn test -Dtest -DfailIfNoTests=false '
            }
        }
    }
}