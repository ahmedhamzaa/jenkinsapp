pipeline {
    agent any 
    tools { 
        maven 'maven'
    }
    stages {
        stage ("Clean up"){
            steps {
                deleteDir()
            }
        }
        stage ("Clone repo"){
            steps {
                sh "git clone https://github.com/ahmedhamzaa/jenkinsapp.git"
            }
        }
        stage('Build') {
            steps {
                dir("jenkinsapp"){
                      sh "mvn clean install"
                  }
            }
        }
        stage('Deploy') {
            steps {
                dir("jenkinsapp"){
                      sh "docker compose up -d"
                  }
            }
        }
        
    }
}
