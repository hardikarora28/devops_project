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
                            sh 'chmod -R 744 ?/.sonar'
                            sh './gradlew sonarqube --stacktrace'
                        
                    }
                }
            }
        }
    }
}
