@Library("tomer-groovy-shared-libary") _

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sourceControl()
                sh 'printenv'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}