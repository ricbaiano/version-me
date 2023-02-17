pipeline {
    agent any
    stages {
        stage('git repo & clean') {
            steps {
               bat "rmdir  /s /q version-me"
                bat "git clone https://github.com/ricbaiano/version-me.git"
                bat "mvn clean -f version-me"
            }
        }
        stage('install') {
            steps {
                bat "mvn install -f version-me"
            }
        }
        stage('test') {
            steps {
                bat "mvn test -f version-me"
            }
        }
        stage('package') {
            steps {
                bat "mvn package -f version-me"
            }
        }
    }
}