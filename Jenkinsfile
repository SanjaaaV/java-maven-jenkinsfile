node('agent1') {
    stage("checkout") {
        checkout scm 
    }
    stage('build'){
        // sh 'git clone http://192.168.10.200:8083/svukelic/java-hello-world-with-maven1.git maven2'
        sh 'ls -la'  
        httpRequest authentication: '2e27d0f2-ad04-4ecb-87dd-92cd66ad8434', contentType: 'APPLICATION_JSON', httpMode: 'POST', responseHandle: 'NONE', url: ' http://192.168.10.200:3537/jenkins', wrapAsMultipart: false
    }
    stage('comp'){
        jiraComment body: 'problem solved', issueKey: 'TES-1'
        sh 'mvn compile'
    }
    stage('test'){
        sh 'mvn test' 
    }  
    stage('junit'){
        junit 'target/*/*.xml'
    }
}
