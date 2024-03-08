pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    build 'PES1UG21CS165-1'
                    sh 'g++ test.cpp -o output'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Print the output of the .cpp file using a shell script
                    sh './output'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Add deployment steps if needed
                    echoss 'deploy'
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
