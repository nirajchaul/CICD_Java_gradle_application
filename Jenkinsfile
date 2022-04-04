pipeline{
    agent any
    stages{
        stage("SonarQube Quality Check"){
            agent {
                docker {
                    image "openjdk:11"
                }
            }

            steps{
                script { 
                    withSonarQubeEnv(credentialsId: 'Sonarqube-AdminTokenb') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube --info --build-cache'
                    }
                    
                }
            }
            
        }
    }
    
}