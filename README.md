## Description
The objective of this repo is to create a docker-compose configuration to run Prometheus, Alertmanager and NGINX on local machines.

#### Pre-requesites
Ensure that following softwares are installed on local machine.
##### Git:
- brew install git (MAC)
##### Docker Desktop for Mac:
https://docs.docker.com/desktop/mac/install/
- Note: You may install on windows also, please refer to docker site for windows setup. After installation, docker CLI also work pretty well. UI is friendly and easy to navigate between containers, logs and to launch them locally. If someone wants to setup locally, you may clone this repo and from the current directory (Task) run the commands listed in the **Testing & Results** section.

#### Aim:
Configure Prometheus, alertmanager and nginx on the localhost and when the NGNIX is down for any reason then it should register in Prometheus system which inturn should send an alert to Alertmanager.

#### Method:
 In this section, lets discuss about the method followed to achive the aim.
 - Lookup the internet to find the prometheus, alert manager and ngnix docker-compose configurations.
 - Using reference [1,2], docker compose file configuration has been setup for prometheus, alert manager. Some of the configurations has been updated to make it work locally, like port number and some unused/unwanted configuration has been eliminated and updated the volumes to match with project structure.
 - Using reference [3], docker compose has been updated with ngnix configurations.

#### Testing & Results:
- Once the docker-compose.yml file is ready, run the below command to start all the containers configured inside docker-compose file.
  docker-compose up -d (Run in detached mode throuh CLI or you may start through docker desktop)
- Now, all the containers should be up and running. Check the container logs incase of any issues.  
- Launch prometheus, alert manager and ngnix on your local machine using below URLs (Ports are already configured in docker-compose.yml file)
  http://localhost:80/
  http://localhost:9090/graph
  http://localhost:9093/#/alerts
  Note: If you are using docker desktop then you can click on browse symbol and it bring up the web page automatically. 
- Now, stop the ngnix container using below command or through docker desktop.
  docker container ls (Look for ngnix container ID)
  docker stop <container_id>
- Now, the ngnix web server running locally should be down and as per the prometheus configuration it gets registered in prometheus and the alerts gets displayed   on the alertmanager UI. Screenshots showing all the outputs will be added in the appendices section.


#### References:
[1] https://docs.docker.com/config/daemon/prometheus/   
[2] https://github.com/vegasbrianc/prometheus   
[3] https://linuxiac.com/nginx-docker   

#### Useful resources:
[1] Prometheus - https://prometheus.io   
[2] Alertmanager - https://prometheus.io/docs/alerting/latest/alertmanager   
[3] Docker - https://www.docker.com   
[4] Docker Compose - https://docs.docker.com/compose   

#### Appendices:
In this section, screenshots of the outputs or any relevant configuration should be attached.   
Alert registered in Prometheus UI:
![Prometheus Alert graph](https://github.com/bpradeepchandra/Task/blob/main/images/Prometheus-graph.png?raw=true)   
   
Alert displayed on Alertmanager UI:
![Alert Manager](https://github.com/bpradeepchandra/Task/blob/main/images/Prometheus-Alerts.png?raw=true)
