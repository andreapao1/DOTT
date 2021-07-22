pipeline {
    agent any

    stages {
        stage('First') {
            steps {
                script{
                    env.EXECUTE="True"
                }
            }
        }
        stage('Second') {
            when {
                expression { EXECUTE=="True"}
                }
            steps {
                script{
                    echo 'Updating Second Stage'
                }
            }
        }
        stage('Third') {
            when {
                expression { EXECUTE=="False"}
            }
            steps {
                echo 'Step Three'
            }
        }
    }
}
