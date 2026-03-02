pipeline {
    agent {
        label 'agent'
    }
    stages {

        stage('Build') {
            steps {
                sh '''
                echo "Building Java project..."
                cd "Password Protection"
                mkdir -p build
                javac -d build src/*.java
                echo "Build successful"
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                echo "Testing stage..."
                echo "No JUnit tests configured"
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                echo "Deploy stage..."
                cd "Password Protection"
                jar cf FileEncrypter.jar -C build .
                echo "Artifact created"
                '''
            }
        }

    }

    post {
        success {
            echo "Pipeline executed successfully!"
        }
        failure {
            echo "Pipeline failed!"
        }
    }
}
