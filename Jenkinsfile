pipeline {
    agent { label 'linux' }
    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker-compose build'
                sh 'docker-compose run web scripts/wait-for-it.sh db:5432 -- "rake db:create db:migrate"'
                sh 'docker-compose up'
                sleep 60
                sh 'echo $(curl localhost:8080)'
            }
        }
    }   
}
