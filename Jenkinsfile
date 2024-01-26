''' jenkins
pipeline {
    agent {
        docker {
            image 'agolubkov/buidimage:latest'
            args '-u root'
        }
   } 

    
    stages {
        stage('Copy source with configs') {
            steps {
                git 'https://github.com/golubkovan/JenkinsHW3.git'
            }
        }
        stage('Build jar') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Make docker image') {
            steps {
                sh 'docker build --tag=tomcat+war .'
                sh '''docker tag tomcat+war agolubkov/tomcat+war && docker push agolubkov/tomcat+war'''

      }
    }
    }
}

'''
