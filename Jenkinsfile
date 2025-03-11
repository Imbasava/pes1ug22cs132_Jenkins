pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Intentional error: Referencing a nonexistent file
                    sh 'g++ -o output nonexistent_file.cpp'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './output'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline Failed ❌'
        }
    }
}
