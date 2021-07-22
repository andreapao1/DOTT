pipeline {
    agent { label 'master'}
    
    stages {
        stage ('install'){
            steps {
                dir("build_node"){
                    sh "pwd ls"
                    sh "npm install"
                }
            }
        }
        
        stage ('test') {
            steps {
                dir("node"){
                    sh "npm test"
                }
            }
        }
        stage ('docker build'){
            steps {
                echo "build"
            }
        }
        
        stage ('docker push') {
            steps {
                echo "push"
            }
        }
    }
}
