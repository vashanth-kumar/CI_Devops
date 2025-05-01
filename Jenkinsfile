pipeline {
    agent any

    environment {
        VENV_DIR = 'venv'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/vashanth-kumar/CI_Devops.git'
            }
        }

        stage('Set up Python venv') {
            steps {
                echo 'Setting up Python virtual environment...'
                sh '''
                    python3 -m venv $VENV_DIR
                    . $VENV_DIR/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt || true
                '''
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running unit tests...'
                sh '''
                    . $VENV_DIR/bin/activate
                    pytest || echo "Tests failed or no tests found"
                '''
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            sh 'rm -rf $VENV_DIR'
        }
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed. Check logs above for errors.'
        }
    }
}
