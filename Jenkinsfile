pipeline {
    agent any
    parameters {
   choice(name: 'VERSION', choices: ['1.10', '1.20', '1.30'], description: '')
        booleanParam (name: 'execute', defaultValue: true, description: '')
    }
        


    stages {
        stage('build') {
            when{
                expression{
                    params.execute
                }
            }
   
            steps {
                echo 'de the application'
            }
        }
    
   
        stage('test') {
   
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
}
