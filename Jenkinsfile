pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                retry(3) {
                    sh './flakey-deploy.sh'
                }

                timeout(time: 1, unit: 'MINUTES') {
                    sh './health-check.sh'
                }
            }
        }
    }
}