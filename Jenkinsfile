node('agent1') {
    stage('build'){
        sh 'git init'
        withCredentials([usernamePassword(credentialsId: '5bb054df-138d-445d-a645-e5af729fece5', passwordVariable: 'Sanja1972!', usernameVariable: 'svukelic')]) {
    sh 'git clone http://192.168.10.200:8083/svukelic/java-hello-world-with-maven1.git maven2'
}
         
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
