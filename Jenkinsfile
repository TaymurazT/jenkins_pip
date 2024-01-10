pipeline {
    agent any
    tools {
        maven "m3"
    }


    stages {
        stage ('git') {
            steps {
                git 'https://github.com/TaymurazT/less11.git'
            }
        }
        stage ('build') {
            steps {
                sh 'mvn package'
            }
        }
        stage ('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: '17a98a1d-8170-4e47-841f-2d98569ee4c6', path: '', url: 'http://84.201.152.205:8080')], contextPath: 'mywebapp33', war: '**/*.war'
            }
        }
    }
}