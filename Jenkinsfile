@Library("tomer-groovy-shared-libary") _

pipeline {
    agent any
       parameters {
              string(name: 'projectName', defaultValue: 'testJenkis', description: 'test')
       }
  //  triggers { pollSCM('* * * * *') }
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
                packArtifact(name:"${params.projectName}");
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