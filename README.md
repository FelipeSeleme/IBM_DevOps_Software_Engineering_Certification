# Customer Accounts Microservice - DevOps Capstone Project

![Build Status](https://github.com/FelipeSeleme/devops-capstone-project/actions/workflows/ci-build.yaml/badge.svg)

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python 3.9](https://img.shields.io/badge/Python-3.9-green.svg)](https://shields.io/)

## Project Overview

This repository showcases my completed Capstone project from the [**IBM DevOps and Software Engineering Professional Certificate**](https://www.coursera.org/account/accomplishments/professional-cert/UPCQ77XOVJHG) on Coursera. The project is a fully functional **Customer Accounts microservice**, designed and deployed using modern DevOps practices and tools. It demonstrates my ability to build, test, secure, and deploy a RESTful microservice while integrating Agile methodologies, Test-Driven Development (TDD), Continuous Integration/Continuous Deployment (CI/CD), and Kubernetes orchestration.

The microservice manages customer account data (e.g., name, email, address) and provides REST API endpoints for **CREATE**, **READ**, **UPDATE**, **DELETE**, and **LIST** operations, all while maintaining **95% code coverage** through rigorous testing. This project highlights my skills in software development, cloud-native deployment, and DevOps automation, making it a strong addition to my professional portfolio.

---

## What I Built

This project was developed over multiple sprints, each focusing on specific aspects of DevOps and software engineering. Here’s a breakdown of what I accomplished:

1. **Agile Project Management**  
   - Created a GitHub repository and Kanban board to manage the project.  
   - Wrote well-structured **user stories** and built a product backlog to define the microservice’s features.  
   - Planned and executed sprints, assigning story points and tracking progress from "Backlog" to "Closed."

2. **Test-Driven Development (TDD)**  
   - Developed a Flask-based RESTful microservice using Python 3.9.  
   - Wrote unit tests for all CRUD operations (READ, UPDATE, DELETE, LIST) before implementing the code.  
   - Achieved **95% code coverage** using `nosetests` and the `coverage` tool, ensuring reliability.

3. **Continuous Integration (CI)**  
   - Configured **GitHub Actions** workflows to automate building, testing, and linting on every push or pull request.  
   - Integrated **Flake8** for code quality checks and enforced testing standards in the CI pipeline.

4. **Security Enhancements**  
   - Added **Flask-Talisman** to implement secure HTTP headers and **Flask-CORS** for Cross-Origin Resource Sharing policies.  
   - Wrote and tested security features using TDD, ensuring the microservice meets modern security standards.

5. **Containerization and Deployment**  
   - Created a **Dockerfile** to containerize the microservice into an "accounts" image.  
   - Pushed the image to the **IBM Cloud Container Registry** and manually deployed it to an OpenShift/Kubernetes cluster.  
   - Set up a **PostgreSQL** service in OpenShift as the application’s database, using YAML manifests for deployment.

6. **Continuous Deployment (CD)**  
   - Built a **Tekton pipeline** to automate deployment to Kubernetes/OpenShift.  
   - The pipeline handles cloning, linting, testing, building, and deploying the service, eliminating manual steps.

7. **Documentation and Peer Review**  
   - Organized deliverables (screenshots, URLs, code) for submission and conducted a peer review using a rubric.

---

## Key Skills Demonstrated

This project required a diverse set of technical and professional skills, which I successfully applied:

- **Software Development**: Proficient in Python, Flask, and REST API design using the Model-View-Controller (MVC) pattern.  
- **Test-Driven Development (TDD)**: Skilled in writing unit tests and achieving high code coverage to ensure quality.  
- **DevOps Practices**: Expertise in CI/CD pipelines, containerization (Docker), and Kubernetes/OpenShift deployment.  
- **Agile Methodologies**: Experienced in managing projects with Kanban boards, user stories, and sprint planning.  
- **Cloud Technologies**: Knowledge of IBM Cloud Container Registry and OpenShift for cloud-native applications.  
- **Security**: Ability to implement secure coding practices, including HTTP headers and CORS policies.  
- **Automation**: Proficient in automating workflows with GitHub Actions and Tekton pipelines.  
- **Version Control**: Strong command of Git for branching, pull requests, and collaboration.

---

## Project Structure

The microservice follows a clean **Model-View-Controller (MVC)** architecture:

```text
├── service         <- Microservice package
│   ├── common/     <- Common log and error handlers
│   ├── config.py   <- Flask configuration object
│   ├── models.py   <- Database models and business logic
│   └── routes.py   <- REST API routes
├── setup.cfg       <- Tools setup config
└── tests           <- Unit tests
    ├── factories.py            <- Test factories
    ├── test_cli_commands.py    <- CLI tests
    ├── test_models.py          <- Model unit tests
    └── test_routes.py          <- Route unit tests
```

### Data Model

The `Account` model includes:

| Name          | Type        | Optional |
|---------------|-------------|----------|
| id            | Integer     | False    |
| name          | String(64)  | False    |
| email         | String(64)  | False    |
| address       | String(256) | False    |
| phone_number  | String(32)  | True     |
| date_joined   | Date        | False    |

---

## How to Run Locally

If you'd like to explore this project on your machine:

### Prerequisites
- [Docker Desktop](https://www.docker.com/products/docker-desktop)
- Python 3.9
- Git

### Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/FelipeSeleme/devops-capstone-project.git
   cd devops-capstone-project
    ```

2. Set up the Python virtual environment:
    ```bash
   source bin/setup.sh
    ```
3. Install dependencies:
    ```bash
   make install
    ```
4. Start the PostgreSQL container:
    ```bash
   make db
    ```
5. Run the microservice:
    ```bash
   python service/routes.py
    ```


### Local Kubernetes Development
For a full local Kubernetes experience:
1. Install [K3D](https://k3d.io/), [Tekton](https://tekton.dev/), and cluster tasks:
   ```bash
   make cluster
   make tekton
   make clustertasks
   ```
2. Deploy the service using the provided Tekton pipeline.

## Why This Matters

This project is a testament to my ability to bridge software development and operations, delivering a production-ready microservice with automation, scalability, and security in mind. It reflects real-world DevOps workflows and showcases my readiness to tackle complex engineering challenges.

Feel free to explore the code, workflows, and deployment configurations in this repository!

---

## Author

Felipe Seleme Ribeiro - DevOps Engineer and Software Developer

## License

Licensed under the Apache License. See [LICENSE](LICENSE)

## Acknowledgments

This project was completed as part of the IBM DevOps and Software Engineering Professional Certificate, guided by instructor [John Rofrano](https://www.coursera.org/instructor/johnrofrano).

