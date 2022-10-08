pipeline{
    agent any 
    environment{
        VERSION = "${env.BUILD_ID}"
    }
    stages{
        stage("sonar quality check"){
            agent any
            steps{
                script{
                    withSonarQubeEnv('sonarserver') {
                            sh 'chmod +x gradlew'    
                            sh './gradlew sonarqube --stacktrace'
                        
                    }
                }
            }
        }
    }
}
