pipeline {
    agent any
    
    tools{
            maven 'maven-3'
    }

    options{
        retry(3)
        timeout(time: 1, unit: 'HOURS')
    }
    
    stages {
        stage('Maven-Clean'){
            steps{
                sh 'mvn clean'
            }
        }
        stage('Maven-Compile'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Maven-test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Maven-Package'){
            steps{
                sh 'mvn package''
            }
        }
    }
}
