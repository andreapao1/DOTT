pipeline {
    stage('Build') {
        sh 'echo "Step One build something else" '
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/andreapao1/DOTT.git']]])
    }
    stage('SonarQube') {
        sh 'echo "Step Two Sonarqube x" '
        sh "ls -a"
        def scannerhome =tool 'sonar';
        withSonarQubeEnv ('sonar'){
            sh """${scannerhome}/bin/sonar-scanner \
            -Dsonar.projectKey=Prueba \
            -Dsonar.sources=. \
            -Dsonar.host.url=http://18.191.237.226:9000 \
            -Dsonar.login=67da9d6baa6086238ec2bea0f00035d7ed60c4f5 """
        }
    }
    stage('Quality Gate') {
        sh 'echo "Step Three ddd" '
    }
    stage('Testing') {
        sh 'echo "Step Three ddd" '
    }
    stage('Deploy') {
        sh 'echo "Step Three" '
    }
}
