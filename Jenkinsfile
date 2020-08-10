pipeline {
agent {
label 'build-machinejava'
}

stages {

stage ('Checkout') 
{
steps
    {
    
        checkout scm
        
    }
    
}
stage ('Build') 
{
    steps
    {
       sh "cd ${params.Service_Name} ; mvn clean install " 
    }
}
stage ('Create_Image')
{
   steps
    {
        sh "cd $WORKSPACE/${params.Service_Name} ; sudo docker build --tag=${params.Service_Name} ."
    }
}
docker_image_push()
{
      stage('image pushing')
      {
            sh "sudo docker login -uankit1111 -pmiet@123"
            sh " sudo docker tag ${params.Service_Name} ankit1111/${params.Service_Name}:v1"
            sh " sudo docker push ankit1111/${params.Service_Name}:v1"
            
      }
} 

stage ('deploying_to_k8s') {
      
steps {
      node ('ansible-machine')
      {
            sh "cd /opt ; sudo ansible-playbook devops.yaml"
            
      }
}
}
}
}
