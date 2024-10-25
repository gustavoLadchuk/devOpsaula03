pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
		sudo apt update
		sudo apt install python3
		python -m venv devops
		source devops/bin/activate
		pip install flask
		pip install flask flask-cors
		'''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
		python3 main.py --host=0.0.0.0
		'''
            }
        }
    }
}
