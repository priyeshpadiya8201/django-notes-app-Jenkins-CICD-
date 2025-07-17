@Library("shared") _
pipeline {
    agent any

    stages {
        
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code") {
            steps {
                script{
                clone("https://github.com/LondheShubham153/django-notes-app.git","main")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    docker_build("notes-app","latest","priyeshpadiya8201")
                }
            }
        }
        stage("Test"){
            steps{
                echo "This is tesing the code"
            }
        }
        stage("Push to Dockerhub"){
            steps{
                script{
                    docker_push("notes-app","latest","priyeshpadiya8201")
                }
            }
        }
        stage("Deploy"){
            steps{
                echo "This is deploing the code"
                sh "docker compose up -d"
            }
        }
    }
}
