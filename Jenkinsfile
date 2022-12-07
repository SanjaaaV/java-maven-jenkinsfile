node('agent1') {
    stage("checkout") {
        checkout scm 
    }
    stage('build'){
        // sh 'git clone http://192.168.10.200:8083/svukelic/java-hello-world-with-maven1.git maven2'
        sh 'ls -la'  
        httpRequest acceptType: 'APPLICATION_JSON', contentType: 'APPLICATION_JSON',
            httpMode: 'POST', quiet: true,
            requestBody: '''{
               "display-name" : "my_Username",
               "email" : "user@example.test",
               "password" : {
                  "value" : "my_password"
               },
            }''',
            url: 'https://192.168.10.200:3537/jenkins' 
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
