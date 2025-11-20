@Library("shared") _

pipeline {
    agent { label "akshat" }

    stages {
        stage('Code'){
            steps {
                 script {
                     git_clone("https://github.com/AkshatPareek9/project-django-notes-app.git", "main")
                 }
            }
        }
        stage('Build'){
            steps {
                script{
                    docker_build("notes-app", "latest")
                }
            }
        }
        stage('Push'){
            steps {
                script{
                    docker_push("notes-app", "latest")
                }
            }
        }
        stage('Deploy'){
            steps {
                script{
                    docker_compose()
                }
            }
        }
    }
}
