pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/premkumarmarri2006/PYTHONCI.git'
            }
        }

        stage('Run Application') {
            steps {
                bat 'python app.py'
            }
        }

        stage('Test') {
            steps {
                bat 'python -m unittest test_app.py'
            }
        }

        stage('Package') {
            steps {
                bat 'powershell Compress-Archive -Path app.py,test_app.py -DestinationPath PythonCI.zip -Force'
            }
        }
    }
}