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
              sonar-scanner \
              -Dsonar.projectKey=Prueba \
              -Dsonar.sources=. \
              -Dsonar.host.url=http://ec2-52-14-179-80.us-east-2.compute.amazonaws.com:9000 \
              -Dsonar.login=a31a5c26906baa360b699f455b9877bbe9a2be4d """
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
