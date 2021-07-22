pipeline {
    agent { label 'master'}
    
    stages {
        stage ('install'){
            steps {
                dir("build_node"){
                    sh "pwd"
                    sh "ls"
                    sh "npm install"
                }
            }
        }
    }
}
