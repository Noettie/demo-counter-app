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
                
                   withSonarQubeEnv(credentialsId: 'sonar-token') {
                
                   sh 'mvn clean package sonar:sonar'
                 }
                }
            }
        }
    }
}
