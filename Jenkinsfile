pipeline {
    agent any
    environment {
    stage = "dev"
    login = credentials('tomcat')
    }
    stages {
        stage('Build') {
            
            when {
                expression  {
                   BRANCH_NAME == "dev"
                   }
}
        steps {            
    echo "Building ${stage} with ${login} .."
            }
        }
        stage('Dev') {
            when {
                  expression {
                BRANCH_NAME == "master"
}
}
            steps {
               
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
