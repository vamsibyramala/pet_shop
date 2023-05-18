pipeline {
    agent any
    stages {
        stage (SCM) {
            steps {
                git branch: 'main', url: 'https://github.com/vamsibyramala/pet_shop.git'
            }
        }
        stage (build) {
            steps {
                sh 'mvn clean package'
            }
        }
        stage (deploy) {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://13.127.16.29:8081/')], contextPath: 'test', war: '**/*.war'
            }
        }
    }
}
