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
    bat 'kubectl apply -f deployment.yaml --validate=false'
   }
  }
 }
}