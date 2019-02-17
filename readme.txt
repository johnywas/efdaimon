INFO:
** For the environment set up and implementation has been used a cloud VM CentOS7 with Docker version 18.06.0-ce.
** Project repository: https://github.com/johnywas/efdaimon.git
** Image repository: efdaimon/testcase:appimage
** Dockerfile and docker-compose files: efdaimon/Dockerfile/Dockerfile
********************************************************************************************************************

Please see below instructions to run the environment of the website services stack in a Swarm cluster.

- Runs container from image efdaimon/testcase:appimage:
		
	docker run -d --name appcontainer -p 80:80 efdaimon/testcase:appimage
	curl http://localhost  #visit the hosted website from the Docker container having centos with apache

- Builds and deploys services from the compose-file on the host if ports are available:

	docker-compose up -d
	pip install docker-compose  #requires docker-compose (version 1.23.2)

  Check all containers are up and working:
	curl http://localhost:81 #website
	curl http://localhost:82 #website
	curl http://localhost    #proxy

- Build webstack services from the docker-compose to the workers of a Swarm cluster:

	docker stack deploy --compose-file docker-compose.yml webstack