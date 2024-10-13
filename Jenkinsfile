pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/saadbhatti763/jenkins_demo.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh 'echo "Building the app..."'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    sudo cp -r * /var/www/html/
                    sudo systemctl reload nginx
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
