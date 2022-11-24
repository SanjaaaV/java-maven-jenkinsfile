node('agent1') {
    stage('build'){
        sh 'git init'
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
