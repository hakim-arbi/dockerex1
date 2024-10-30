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
                sh "git clone https://github.com/MaBouz/exp1-spring.git"
            }
        }
        stage('Generate backend image') {
            steps {
                dir("exp1-spring"){
                      sh "mvn clean install"
                      sh "sudo docker build -t docexp1.spring ."
                  }
            }
        }
        stage ("Run docker compose") {
            steps {
            dir("exp1.spring"){
                sh "sudo docker compose up -d"
        }
    }
  }
}
                }
