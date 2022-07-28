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
             
                 sh(returnStdout: true, script: "git log -1 --pretty=%B").trim()
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}