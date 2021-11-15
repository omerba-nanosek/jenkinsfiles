pipeline {
    agent {
        kubernetes {
            yaml """
apiVersion: v1
kind: Pod
spec: 
  containers: 
  - name: maven
    image: maven:3.3.9-jdk-8-alpine
    command: ['cat']
    tty: true
"""
        }
    }
    stages {
        stage('Maven-Install') {
            steps {
                git credentialsId: 'e60acdb4-4877-405e-9b2e-d7b980365021', url: 'https://github.com/web3j/sample-project-maven'
                container('maven') {
                    sh 'mvn -version'
                }
            }
        }
    }
}
