@Library("tomer-groovy-shared-libary") _

pipeline {
    agent any
    triggers { pollSCM('* * * * *') }
    stages {
        stage('Build') {
            steps {
                prepareEnv()
            }
        }
        
        stage('Pack') {
            steps {
                echo 'Pack'
             //  archiveArtifacts artifacts: 'build/', onlyIfSuccessful: true
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
               
            }
        }
    }
     post {
             always {
                      archiveArtifacts artifacts: 'build/', onlyIfSuccessful: true
                        
                    }
                }
}