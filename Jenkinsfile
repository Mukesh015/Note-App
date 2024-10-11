@Library("Shared") _
pipeline {
    agent { label "mukesh-agent"}
    stages {
        stage('clone'){
            steps{
                script{
                    clone("https://github.com/Mukesh015/Note-App.git","main")
                }
            }
        }
        stage('build'){
            steps{
                 script{
                    docker_build("notes-app","latest","mukeshgupta007")
                }
            }
        }
        stage('push to docker hub'){
            steps{
                  script{
                    docker_push("notes-app","latest","mukeshgupta007")
                }
            }
        }
        stage('deploy'){
            steps{
                 sh "docker compose up -d"
            }
        }
     }
 }
