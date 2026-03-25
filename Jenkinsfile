@Library("shared") _
pipeline{
    
    agent {label 'shivam'}
    stages{
        stage("hello")
        {
            steps{
                script{
                    hello()
                }
            }
        }
        stage("code")
        {
            steps{
                script{
                    clone("https://github.com/ShivamPatidar24/django-notes-app.git/", "main")
                }
            }
        }
        stage("build")
        {
        steps{
                script{
                    build("notes-app", "latest")
                }
                
            }
        }
        stage("push in dockerpub")
        {
            steps{
                script{
                    push("notes-app","latest", "shivampati741")
                }
                
            }
        }
        stage("deploy")
        {
            steps
            {
                echo "this is deploy the code"
                sh "docker compose up -d"
            }
        }
    }
}
