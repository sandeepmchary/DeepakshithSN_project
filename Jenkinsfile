pipeline{
    agent any
    stages{
        stage("Sonarqube"){
            agent {
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
                script {
                        withSonarQubeEnv(credentialsId: 'sonar-id'){
                            sh 'chmod +x gradlew'
                            sh './gradlew sonarqube'
                        }

                }
            }
        }
    }
}
