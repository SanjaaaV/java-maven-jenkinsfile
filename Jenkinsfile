node('agent1') {
    stage('build'){
        sh 'chmod 777 maven2'
        sh 'ls -la'   
    }
    stage('comp'){
        sh 'chmod 777 maven2'
        sh 'mvn compile'
    }
    stage('test'){
        sh 'chmod 777 maven2'
        sh 'mvn test' 
    }  
    stage('junit'){
        sh 'chmod 777 maven2'
        junit 'target/*/*.xml'
    }
}
