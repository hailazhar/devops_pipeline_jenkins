pipeline {
    agent any
    triggers {
        pollSCM '*/5 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                sh "docker-compose up -d"
            }
        }
        stage('Test') {
            steps {
                sh '''
                  apt update 
                  apt install -y python3 python3-pip python3-venv
                  python3 -m venv /venv
                  . /venv/bin/activate
                  docker-compose up -d
                  sleep 5
                  '''
            }
        }
    }
}
        stage('Deliver') {
            steps {
                echo ("Delivered . . . . . ")
            }
        }    