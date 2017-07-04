SHELL := /bin/bash

build: build-master build-slave

build-master:
	cd master && docker build -t zulcss/jenkins-master .
build-slave:
	cd slave && docker build -t zulcss/jenkins-slave .

run-master:
	docker run -d --name jenkins \
		-p 8080:8080 -p 50000:50000 \
		-v ./master/jenkins:/etc/jenkins \
		zulcss/jenkins-master

run-slave:
	docker run -d --name jenkins-slave \
		-v /var/run/docker.sock:/var/run/docker.sock \
		zulcss/jenkins-slave
