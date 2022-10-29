pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                checkout([$class: 'GitSCM',branches: [[name: env.master]],extensions: [[$class: 'WipeWorkspace']],userRemoteConfigs: [[url: 'https://github.com/fayizv/maven_sample.git']]])
            }
        }
        stage('Test') {
            steps {
                sh 'dir'
            }
        }
    }
}
