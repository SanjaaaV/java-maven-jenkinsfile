node('agent1') {
    stage('build') {
        git credentialsId: 'f4de5833-cc1a-4404-98cb-3e5a1dea62ef', url: 'http://192.168.10.200:8083/svukelic/java-hello-world-with-maven1'
        sh 'ls -la'   
    }
    stage('test'){
        sh 'mvn test' 
    }  
    stage('junit'){
        junit 'target/*/*.xml'
    }
}
