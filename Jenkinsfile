pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                 echo 'Building...'
             }
             post {
                 always {
                     jiraSendBuildInfo site: 'richardbarbosa.atlassian.net'
                 }
             }
         }
         stage('Deploy - Staging') {
             when {
                 branch 'main'
             }
             steps {
                 echo 'Deploying to Staging from main...'
             }
             post {
                 always {
                     jiraSendDeploymentInfo environmentId: 'TESTEJJ-1', environmentName: 'TESTEJJ-1', environmentType: 'staging'
                 }
             }
         }
         stage('Deploy - Production') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying to Production from main...'
            }
            post {
                always {
                    jiraSendDeploymentInfo environmentId: 'TESTEJJ-1', environmentName: 'TESTEJJ-1', environmentType: 'production'
                }
            }
         }
     }
 }