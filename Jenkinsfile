pipeline {
    agent  any
    stages {
        stage('deployments') {
            parallel {
                stage('JIRA') {
                    steps {
                        def versao = jiraJqlSearch jql: "project = testejenkinsjira AND fixVersion = teste-123"
                        echo versao.data.toString()
                        echo 'Jira deployment done'
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