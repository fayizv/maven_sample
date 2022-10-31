pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/fayizv/maven_sample']]])
            }
        }
        stage('Test') {
            steps {
                sh 'ls'
            }
        }
    }
}
