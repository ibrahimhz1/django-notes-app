@Library("Shared") _
pipeline{
    
    agent { label "agent-max" }
    
    stages{
        
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code"){
            steps{
                script{
                    checkout_code("https://github.com/ibrahimhz1/django-notes-app.git", "main")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    docker_build("notes-app", "latest", "ibrahimcentra")
                }
            }
        }
        stage("Test"){
            steps{
                echo "This is testing the code ..."
            }
        }
        stage("Push"){
            steps{
                script{
                    docker_push("notes-app", "latest", "ibrahimcentra")
                }
            }
        }
        stage("Deploy"){
            steps{
                script{
                    docker_compose()
                }
            }
        }
    
    }
}
