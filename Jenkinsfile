#!groovy

pipeline {
  agent {
        docker {
            image "maven:3.6.0-jdk-13"
            label "docker"
            args "-v /tmp/maven:/var/maven/.m2 -e MAVEN_CONFIG=/var/maven/.m2"
        }
    }
    tools {
        maven "MAVEN" 
    }

    stages {
        stage("Build") {
            steps {
                sh "mvn -version"
                sh "mvn clean install"
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
