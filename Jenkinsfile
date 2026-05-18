pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh 'gcc hello_world.c -o hello'
            }
        }

        stage('Run') {
            steps {
                sh './hello'
            }
        }

    }
}
