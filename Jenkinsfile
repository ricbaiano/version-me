pipeline {
    agent  any
    stages {
        stage('deployments') {
            parallel {
                stage('deploy to dsv') {
                    steps {
                        echo 'dsv deployment done'
                    }
                }
                stage('deploy to hmg') {
                    steps {
                        echo 'hmg deployment done'
                    }
                }
                stage('deploy to prod') {
                    steps {
                        echo 'prod deployment done'
                    }
                }
            }
        }
    }
}