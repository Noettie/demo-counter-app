pipeline{
    
    agent any 
    
    stages{
        
        stage('sonaar quality check'){
            
            agent{
                
                docker {
                    docker.withServer('jenkins') {
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
