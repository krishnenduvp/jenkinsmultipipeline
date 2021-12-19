pipeline {
    agent any
    environment {
    stage = "dev"
    }
    stages {
        stage('Build') {
            steps {
            when {
                expression  {
                   BRANCH_NAME == "dev"
                   }
}
                echo "Building ${stage} .."
            }
        }
        stage('Dev') {
            steps {
            when {
                  expression {
                BRANCH_NAME == "master"
}
}
                echo "Testing on ${BRANCH_NAME} .."
            }
        }
        stage('Deploy Dev') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
