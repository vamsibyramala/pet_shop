pipeline {
    agent {
  label 'dev'
}
tools {
  maven 'maven'
}
    stages {
        stage('Git') {
            steps {
                git branch: 'main', url: 'https://github.com/vamsibyramala/pet_shop.git'
            }
        }
        stage('maven') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('deploy') {
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat', path: '', url: 'http://18.216.225.116:8080/')], contextPath: 'myapp', war: '**/*.war'
            }
        }
    }
}
