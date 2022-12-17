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
    }
}
