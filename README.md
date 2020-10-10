# jekins-test

docker container run \
    -p 8080:8080 \
    -v jenkins:/var/jenkins_home \
    --name jenkins-local \
    jenkins/jenkins:lts