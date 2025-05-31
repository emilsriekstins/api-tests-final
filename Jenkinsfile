pipeline {
    agent any
    triggers {
        pollSCM('*/1 * * * *')
    }
    stages {
         stage('build-docker-image') {
            steps {
               buildDockerImage()
            }
        }
    }
}

def buildDockerImage(){
    echo "Building of application is starting.."
    sh "docker build -t emilsriekstins/api-tests:latest ."

    echo "Pushing image to docker registry.."
    sh "docker push emilsriekstins/api-tests:latest"
}
