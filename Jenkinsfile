@Library("tomer-groovy-shared-libary") _

pipeline {
    agent any
    triggers { pollSCM('* * * * *') }
    tools {nodejs "node"}
    stages {
        stage('Git') {
            steps {
              gitClone()
            }
       }
        stage('Build') {
            steps {
                prepareEnv()
            }
        }
        
        stage('Pack') {
            steps {
                echo 'Pack'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
               
            }
        }
    }
     /*post {
             always {
                      archiveArtifacts artifacts: 'build/', onlyIfSuccessful: true
                        
                    }
                }*/
}