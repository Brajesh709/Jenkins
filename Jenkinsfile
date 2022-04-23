pipeline {
    agent any
    environment {
        name ='brajesh'
        sex ='male'
    }
    parameters {
        string(name: 'person', defaultValue: 'none', description: "")
    }
    stages {
        stage('test') {
            steps {
                sh '''
                ls
                cal
                date
                '''
            }
        }
        stage('Environment variables') {
            steps {
                sh 'echo  "${BUILD_ID}"'
                sh 'echo  "${name}"'
                sh 'echo  "${sex}"'
            }
        }
        stage('deploy on test') {
            steps {
                echo 'deploy on test'
            }
        }    
        stage('continue?') {
            input {
                message "should we continue?"
                ok 'Yes,we should'
            }
            steps {
                echo 'deploy on prod'
            }
        }
        stage('deploy on prod') {
            steps {
                echo 'deploy on prod'
            }
        }
    }
    post { 
            always { 
                echo 'I will always say Hello again!'
            }
        }
}
