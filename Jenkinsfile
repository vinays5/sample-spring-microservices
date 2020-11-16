pipeline {
agent {
label 'build.javamachine'
}

stages {

stage ('Checkout1') 
{
steps
    {
    
        checkout scm
        
    }
    
}
stage ('Build1') 
{
    steps
    {
       sh "cd /home/ubuntu/workspace/16thnovdevopsjava/account-service ; mvn clean install " 
    }
}
  }
}
