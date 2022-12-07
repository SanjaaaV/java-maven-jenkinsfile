node('agent1') {
    stage("checkout") {
        checkout scm
        
    }
    stage('build'){
        // sh 'git clone http://192.168.10.200:8083/svukelic/java-hello-world-with-maven1.git maven2'
        sh 'ls -la'   
    }
    stage('comp'){
        jiraComment body: 'problem solved', issueKey: 'TES-1'
        sh 'mvn compile'
        sh "curl -X POST -H 'Content-Type: application/json' http://192.168.10.200:3537/jenkins"
        
    }
    stage('test'){
        sh 'mvn test' 
    }  
    stage('junit'){
        junit 'target/*/*.xml'
    }
}
