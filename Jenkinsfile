pipeline{
    agent any
        stages{
   
           stage('Build'){
               steps{
                      git url: 'https://github.com/KRDevops/hello-world-war.git'
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
       deploy adapters: [tomcat9(credentialsId: '9ca0a4b5-e19f-426b-aa88-7a5345482f9d', path: '', url: 'http://13.233.98.12:8888')],
           contextPath: 'hellokondareddy', war: '**/*.war'
            
        }
        }
        
    }
}

