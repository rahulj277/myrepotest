pipeline {
    /* specify nodes for executing */
    agent any
 
    stages {
        stage('Do the deployment') {
            steps {
                echo ">> Run deploy applications "
                sh "ls -l"
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