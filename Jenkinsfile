pipeline {
    agent any
    parameters {
  choice choices: ['1.10', '1.20', '1.30'], description: 'Select the version', name: 'VERSION'
  booleanParam defaultValue: true, description: 'check and execute', name: 'check'
    }
         


    stages {
        stage('build') {
            when{
                expression{
                    params.check
                }
            }
   
            steps {
                echo 'building the application'
            }
        }
    
   
        stage('test') {
 

   
            steps {
               
                echo 'testing the application'
                echo " the version for testing is ${params.VERSION}"
                
            }
        }
        stage('Approval') {
            steps {
                script {
                    input message: 'Do you want to proceed to Deploy?', ok: 'Yes', submitter: 'admin'
                    echo 'Aprroval'
                }
            }
        }
    

        stage('deploy') {
   
            steps {
               
                echo 'deploying the application'
            }
        }
    }
        post {
  aborted {
   echo ' application aborted'
  }
  success {
 echo ' application sucess'
  }
  failure {
  echo ' application failure'
  }
}

    


}
