# The Pipeline

The pipeline is run with CircleCI and consists of three jobs:

- [Test and Build](#test-and-build)
- [Hold](#hold)
- [Deploy](#deploy)

## Test and Build

- Create docker image
- Install NodeJS and Yarn
- Get source code and submodules from Git
- Install dependencies for backend and frontend
- Run tests for backend and frontend
- Build the application

## Hold

Requires test & build job to run and succeed

- Wait for approval

## Deploy

Requires the hold job to be approved

- Create docker image
- Install NodeJS and Yarn
- Get source code and submodules from Git
- Install dependencies for backend and frontend
- Build the application
- Deploy the application

The difference between the test & build and deploy job is that no tests are run in the deploy job and it needs the test & build job to run first

![Diagram](../pipeline-diagram.png)
