pipeline {
    agent any
    triggers{
        pollSCM('* * * * *')
    }
    
    tools{
            maven 'maven3'
            jdk 'jdk11'
    }
    //Nothing Interesting Happening
    stages {
        stage('clean')
        {
            steps{
            bat 'mvn clean'
            }
        }
        stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonarqube') {
                    
                        bat 'mvn package sonar:sonar'
                    
                }
            }
        }
    }
    
}
