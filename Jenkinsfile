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
             
                   wrap([$class: 'BuildUser']) {
                   sh 'echo "${BUILD_USER}"'
                  }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}