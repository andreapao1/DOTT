pipeline {
    agent any
    stages {
    stage('Build') {
          steps {
        sh 'echo "Step One build something else" '
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/andreapao1/DOTT.git']]])
                }
            }
        stage('SonarQube') {
        steps {
        sh 'echo "Step Two Sonarqube x" '
        sh "ls -a"
        def scannerhome = tool 'Prueba';
        withSonarQubeEnv ('Prueba'){
            sh """${scannerhome}/opt/sonarqube  \
              -Dsonar.projectKey=Prueba \
              -Dsonar.sources=. \
              -Dsonar.host.url=http://18.191.237.226:9000 \
              -Dsonar.login=67da9d6baa6086238ec2bea0f00035d7ed60c4f5 """
        }
    }
    }
    stage('Quality Gate') {
        steps {
        sh 'echo "Step Three ddd" '
                  }
    }
    stage('Testing') {
        steps {
        sh 'echo "Step Three ddd" '
               }
    }
    stage('Deploy') {
        steps {
        sh 'echo "Step Three" '
               }
    }
}
}
