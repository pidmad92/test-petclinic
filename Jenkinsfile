pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'maven:3.8.3-jdk-11'
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
                    image 'maven:3.8.3-jdk-11'
                    reuseNode true
                }
            }
            steps {
                sh 'mvn test -Dtest -DfailIfNoTests=false '
            }
        }
    }
}