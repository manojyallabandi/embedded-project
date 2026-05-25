pipeline {

    agent any

    stages {

        stage('Clean') {
            steps {
                sh 'rm -f math math.tar'
            }
        }

        stage('Build') {
            steps {
                sh 'gcc math.c -o math'
            }
        }

        stage('Test') {
            steps {
                sh './math'
            }
        }

        stage('Package') {
            steps {
                sh 'tar -cvf math.tar math'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'math.tar'
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
