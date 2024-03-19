# hugo-mock-landing-page

Mock landing page for myLearning Companion, an app to support students in learning new concepts, hosted on a domain.

Website: https://mylearning.buzz

Time Log: https://docs.google.com/spreadsheets/d/15VUJiCqIrWVMc-coeLHGMa3XyGXW4hZrqhx5jgnHb8U/edit#gid=0

Author: Eshaan Chichula

## Automated Build and Deployment with GitHub Actions

This repository uses a GitHub Actions workflow to automate the build and deployment process for the Hugo website. The workflow is defined in the `.github/workflows/gh_pages_deployment.yml` file.

### Workflow Overview

Whenever changes are pushed to the `main` branch, the following steps are executed:

1. **Check Out Source Repository**: The repository code is checked out, including any submodules (e.g., Hugo themes) and fetching the entire commit history for certain Hugo features.

2. **Initialize Hugo Environment**: The workflow sets up the Hugo environment, using version 0.123.4 and enabling extended Hugo functionality.

3. **Compile Hugo Static Files**: The `hugo` command is executed to build the static website, including draft content (`-D` flag), enabling garbage collection (`--gc`), and minifying the output (`--minify`).

4. **Publish to GitHub Pages**: The built website is published to the `gh-pages` branch, which is used by GitHub Pages to serve the site. The deployment is configured with a custom user name and email for the commit.

### Benefits

Using this automated GitHub Actions workflow provides several advantages:

- **Continuous Integration/Continuous Deployment (CI/CD)**: Every time changes are pushed to the `main` branch, the site is automatically rebuilt and deployed, ensuring the live site is always up-to-date.

- **Consistent Builds**: By specifying the Hugo version and environment in the workflow, consistent builds are ensured across different machines and environments.

- **Version Control**: The deployment process is version-controlled along with the site's source code, making it easier to track changes and collaborate with team members.

- **Secure Deployments**: The workflow can access and use encrypted secrets (like deployment keys or API tokens) securely, without exposing sensitive information in the repository.

With this automated workflow in place, maintaining and deploying the Hugo website becomes a streamlined process, saving time and reducing the potential for manual errors.

