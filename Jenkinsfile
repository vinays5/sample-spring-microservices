pipeline {
agent {
label '24thdevops'
}

stages {

stage ('Checkout') 
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
       sh "cd /home/ubuntu/workspace/28thJava/account-service ; mvn clean install " 
    }
}
 
}
    
}
