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
    }
}
