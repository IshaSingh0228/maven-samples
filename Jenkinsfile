pipeline {
    agent any
    
    tools{
            maven 'maven-3'
    }
    
    stages {
        stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('My SonarQube Server') {
                    // Optionally use a Maven environment you've configured already
                    withMaven(maven:'Maven-3') {
                        sh 'mvn clean package sonar:sonar'
                    }
                }
            }
        }
    }
post{
    failure{
        options{
        retry(3)
    }
    }

}
    
}
