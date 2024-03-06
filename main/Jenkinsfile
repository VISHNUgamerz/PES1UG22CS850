pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the .cpp file using a shell script
                    sh 'g++ -o output hello.cpp'
                }
            }
            post {
                success {
                    echo 'Build stage successful'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Print output of .cpp file using a shell script
                    sh './output'
                }
            }
            post {
                success {
                    echo 'Test stage successful'
                }
            }
        }
        stage('Deploy') {
            steps {
                // Add deployment steps if required
            }
            post {
                success {
                    echo 'Deploy stage successful'
                }
            }
        }
    }

    post {
        always {
            script {
                // Display 'pipeline failed' in case of any errors
                if (currentBuild.result == 'FAILURE') {
                    echo 'pipeline failed'
                }
            }
        }
    }
}
