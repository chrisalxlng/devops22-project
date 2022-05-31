# Project Concept: 932459

> **This concept is an initial version/work-in-progress and will be updated during the lifecycle of this project.**

### Goal

- Goal of the project work is to deploy an application in a cloud or cloud-simulated environment by providing all the services required for the application to function properly in multiple environments and an automated manner
- The [app](./deployable/) to be deployed is a simple ToDo application cloned from [this repo](https://github.com/lucendio/lecture-devops-app)

### Target Environments

Each of the following environment is represented by its own branch in this repository:

- Production (`prod`)
  - The `prod` environment is the place where real-world customers use and depend on this application which is why this environment needs to be stable
- Staging (`staging`)
  - The `staging` environment is almost an exact replica of the `prod` environment and is used to test all aspects of the application in a scenario where outer conditions resemble the real-world use case of the `prod` environment
- Development (`dev`)
  - The `dev` environment is is used during development and can therefore be unstable at times

### Tech Stack

- [GitHub Actions](https://github.com/features/actions)
  - Integrated CI/CD solution by GitHub
  - Represents platform of CI/CD Pipeline
- [Docker](https://www.docker.com)
  - Represents containerization tool
- [AWS](https://aws.amazon.com/)
  - Represents platform where all environments will be hosted

### Automation Processes & Application Lifecycle

- Development workflows
  - `push` -> `master`, `pull_request` (feature branch) -> `master`:
    - Setup of application
    - Install dependencies
    - Run client tests
    - Build application
    - Deploy to `dev` environment
- Staging workflows
  - `pull_request` (`master`) -> `staging`:
    - Setup of application
    - Install dependencies
    - Run client tests
    - Build application
    - Deploy to `staging` environment
- Production workflows
  - `pull_request` (`staging`) -> `prod`:
    - Setup of application
    - Install dependencies
    - Run client tests
    - Build application
    - Deploy to `staging` environment

All workflows that do not appear in the previous section are not allowed.

## Links

- [Repository of deployable app](https://github.com/lucendio/lecture-devops-app)
- [Project Conecpt Requirements](https://github.com/lucendio/lecture-devops-infos/blob/main/assignments/deliverables/project_concept.md)
- [Project Grading](https://github.com/lucendio/lecture-devops-infos/blob/main/grading.md)
