pipeline {
 agent any
 tools {
  maven 'Maven'
 }
 stages {
  stage('Build') {
   steps {
    bat 'mvn clean package'
   }
  }
  stage('Docker') {
   steps {
    bat 'docker build -t app .'
   }
  }
  stage('Deploy') {
 steps {
  bat 'set KUBECONFIG=C:\\Users\\Gautam\\.kube\\config && kubectl apply -f deployment.yaml --validate=false'
    }
  }
 }
}