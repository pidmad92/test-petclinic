pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn --version'
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test -Dtest -DfailIfNoTests=false '
            }
        }
    }
}