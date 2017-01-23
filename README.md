![AyeAye](https://github.com/shippableSamples/node-build-push-docker-hub/blob/master/public/resources/images/captain.png)

# Docker Build, Continuous Integration, and Deployment to Kubernetes for a Node JS application
[![Run Status](https://api.shippable.com/projects/5885ecca11c45a1000af5760/badge?branch=master)](https://app.shippable.com/projects/5885ecca11c45a1000af5760)
[![Coverage Badge](https://api.shippable.com/projects/5885ecca11c45a1000af5760/coverageBadge?branch=master)](https://app.shippable.com/projects/5885ecca11c45a1000af5760)


A simple Node JS application with unit tests and coverage reports using mocha
and istanbul. It also does a docker build once CI posses and then pushes the image
to Docker Hub. Every time the image on Docker Hub changes, it is deployed to a Kubernetes pod running on Amazon EC2.

## Run CI for this repo on Shippable
* Fork this repo into your local repo
* Login into the [Continuous Integration Service](wwww.shippable.com)
* Create an [integration](http://docs.shippable.com/integrations/imageRegistries/dockerHub/) on shippable to your Docker Hub
* All CI configuration is in `shippable.yml`
* Follow these [CI Setup Instructions](http://docs.shippable.com/ci/runFirstBuild/) if you have never used Shippable CI Service
* You should be able to run a manual build or webhook build on commit

## Add Continuous Delivery pipelines to deploy to Kubernetes

* Create an integration for [Kubernetes](http://docs.shippable.com/integrations/containerServices/kubernetes/)
* All pipeline config is in `shippable.resources.yml` and `shippable.jobs.yml`. Check these files and update config wherever the comment asks you to replace with your specific values
* Follow instructions to add your [Continuous Deployment pipeline](http://docs.shippable.com/tutorials/pipelines/howToAddSyncRepos/)
* Right click on the manifest job in the SPOG view and run the job.
* Your app should be deployed to your Kubernetes pod.
* Follow instructions to [connect your Continuous Integration project to your Continuous Delivery pipelines](http://docs.shippable.com/tutorials/pipelines/connectingCiPipelines/)

Your end to end pipeline is ready! From here on, any change you make to the application will be deployed to your Kubernetes pod.

### CI Console Log
![CI Console Log](https://github.com/shippableSamples/node-build-push-docker-hub/blob/master/public/resources/images/console-log.jpg)

### CI Integration View
![CI Integration View](https://github.com/shippableSamples/node-build-push-docker-hub/blob/master/public/resources/images/trigger-deploy-kubernetes.jpg)

### CD Pipeline
![CD Pipeline](https://github.com/shippableSamples/node-build-push-docker-hub/blob/master/public/resources/images/deployment-pipeline-to-kubernetes.jpg)
