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
        withCredentials([gitUsernamePassword(credentialsId: '2e27d0f2-ad04-4ecb-87dd-92cd66ad8434', gitToolName: 'Default')]) {
            sh "curl -D -u $USERNAME:$PASSWORD -X GET -H 'Content-Type: application/json' http://192.168.10.200:3537/path/to/api/ endpoint"
        }
    }
    stage('test'){
        sh 'mvn test' 
    }  
    stage('junit'){
        junit 'target/*/*.xml'
    }
}
