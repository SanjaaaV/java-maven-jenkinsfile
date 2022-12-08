node('agent1') {
    stage("checkout") {
        checkout scm 
    }
    stage('build'){
        // sh 'git clone http://192.168.10.200:8083/svukelic/java-hello-world-with-maven1.git maven2'
        sh 'ls -la' 
        def toJson = {
    input ->
    groovy.json.JsonOutput.toJson(input)
}
def body = [
    displayName: [
        text: "build success"],
    description: [
        text: "jenkins"],
    genusTypeId: "type"
] 
        def response = httpRequest acceptType: 'APPLICATION_JSON', consoleLogResponseBody: true, contentType: 'APPLICATION_JSON', httpMode: 'POST', requestBody: 'toJson(body)', responseHandle: 'NONE', url: 'http://192.168.10.200:3537/jenkins', validResponseCodes: '200', wrapAsMultipart: false
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
