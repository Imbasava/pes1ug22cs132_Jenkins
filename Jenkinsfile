pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ -o pes1ug22cs132-1 pes1ug22cs132.cpp'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh './pes1ug22cs132-1'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    sh 'git add .'
                    sh 'git commit -m "Added working .cpp file"'
                    sh 'git push origin main'
                }
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
