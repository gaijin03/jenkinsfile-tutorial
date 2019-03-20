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
                //script {
                //    def varName = 
                //}
                input 'Do you want to deploy to stage?'
            }
        }

        stage('parallel') {
            parallel {
                stage('test1') {
                    agent any
                    steps {
                        sh 'sleep 20'
                    }
                }
                stage('test2') {
                    agent any
                    steps {
                        sh 'sleep 20'
                    }
                }
            }
        }

        stage('variable') {
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
