pipeline {
    agent any
    parameters {
  choice choices: ['1.10', '1.20', '1.30'], description: 'Select the version', name: 'VERSION'
  booleanParam defaultValue: true, description: 'check and execute', name: 'check'
         


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
            input {
  message 'check and execute'
}

   
            steps {
                echo 'testing the application'
                echo " the version for testing is ${params.VERSION}"
                
            }
        }
    

        stage('deploy') {
   
            steps {
                echo 'deploying the application'
            }
        }
    }
        post {
  success {
  
      sh '${date}
  }
}

}
