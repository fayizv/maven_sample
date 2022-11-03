pipeline{
    agent any
    stages {
        stage("Build Maven") {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/fayizv/maven_sample']]])
            }
        }       
       stage('Build'){
            steps{
                sh 'mvn clean package'
            }
         }
        stage('SonarQube analysis') {
        steps{
        withSonarQubeEnv('sonarqube-9.2.2') { 
        sh "mvn sonar:sonar"
    }
        }
        }
       
    }
}

//test jekins webhook
