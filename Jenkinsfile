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
                sh 'mkdir archive'
                sh 'echo test > archive/test.txt'
                zip zipFile: 'test.zip', archive: false, dir: 'archive'
                archiveArtifacts artifacts: 'test.zip', fingerprint: true
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
               
            }
        }
    }
   /*  post {
             always {
                 zip zipFile: "x64\\Release\\${APPLY_TAG}.zip", dir: "x64\\Release\\${APPLY_TAG}";
                    archiveArtifacts artifacts: "x64\\Release\\${APPLY_TAG}.zip", fingerprint: false, allowEmptyArchive: false, onlyIfSuccessful: true;
                      archiveArtifacts artifacts: 'dist/', onlyIfSuccessful: true
                        
                    }
                }
                */
}