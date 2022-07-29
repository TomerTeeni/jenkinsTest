@Library("tomer-groovy-shared-libary") _

pipeline {
    agent any
    triggers { pollSCM('* * * * *') }
    stages {
        stage('Build') {
            steps {
                 script {
                  def author = sh script: "git show -s --pretty=\"%an <%ae>\" ${GIT_COMMIT}", returnStdout: true
                 
                }
                 prepareEnv(name:author)
            }
        }
        stage('Test') {
            steps {
             
                 echo "buildNumber ${env.BUILD_NUMBER}"

                echo "Biography: ${env.GIT_COMMIT}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${env.GIT_AUTHOR_NAME}"

                echo "Password: ${params.PASSWORD}"
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