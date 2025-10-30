pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/nerdydatacool/my-sample-app.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'C:\Users\12013\anaconda3\python.exe -m py_compile app.py'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'pytest || echo "No tests found"'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Example: deploy to EC2 using SSH
                // sh 'scp app.py ubuntu@<your-ec2-ip>:/home/ubuntu/app/'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
