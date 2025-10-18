pipeline {
    agent  { label 'agent-01' }
    tools {
        maven 'My-Mavan'
        jdk   'JDK-17'
    }
    stages {

        stage('compile') {
            steps {
                sh "mvn compile"
            }
        }
        stage('test') {
            steps {
                sh "mvn test"
            }
        }
        stage('package') {
            steps {
                sh "mvn package"
            }
        }
       stage('Artifacts') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false, onlyIfSuccessful: true
            }
        }
        
    }
}
