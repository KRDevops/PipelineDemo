pipeline{
    agent any
        stages{
   
           stage('Build'){
               steps{
                      git url: 'https://github.com/KRDevops/PipelineDemo.git'
             }
        }
       
        stage('Maven package'){
            steps{
       
            sh "/opt/maven/bin/mvn clean package sonar:sonar"
        }
        }
        stage('Maven deploy'){
            steps{
       
            sh "/opt/maven/bin/mvn clean deploy"
        }
        }
            stage('deploy_container'){
            steps{
       deploy adapters: [tomcat9(credentialsId: 'c9a8be14-f268-410b-a60b-ad9bdeb44fc5', 
                                 path: '', url: 'http://13.233.98.12:8888/')], 
           contextPath: 'helloworld', war: '**/*.war'
            
        }
        }
        
    }
}

