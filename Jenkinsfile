node ('dev') {
    tool 'maven'
    stage('Git') { 
        git branch: 'main', url: 'https://github.com/vamsibyramala/pet_shop.git'
    }
    stage('Build') {
        sh 'mvn clean package'
    }
    stage('Deploy') {
        deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://13.232.206.198:8081/')], contextPath: 'vamsi', war: '**/*.war'
    }
}
