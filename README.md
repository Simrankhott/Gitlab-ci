# Python Flask - Demo Web Application

This is a simple Python Flask web application. The app provides system information and a realtime monitoring screen with dials showing CPU, memory, IO and process information.

The app has been designed with cloud native demos & containers in mind, in order to provide a real working application for deployment, something more than "hello-world" but with the minimum of pre-reqs. It is not intended as a complete example of a fully functioning architecture or complex software design.

Typical uses would be deployment to Kubernetes, demos of Docker, CI/CD (build pipelines are provided), deployment to cloud (Azure) monitoring, auto-scaling

## Screenshot

<p align="center">
  <img width="957" alt="Screenshot 2023-06-07 115548" src="https://github.com/Simrankhott/Gitlab-ci/assets/91006102/01118eb5-0a07-4c13-84a9-fe43a69961c5">
</p>
<br>

<p align="center">
  <img width="960" alt="Screenshot 2023-06-07 115220" src="https://github.com/Simrankhott/Gitlab-ci/assets/91006102/164dc1a4-e929-467c-9722-f6c296f5557f">
</p>
<br>

<p align="center">
  <img width="958" alt="Screenshot 2023-06-07 115323" src="https://github.com/Simrankhott/Gitlab-ci/assets/91006102/3af36a59-b213-41d6-a506-cd90edeb64bf">
</p>
<br>

<p align="center">
  <img width="960" alt="Screenshot 2023-06-07 115444" src="https://github.com/Simrankhott/Gitlab-ci/assets/91006102/084cb315-611d-48f9-a399-0cd034b40a05">
</p>
<br>

## Building & Running Locally

### Pre-reqs

- Be using Linux, WSL or MacOS, with bash, make etc
- [Python 3.8+](https://www.python.org/downloads/) - for running locally, linting, running tests etc
- [Docker](https://docs.docker.com/get-docker/) - for running as a container, or image build and push
- [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-linux) - for deployment to Azure

Clone the project to any directory where you do development work

```
git clone https://github.com/Simrankhott/Gitlab-ci.git
```    

# Containers

Public container image is [available on GitHub Container Registry](https://github.com/users/benc-uk/packages/container/package/python-demoapp)

Run in a container with:

```bash
docker run -it -d --name python-app -p 5000:5000 simrankhot/demo-app:python-app-1.0
```

## Running in Azure App Service (Linux)

If you want to deploy to an Azure Web App as a container (aka Linux Web App), a Bicep template is provided in the [deploy](deploy/) directory

For a super quick deployment, use `make deploy` which will deploy to a resource group, temp-demoapps and use the git ref to create a unique site name

```bash
make deploy
```

## Running in Azure App Service (Windows)

Just don't, it's awful 

