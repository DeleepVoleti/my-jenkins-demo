pipeline {
    agent any

    stages {
        stage('Install Python') {
            steps {
                sh 'python3 --version'
                sh 'pip3 install --upgrade pip'
            }
        }

        stage('Run Unit Tests') {
            steps {
                sh 'python3 -m unittest discover -s .'
            }
        }
    }

    post {
        always {
            echo 'Build finished.'
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
