node('agent1') {
    stage("checkout") {
        checkout scm 
    }
    stage('build'){
        // sh 'git clone http://192.168.10.200:8083/svukelic/java-hello-world-with-maven1.git maven2'
        sh 'ls -la'  
        def rsponse = httpRequest contentType: 'APPLICATION_JSON', httpMode: 'POST', url: ' http://192.168.10.200:3537/jenkins'
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
