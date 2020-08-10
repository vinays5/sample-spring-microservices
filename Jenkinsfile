pipeline {
agent {
label 'build-machinejava'
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
       sh "cd ${params.Service_Name} ; mvn clean install " 
    }
}
stage ('Create_Image'1)
{
   steps
    {
        sh "cd $WORKSPACE/${params.Service_Name} ; sudo docker build --tag=${params.Service_Name} ."
    }
}
docker_image_push()
{
      stage('image pushing1')
      {
            sh "sudo docker login -uankit1111 -pmiet@1234"
            sh " sudo docker tag ${params.Service_Name} ankit1111/${params.Service_Name}:v1"
            sh " sudo docker push ankit1111/${params.Service_Name}:v1"
            
      }
} 

stage ('deploying_to_k8s1') {
      
steps {
      node ('ansible-machine')
      {
            sh "cd /opt ; sudo ansible-playbook devops.yaml"
            
      }
}
}
}
}
