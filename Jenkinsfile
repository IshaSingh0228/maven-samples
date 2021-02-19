pipeline {
    agent any
    triggers{
        pollSCM('* * * * *')
    }
    
    tools{
            maven 'maven-3'
            jdk 'java11'
    }
    
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
