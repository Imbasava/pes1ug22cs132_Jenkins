pipeline {
    agent any
    stages {
        // stage('Clone repository') {
        //     steps {
        //         checkout([$class: 'GitSCM',
        //         branches: [[name: '*/main']],
        //         userRemoteConfigs: [[url: 'https://github.com/Imbasava/pes1ug22cs132_Jenkins.git']]])
        //     }
        // }

        stage('Build') {
            steps {
                build 'PES1UG22CS132'
                sh 'g++ PES1UG22CS132.cpp -o PES1UG22CS132'
            }
        }

        stage('Test') {
            steps {
                sh './PES1UG22CS132'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            error "Pipeline failed"
        }
    }
}
