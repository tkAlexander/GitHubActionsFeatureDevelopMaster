This document provides guidelines for contributing to the repository and deploying changes to various environments.

## Table of Contents

1. [Contributing](#contributing)
    - [Branching Model](#branching-model)
    - [Making Changes](#making-changes)
    - [Pull Requests](#pull-requests)
2. [Deployment](#deployment)
    - [Deployment Environments](#deployment-environments)
    - [Deployment Process](#deployment-process)

## Contributing

### Branching Model

This project follows a Git branching model based on the Gitflow Workflow. The main branches are:

- **master**: Represents the latest stable version of the project. Production-ready changes are merged into this branch.
- **develop**: Integration branch where feature branches are merged for testing before deployment.
- **release**: Branch used for preparing releases. Release candidates are created from this branch for testing.
- **feature/**: Branches created for developing new features or fixing specific issues. Each feature or fix should have its own feature branch.

### Making Changes

To contribute to the project, follow these steps:

1. Clone the repository: `git clone <repository-url>`
2. Create a new feature branch from `develop`: `git checkout -b feature/<feature-name>`
3. Make changes and commit them to your feature branch: `git commit -am "Brief description of changes"`
4. Push your feature branch to the remote repository: `git push origin feature/<feature-name>`
5. Open a pull request targeting the `develop` branch.
6. Discuss and review changes with team members.
7. After approval, merge your pull request into `develop`.

### Pull Requests

When opening a pull request:

- Provide a descriptive title and detailed description of the changes.
- Reference relevant issues or feature requests if applicable.
- Ensure the code passes all tests and follows coding standards.
- Request reviews from team members.

## Deployment

### Deployment Environments

The docker images are deployed to multiple environments for testing and production use:

- **Development**: Used for testing new features and changes. Deployed automatically from `feature` and `develop` branches.
- **Test**: Pre-production environment for final testing before release. Deployed from release candidates on the `release` branch.
- **Production**: Live environment accessible to end-users. Deployed from the `master` branch.

### Deployment Process

To deploy changes to different environments:

1. **Development**: Changes merged or commited into `feature` and `develop` branches trigger automatic deployment to the development environment.
2. **Test**: When preparing for release, create a release candidate from the `develop` branch and merge it into the `release` branch. Deployment to test environment is automatically triggered from the `release` branch.
3. **Production**: Once testing in test is complete and approved, merge the `release` branch into `master` and deploy to the production environment.
