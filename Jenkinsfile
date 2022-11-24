node('agent1') {
    stage('build'){
        git branch: 'main', credentialsId: '2e27d0f2-ad04-4ecb-87dd-92cd66ad8434', url: 'http://192.168.10.200:8083/svukelic/java-hello-world-with-maven1.git'
        sh 'git clone http://192.168.10.200:8083/svukelic/java-hello-world-with-maven1 maven2'
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
