pipeline {
    agent { label 'master'}
    
    stages {
        stage ('install'){
            steps {
                dir("build_node"){
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
