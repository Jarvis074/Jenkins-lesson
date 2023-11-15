pipeline {
    agent {
        docker {
            image 'python:latest'
            args '-u root'
        }
    }
    stages {
        stage("deps") {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage("test") {
            steps {
                sh 'python -m coverage -m nose2'
                sh 'python -m coverage xml'
                sh 'python -m coverage html'
            }
        }
    }
}