## Enterprise Stack:
This project contains a setup for a CI/CD stack, along with a Log Management Stack.

### Technical Stack:
* Jenkins
* SonarQube
* Postgresql
* Graylog
* Elasticsearch
* MongoDB


### Architecture

                                                                                                                                                                             ##############
                                                                                                                                                                             # Postgresql #
                                                                                                                                                                             ##############
                                                                                                                                                                                   |
                                                                                                                                                                                   |
                                                                          push           ##########         Webhook                                                                |
                             ###################                          -------------> # Github # <----------------                                                              |
       ------------------->  #  ElasticSearch  #                          |              ##########                 |                                                              |
       |                     ###################                          |                                         |                                                              |
       |                                                                  |                                         |                                                              |
 #############                                                 ######################                            ###########              Code Quality                             |
 #  Graylog  #  <--------------------------------------------- # Spring Application #                            # Jenkins # ---------------------------------                     |
 #############                                                 ######################                            ###########                                 |                     |
       |                                                                                                                                                     |                     |
       |                    ###########                                                                                                                  #############             |
       -------------------> # MongoDB #                                                                                                                  # SonarQube # -------------
                            ###########                                                                                                                  #############

### How to use this stack:
This project contains a Docker Deployment along with Kubernetes Deployment to run Jenkins CI-CD Server,
and Sonarqube, PostgreSQL on my machine.

for Docker, you can use docker-compose to run the deployment, also you can run the deployment using Docker in Swarm Mode.
```
docker-compose -f docker/docker-ci-cd-compose.yaml
```

this stack is used by me in my daily basis work, to test, an measure my code quality. you can custome this configuration to meet you needs.
