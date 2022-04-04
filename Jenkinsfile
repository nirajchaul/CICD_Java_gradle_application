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
                echo "========executing A========"
                script { 
                    withSonarQubeEnv(credentialsId: 'Sonarqube-AdminTokenb') {
                    sh 'chmod +x gradlew'
                    sh './gradlew sonarqube'
                    }

                }
            }
            
        }
    }
    post{
        always{
            echo "Success"
        }
        
    }
}
