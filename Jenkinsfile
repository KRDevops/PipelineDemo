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
        
        
    }
}

