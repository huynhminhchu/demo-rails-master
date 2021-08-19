pipeline {
    agent linux
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    app = docker.build("huynhminhchu/demo-rails")
                    app.inside {
                        sh 'echo $(curl localhost:8080)'
                    }
                }
            }
        }
    }   
}
