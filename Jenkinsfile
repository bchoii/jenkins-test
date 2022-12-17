pipeline {
    agent none
    stages {
        stage('Build') {
            agent any
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
        stage('Test') {
            agent any
            steps {
                sh 'echo "Fail!"; exit 1'
            }
        }
        stage('Example Build') {
            agent { docker 'maven:3.8.1-adoptopenjdk-11' }
            steps {
                echo 'Hello, Maven'
                sh 'mvn --version'
            }
        }
        stage('Example Test') {
            agent { docker 'openjdk:8-jre' }
            steps {
                echo 'Hello, JDK'
                sh 'java -version'
            }
        }
    }
}
