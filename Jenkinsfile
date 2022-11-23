node('agent1') {
    stage('build') {
        git credentialsId: '5bb054df-138d-445d-a645-e5af729fece5', url: 'http://192.168.10.200:8083/svukelic/java-hello-world-with-maven-1'
        sh 'ls -la'   
    }
    stage('test'){
        sh 'mvn test' 
    }  
    stage('junit'){
        junit 'target/*/*.xml'
    }
}
