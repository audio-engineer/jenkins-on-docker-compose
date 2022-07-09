# Jenkins On Docker Compose

## About

There are many articles out there on the internet explaining how to use the official Jenkins Docker image, or how to run
Jenkins using Docker Compose, and this repository is nothing more than my twist on the concept.

The BlueOcean and Docker Pipeline plugins come preinstalled as part of the Jenkins image.

## Prerequisites

You need to have Docker and Docker Compose installed on your system.

## Usage

1. Copy the `.env.sample` file to `.env` and set a host port after the equal sign
2. Run `docker compose up -d`
3. Open `localhost:<your_specified_port>` in your browser and start the Jenkins setup
    1. Docker will copy the contents of the `/var/jenkins_home` directory from the Jenkins server container
       to [`./jenkins_home/`](./jenkins_home). If you open this directory during setup and navigate
       to [`./jenkins_home/secrets/initialAdminPassword`](./jenkins_home/secrets/initialAdminPassword) you will find
       your initial administrator password
4. If you want to use Jenkins CLI features, you can simply log into the Jenkins server container by
   running `docker exec -it jenkins /bin/bash`
