def gv
pipeline {
    agent any
    parameters {
 choice(name: 'version', choices: ['1.0', '2.0', '3.0', '4.0'], description: 'version details')
}
    environment {
    stage = "dev"
    login = credentials('tomcat')
    }
    stages {
    stage("initi") {
        steps {
        script {
         gv = load "script.groovy"

}
}
}


        stage('Build') {
            
            when {
                expression  {
                   BRANCH_NAME == "dev"
                   }
}
        steps {            
        script {
         gv.buildapp()
   
}
    echo "Building ${stage} with VERSION ${params.version} .."
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

