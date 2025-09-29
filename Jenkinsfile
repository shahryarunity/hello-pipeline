pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/shahryarunity/hello-pipeline.git'
            }
        }

        stage('Deploy to Web') {
            steps {
                script {
                    // Copy project files to nginx web root
                    sh 'sudo cp -r * /var/www/html/'
                }
            }
        }
    }
}
