pipeline {
    agent any
    environment {
        AWS_ACCOUNT_ID="767398084126"
        AWS_DEFAULT_REGION="us-east-2"     
    }
        
    stages {
        stage('Akshow Infrastructure Deployment') {
           environment {
             AWS_ACCESS_KEY_ID = credentials('aws_access_key_id')
             AWS_SECRET_ACCESS_KEY = credentials('aws_secrete_access_key')
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
