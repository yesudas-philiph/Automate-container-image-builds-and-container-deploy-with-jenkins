# Automate-container-image-builds-and-container-deploy-with-jenkins
Automatically creates container from newly created docker image with jenkins

when developer make changes or commit a code change the an alert is send to jenkins via the webhook
when the alert is received at the jenkins it will automatically start the build process
build is configured to start when the webhook send an alert

>GitHub hook trigger for GITScm polling

The item or project is configured in the jenkins with ansible
source code is set to git
trigger is set github webhook
code location details are specified in build area

The playbook has two parts on for build server where the new container image is created and pushed to docker hub, deletes the image in the build server

the second part of the playbook pull the image from the docker hub and creates a new container, new container created only when new image is pulled


### git webhook:
    
>When one of those events is triggered, we'll send a HTTP POST payload to the webhook's configured URL.

### Jenkins:
>is an open source automation server. It helps automate the parts of software development related to building, testing, and deploying, facilitating continuous integration and continuous delivery. It is a server-based system that runs in servlet containers


![image](https://github.com/yesudas-philiph/Automate-container-image-builds-and-container-deploy-with-jenkins/blob/main/diagam.jpeg)
