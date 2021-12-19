pipeline {
    agent any
    environment {
    stage = "dev"
    }
    stages {
        stage('Build') {
            steps {
                echo "Building ${stage} .."
            }
        }
        stage('Dev') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy Dev') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
