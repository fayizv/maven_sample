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
        
            node {
      stage('SCM') {
        git 'https://github.com/foo/bar.git'
      }
      stage('SonarQube analysis') {
        withSonarQubeEnv(credentialsId: 'f225455e-ea59-40fa-8af7-08176e86507a', installationName: 'My SonarQube Server') { // You can override the credential to be used
          sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
        }
      }
    }
    }
}
