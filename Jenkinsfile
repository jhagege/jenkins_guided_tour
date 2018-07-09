pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                retry(3) {
                    sh 'bash ./flakey-deploy.sh'
                }

                timeout(time: 1, unit: 'MINUTES') {
                    sh 'bash ./health-check.sh'
                }
            }
        }
    }
}