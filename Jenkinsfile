pipeline {

    agent any

    stages {

        stage('Clean') {
            steps {
                sh 'rm -f student student.tar'
            }
        }

        stage('Build') {
            steps {
                sh 'gcc student.c -o student'
            }
        }

        stage('Test') {
            steps {
                sh './student'
            }
        }

        stage('Package') {
            steps {
                sh 'tar -cvf student.tar student'
            }
        }

    }

    post {

        success {
            echo 'Pipeline completed successfully'
        }

        failure {
            echo 'Pipeline failed'
        }

    }

}
