## Description
The objective of this repo is to create a docker-compose configuration to run Prometheus, Alertmanager and NGINX.

#### Pre-requesites
Since this experiment has been carried out on a MAC machine, ensured that following softwares are installed.
##### Git:
- brew install git
##### Docker Desktop for Mac:
https://docs.docker.com/desktop/mac/install/
- Note: Post installation, docker works command line as well. UI is friendly and easy to navigate between containers, logs and to launch them locally.

#### Aim:
Configure Prometheus, alertmanager and nginx on the localhost and when the NGNIX is down for any reason then it should register in Prometheus system which inturn should send an alert to Alertmanager.

#### Method:
 In this section, lets discuss about the method followed to achive our aim.

