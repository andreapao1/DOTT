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
            -Dsonar.sources=./cidr_convert_api \
            -Dsonar.host.url=http://ec2-18-191-237-226.us-east-2.compute.amazonaws.com:9000 \
            -Dsonar.login=4cb0a7188397c274fed2efeec862b0642c8cfcd1 """
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
