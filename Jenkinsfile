pipeline {
    agent any
    environment {
        AWS_ACCOUNT_ID="775012328020"
        AWS_DEFAULT_REGION="us-east-1"     
    }
        
    stages {
        stage('Akshow Infrastructure Deployment') {
           environment {
             AWS_ACCESS_KEY_ID = credentials('Access_key_ID')
             AWS_SECRET_ACCESS_KEY = credentials('Secret_access_key')
           }
           steps {
              script {
                  sh "terraform init"
                  sh "terraform validate"
                  sh "terraform plan"
                  sh "terraform ${action} --auto-approve"
            }
        }
               
     }
    }
    
}
