@Library("tomer-groovy-shared-libary") _

pipeline {
    agent any
       parameters {
              string(name: 'PROJECTNAME', defaultValue: 'testJenkis', description: 'test123')
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
                packArtifact(name:params.PROJECTNAME);
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