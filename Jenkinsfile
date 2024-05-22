node ('dev') {
    stage('Git') {
        git branch: 'main', url: 'https://github.com/vamsibyramala/pet_shop.git'
    }
    stage('Build') {
        sh 'mvn clean package'
    }
    stage('Deploy') {
        deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://52.66.55.153:8080/')], contextPath: 'app', war: '**/*.war'
    }
}
