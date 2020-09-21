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
       sh "cd /home/ubuntu/workspace/21stjava/account-service ; mvn clean install " 
    }
}

stage ('Create_Image1')
{
   steps
    {
        sh "cd /home/ubuntu/workspace/21stjava/account-service ; sudo docker build --tag=account-service ."
    }
}

 stage('image pushing1')
    {
    steps 
    {
            sh "sudo docker login -uankit1111 -pmiet@1234"
            sh " sudo docker tag account-service ankit1111/account-service"
            sh " sudo docker push ankit1111/account-service"
            
      }

}

    stage ('k8sdeployment'){
        steps {
            
        node ('build.javamachine'){
            
            
              sh "sudo ansible-playbook /opt/devops.yaml"  
    
            }
        }
    }
  }
}
