pipeline {
agent {
label 'build.machinejava'
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
       sh "cd /home/ubuntu/workspace/Devops-102/account-service ; mvn clean install " 
    }
}

     
}
}
