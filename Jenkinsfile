pipeline {
    agent any
    
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
                    // Optionally use a Maven environment you've configured already
                    //withMaven(maven:'maven-3') {
                        bat 'mvn package sonar:sonar'
                   // }
                    //sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar'
                    
                }
            }
        }
    }
    
}
