node('agent1') {
    stage('build') {
        git credentialsId: 'f4de5833-cc1a-4404-98cb-3e5a1dea62ef', url: 'http://192.168.10.200:8083/svukelic/java-hello-world-with-maven1'
        sh 'git clone http://192.168.10.200:8083/svukelic/java-hello-world-with-maven1.git'
        sh 'ls -la'   
    }
    stage('comp'){
        sh 'mvn compile'
    }
    stage('test'){
        sh 'mvn test' 
    }  
    stage('junit'){
        junit 'target/*/*.xml'
    }
}
