pipeline {
    agent any
    
    tools{
            maven 'maven-3'
    }
    
    stages {
        stage('clean')
        {
            steps{
            sh 'mvn clean'
            }
        }
        stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonarqube') {
                    // Optionally use a Maven environment you've configured already
                    //withMaven(maven:'Maven-3') {
                        //sh 'mvn clean package sonar:sonar'
                    sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar'
                    
                }
            }
        }
    }
    
}
