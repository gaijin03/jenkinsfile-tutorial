pipeline {
    agent none
    stages {
        stage('Grab the code') {
            agent any

            steps {
		checkout scm
                sh 'echo hello world'
                sh 'ls'

            }
        }
    }
}
