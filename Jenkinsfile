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
                    sh "${scannerHome}/bin/sonar-scanner"
                
                    sh 'mvn clean package sonar:sonar'
                  }
                }
            }
        }
    }
}
