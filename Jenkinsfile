pipeline {
    /* specify nodes for executing */
    agent {
        any
    }
 
    stages {
        /* checkout repo */
        stage('Do the deployment') {
            steps {
                echo ">> Run deploy applications "
                sh "cat testing.txt"
            }
        }
    }
 
    /* Cleanup workspace */
    post {
       always {
           deleteDir()
       }
   }
}