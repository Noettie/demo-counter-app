pipeline{
    
    agent any 
    
    stages{
        
        stage('sonaar quality check'){
            
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
