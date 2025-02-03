pipeline {
    agent { label 'dev' }
    tools {maven 'maven'}

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
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://172.31.8.55:8080/')], contextPath: 'vamsi', war: '**/*.war'
            }
        }
    }
}
