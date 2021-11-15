pipeline {
    agent {
        kubernetes {
            yaml """
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: centos
    image: centos:7
    command: ['cat']
    tty: true
  - name: ubuntu
    image: ubuntu:18.04
    command: ['cat']
    tty: true
"""
        }
    }
    stages {
        stage('Run CentOS7') {
            steps {
                container('centos') {
                    sh 'cat /etc/*-release'
                }
            }
        }
        stage('Run Ubuntu') {
            steps {
                container('ubuntu') {
                    sh 'cat /etc/*-release'
                }
            }
        }
    }
}
