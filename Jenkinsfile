pipeline {
    agent any  // Run on any available Jenkins agent (machine)

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/DeleepVoleti/my-jenkins-demo.git'
            }
        }

        stage('Install Python (Optional)') {
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
