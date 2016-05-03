# Jenkins 2.0 with Docker Compose

Pre-built solution for Jenkins 2.0 and a Node.js slave through Docker Compose

This repository accompanies blog post, please head over to the blog for instructions on setting up the build and example project:

> [Jenkins 2.0 first impressions](http://blog.alexellis.io/jenkins-2-0-first-impressions/)

Please **Star** the repo to support the project

> #### Docker, perfect for test-driving Jenkins

> When Jenkins 2.0 was released I wanted to take it for a test drive, the perfect way to do this was through Docker. Docker means zero  commitment to installing packages and configuring your system. Even installing Java could take you on a 30-60min hour detour, Official, prebuilt images in the Docker Hub completely eliminates that and gives you near instant access to pre-packaged software.

> I started off by looking at the official instructions for starting a Jenkins 2.0 container. They give 3-4 variations of the `docker run` command but this can be made much simpler through the use of Docker Compose and a `docker-compose.yml` file.

#### Jenkins Slave Docker images:

You can pull these images straight from the public Docker Hub to be used as Jenkins slave agents.

Jenkins slave images have been trimmed down to 150mb from 650mb+ by switching to Alpine Linux. 

* [alexellis2/jenkins_nodejs_slave](https://hub.docker.com/r/alexellis2/jenkins_nodejs_slave/)

* [alexellis2/jenkins_slave](https://hub.docker.com/r/alexellis2/jenkins_slave/)

#### Supporting files:

* docker-compose.yml file with Node.js
 * [docker-compose.yml](https://github.com/alexellis/jenkins2docker/blob/master/docker-compose.yml)

* alexellis2/jenkins2slave_nodejs (Alpine Linux, node.js and SSHD)
 * [Dockerfile](https://github.com/alexellis/jenkins2docker/blob/master/slave_node_alpine/Dockerfile)

* Sample job config for featured Node.js app
 * [sample_config.xml](https://github.com/alexellis/jenkins2docker/blob/master/sample_config.xml)
