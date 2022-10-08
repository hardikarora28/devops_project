pipeline{
    agent any 
    environment{
        VERSION = "${env.BUILD_ID}"
    }
    stages{
        stage("sonar quality check"){
            agent {
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv('sonarserver') {
                            sh 'chmod +x gradlew'
                            sh 'chmod -R 744 ?/.sonar'
                            sh './gradlew sonarqube --stacktrace'
                        
                    }
                }
            }
        }
    }
}
