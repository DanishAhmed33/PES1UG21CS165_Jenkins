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
                    echo 'deploy'
                }
            }
        }
    }

    post {
        always {
            // Display 'pipeline failed' in case of any errors
            echo 'Pipeline completed'
        }

        failure {
            echo 'Pipeline failed'
        }
    }
}
