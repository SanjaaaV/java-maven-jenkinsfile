node('agent1') {
    stage("checkout") {
        checkout scm 
    }

    stage('build'){
        sh 'ls -la' 
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
    stage('finish'){
        def response = httpRequest acceptType: 'APPLICATION_JSON', consoleLogResponseBody: true, contentType: 'APPLICATION_JSON', httpMode: 'POST', requestBody: '{"result":"Build job - SUCCESS."}', responseHandle: 'NONE', url: 'http://192.168.10.200:3538/jenkins', validResponseCodes: '200', wrapAsMultipart: false  
    }
}
