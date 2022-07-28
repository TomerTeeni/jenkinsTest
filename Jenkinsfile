@Library("tomer-groovy-shared-libary") _

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sourceControl()
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