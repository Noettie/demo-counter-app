pipeline{
    
    agent any 
    
    stages{
        
        stage('sonar quality check'){
            
            agent{
                
                docker {
                    image 'maven'
                }   
            }         
            steps{
            
                stript{
                
                  withSonarQubeEnv(credentialsId: 'sonar-token', installationName: 'sonar-server') {
        
                  sh 'mvn clean package sonar:sonar'
                  }
                }
            }
        }
    }
}
