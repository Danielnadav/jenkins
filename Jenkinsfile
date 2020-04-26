pipeline {
  agent {
    kubernetes {
      //cloud 'kubernetes'
      label 'docker'
      yaml """
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: docker
    image: docker:1.11
    command: ['cat']
    tty: true
    volumeMounts:
    - name: dockersock
      mountPath: /var/run/docker.sock
  volumes:
  - name: dockersock
    hostPath:
      path: /var/run/docker.sock
"""
    }
  }
  stages {
    stage('Build Docker image') {
      steps {
        // git 'https://github.com/jenkinsci/docker-jnlp-slave.git'
        container('docker') {
          script {
            // def image = docker.build('jenkins/jnlp-slave')
            // image.inside() {
              sh "docker ps -a"
            }
          }
        
      }
    }