pipeline {
    agent { label 'linux' }
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    app = docker.build("huynhminhchu/demo-rails")
                    docker.image("huynhminhchu/demo-rails").withRun('-p 3306:3306'){
                        sleep 60
                        sh 'echo $(curl localhost:8080)'
                    }
                    
                }
            }
        }
    }   
}
