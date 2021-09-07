# history-excerptor-chart

### Overview
This repository contains history-excerptor chart templates that use [history-excerptor](https://github.com/epam/edp-ddm-history-excerptor) image in order to run Kubernetes job in history-excerptor Jenkins pipeline.

### Usage
This repository is used to keep history-excerptor Helm chart files that are applied in history-excerptor Jenkins pipeline to for generate an excerpt.

###### Prerequisites
Jenkins operator, Gerrit operator, Codebase operator deployed in Kubernetes cluster;
[history-excerptor image](https://github.com/epam/edp-ddm-history-excerptor).

###### Steps
In order to build an image from the source, perform the following:

Make your changes in Dockerfile. Build a Docker image from the current project directory using the command below:
```bash
docker build . -t history-excerptor-chart:latest
```
Push the newly created Docker image to your public or private Docker image hub:
```bash
docker push yourdockerhub/history-excerptor-chart:latest
```
To deploy execute the command below:
```bash
helm upgrade --install history-excerptor-chart deploy-templates --set namespace=<your-namespace> --set image.name=<your-image>
```

### Licensing
The history-excerptor-chart is Open Source software released under the [Apache 2.0 license](https://www.apache.org/licenses/LICENSE-2.0).
