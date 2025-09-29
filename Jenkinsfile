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
pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        sh 'echo "<h1>Hello from Jenkins Pipeline</h1>" > index.html'
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts artifacts: 'index.html', fingerprint: true
      }
    }
  }
}
    stage('Deploy') {
      steps {
        sh 'sudo cp index.html /var/www/html/'
      }
    }
