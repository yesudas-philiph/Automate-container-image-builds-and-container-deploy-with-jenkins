# Automate-container-image-builds-and-container-deploy-with-jenkins
Automatically creates container from newly created docker image

when developer commit a code change an alert is send to jenkins via the webhook
when the alert is received at the jenkins it will invoke ansible

trigger type used here
>GitHub hook trigger for GITScm polling

The project is configured in the jenkins with ansible
source code is set to git
trigger is set github webhook
ansible playbook details are configured in build area

The playbook has two parts one for build server where the new container image is created when an git changes status, this can be captured by commit changes. The process of detecting git change and invoking playbook execution can be automated by forwarding commit change alert/notification to jenkins, following will invoke the ansible to execute the playbook configured.

The first part of the playbook is solely for creating a new container image based on the git repo files and pushing it to the docker hub, also cleans up the image stored in the build server. The setup for loagging into the docker hub account and looging out the docker hub is also added. The important packages such as ansible, docker, git, python package manager pip and docker-py (Python library for the Docker Engine API) , jenkins etc.. are requird here.

the second part of the playbook pull the new image from the docker hub and creates a new container, new container is created only when a new image is pulled from the docker hub.


### git webhook:
    
>When one of those events is triggered, we'll send a HTTP POST payload to the webhook's configured URL.

### Jenkins:
>is an open source automation server. It helps automate the parts of software development related to building, testing, and deploying, facilitating continuous integration and continuous delivery. It is a server-based system that runs in servlet containers


![image](https://github.com/yesudas-philiph/Automate-container-image-builds-and-container-deploy-with-jenkins/blob/main/diagram.jpeg)
