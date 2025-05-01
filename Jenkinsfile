pipeline {
    agent any

<<<<<<< HEAD
    environment {
        VENV_DIR = 'venv'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/vashanth-kumar/CI_Devops.git'
=======
    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/vashanth-kumar/CI_Devops.git'
>>>>>>> f64814e (Initial commit with test and requirements)
            }
        }

        stage('Set up Python venv') {
            steps {
<<<<<<< HEAD
                echo 'Setting up Python virtual environment...'
                sh '''
                    python3 -m venv $VENV_DIR
                    . $VENV_DIR/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt || true
                '''
=======
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate && pip install -r requirements.txt'
>>>>>>> f64814e (Initial commit with test and requirements)
            }
        }

        stage('Run Tests') {
            steps {
<<<<<<< HEAD
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
=======
                sh '. venv/bin/activate && pytest tests'
            }
        }
    }
}

>>>>>>> f64814e (Initial commit with test and requirements)
