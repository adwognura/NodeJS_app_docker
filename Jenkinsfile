pipeline {
    agent any 
    
        stages {
            stage("Clone Code") {
                steps {
                    echo("Cloning the code from github repo...")
                    git url: "https://github.com/adwognura/NodeJS_app_docker.git", branch:"main"
                }
            }
            stage("Build Docker") {
                steps {
                    echo("Building the docker image...")
                    sh 'docker build -t nodejs_docker .'
                }
            }
            stage("Push to Docker Hub") {
                steps {
                    echo "Pushing the Docker image to Docker Hub"
                withCredentials([usernamePassword(credentialsId: "dockerhub", passwordVariable: "dockerHubPass", usernameVariable: "dockerHubUser")]) {
                    sh "docker tag nodejs_docker ${env.dockerHubUser}/nodejs_docker:latest6"
                    sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
                    sh "docker push ${env.dockerHubUser}/nodejs_docker:latest6"
                }
            }
        }
         stage("Run docker image") {
             steps {
                 echo "Run docker image"
                 sh 'docker run -p 3000:3000 -d adwognura98/nodejs_docker:latest6'
             }
        }
            
    }
}
