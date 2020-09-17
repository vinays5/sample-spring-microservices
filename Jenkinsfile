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
       sh "cd /home/ubuntu/workspace/build-javaJOB/account-service ; mvn clean install " 
    }
}

stage ('Create_Image1')
{
   steps
    {
        sh "cd /home/ubuntu/workspace/build-javaJOB/account-service ; sudo docker build --tag=account-service ."
    }
}



}
}
