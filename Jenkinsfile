pipeline {
    // so you can override later
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
            agent any
            environment {
                SUPER_SECRET = 'blah'
            }

            steps {
                //input 'Do you want to deploy to stage?'
                echo "The password is: ${SUPER_SECRET}"
            }
        }
    }
}
