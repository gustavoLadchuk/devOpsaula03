pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh '''
		python3 -m venv devops
		. devops/bin/activate
		pip install flask
		pip install flask flask-cors
		'''
            }
        }
        stage('Deploy') {
            steps {
                sh '''
		. devops/bin/activate
		nohup python3 main.py --host=0.0.0.0
		'''
            }
        }
    }
}
