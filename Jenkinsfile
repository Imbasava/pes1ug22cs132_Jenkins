pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'g++ pes1ug22cs132.cpp -o pes1ug22cs132-1'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh './pes1ug22cs132-1'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh '''
                git config --global user.email "imbasavanayak@gmail.com"
                git config --global user.name "imbasava"
                git add .
                git commit -m "Added working .cpp file"
                git push origin main
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed'
        }
    }
}
