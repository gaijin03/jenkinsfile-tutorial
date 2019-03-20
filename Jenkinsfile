pipeline {
    // so you can override later
    agent none

    options {
        skipDefaultCheckout()
    }

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
                script {
                    def varName = 
                }
                //input 'Do you want to deploy to stage?'
            }
        }

        stage('Deploy to stage?') {
            agent any
            parallel {
                stage('test1') {
                    steps {
                        sh 'sleep 20'
                    }
                }
                stage('test2') {
                    steps {
                        sh 'sleep 20'
                    }
                }
            }
        }

        stage('Deploy to stage?') {
            agent any
            environment {
                SUPER_SECRET = 'blah'
            }

            steps {
                echo "The password is: ${SUPER_SECRET}"
            }
        }
    }
}
