pipeline {
    agent any
    stages {
        stage ("taking code from SCM") {
            steps {
                git branch: 'main', url: 'https://github.com/vamsibyramala/pet_shop.git'
            }
        }
        
        stage ("building with maven") {
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage ("deploy to tomcat") {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://15.207.254.76:8080/')], contextPath: 'test', war: '**/*.war'
            }
        }
    }
}
