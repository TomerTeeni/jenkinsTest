@Library("tomer-groovy-shared-libary") _

pipeline {
    agent any
        parameters {
                string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

                text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

                booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

                choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

                password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
            }
    stages {
        stage('Build') {
            steps {
                sourceControl()
                sh 'printenv'
            }
        }
        stage('Test') {
            steps {
             
                 echo "buildNumber ${env.BUILD_NUMBER}"

                echo "Biography: ${env.GIT_COMMIT}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${env.GIT_AUTHOR_NAME}"

                echo "Password: ${params.PASSWORD}"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
               
            }
        }
    }
}