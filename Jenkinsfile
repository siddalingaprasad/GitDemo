pipeline {
    agent any

    environment {
        testvariable = "custom_variable_defined"
    }

    stages {

        stage('Build') {
            steps {
                sh 'echo "this is build stage"'
                sh "echo branch name -> ${env.BRANCH_NAME}"
                sh "echo custom env variable -> ${env.testvariable}"
            }
        }

        stage('Test') {
            when {
                branch 'main'
            }
            steps {
                sh 'echo "this is test stage (runs only on main branch)"'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "this is deploy stage"'
            }
        }
    }

    post {
        always {
            sh 'echo "this is POST BLOCK for testing"'
        }
    }
}

