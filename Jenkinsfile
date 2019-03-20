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

        stage('Build the site') {
            agent any

            steps {
                sh 'hugo'
            }
        }

        stage('Deploy to stage?') {
            agent none

            steps {
                input 'Do you want to deploy to stage?'
            }
        }
    }
}
