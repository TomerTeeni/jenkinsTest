@Library("tomer-groovy-shared-libary") _

pipeline {
    agent any
    triggers { pollSCM('* * * * *') }
    stages {
        stage('Build') {
            steps {
                 script {
                  def author = sh script: "git show -s --pretty=\"%an <%ae>\" ${GIT_COMMIT}", returnStdout: true
                   echo "author : ${author}"
                   sourceControl()
                }
                
            }
        }
        stage('Test') {
            steps {
                script {
                  def author = sh script: "git show -s --pretty=\"%an <%ae>\" ${GIT_COMMIT}", returnStdout: true
                  echo "author : ${author}"
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