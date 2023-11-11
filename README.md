# DockHub

This project streamlines the process of building and pushing Different Docker images to DockerHub effortlessly. By adhering to a clear commit message format (`docker-build:subdir_name`), you can trigger an automated workflow to build and publish Docker images for specific subdirectories.

## Features:

- **Automated Docker Builds:** Effortlessly trigger Docker image builds by following a standardized commit message format.

- **Directory-based Builds:** Build and push Docker images for specific subdirectories, allowing for targeted image creation.

- **Tag Management:** Automatically manage versioned tags for each build, providing clarity and traceability for your Docker images.

## Getting Started with DockHub:

To begin using DockHub and enable automated Docker builds for your subdirectories, follow these steps:

#### 1. Fork the Repository

Start by forking this repository to your GitHub account. Click on the "Fork" button at the top right of the repository page.

#### 2. Create DockerHub Access Token

Generate a DockerHub access token to allow the automated workflow to push Docker images to DockerHub on your behalf. Follow these steps:

   - Log in to your DockerHub account.
   - Navigate to Account Settings > Security > New Access Token.
   - Provide a name for your token and select the necessary scopes (e.g., `write`).
   - Click "Create" and copy the generated access token.

#### 3. Add DockerHub Access Token as a Secret

After forking the repository, navigate to your forked repository on GitHub. Then, follow these steps to add your DockerHub access token as a secret:

   - Click on "Settings" at the top of your repository.
   - In the left sidebar, click on "Secrets."
   - Click "New repository secret."
   - Name the secret `DOCKERHUB_TOKEN` and paste the DockerHub access token as the value.
   - Create another secret `DOCKERHUB_USERNAME` and fill the value with your dockerhub username
   - Click "Add secret" to save.

#### 4. Start Automated Docker Builds

Now that you've forked the repository and added the DockerHub access token as a secret, you're ready to trigger automated Docker builds. Simply create a new folder inside the fork repo and commit with the specified format (`docker-build:subdir_name`) for the subdirectory you want to build, and the workflow will take care of the rest!

## Usage:

#### Commit Message Format:
To initiate the automated Docker image build and push workflow, use the following commit message format:

- `docker-build:subdir_name`

For instance, to build and push Docker images for the "android-env-ubuntu" directory, use the commit message:

- `docker-build:android-env-ubuntu`

Streamline your Docker image deployment process with this efficient and easy-to-use GitHub workflow.



## How to Contribute:

#### ⭐ Star the Repository

If you find DockHub useful, consider starring the repository!

#### 🐞 Report Issues

Found a bug or have a suggestion? Please [open an issue](https://github.com/shaquibimdad/DockHub/issues) with detailed information. We appreciate your feedback.

#### 🛠️ Open Pull Requests

Contributions are welcome! If you want to fix a bug or enhance DockHub, open a [pull request](https://github.com/shaquibimdad/DockHub/pulls).

#### Used Actions in Workflow:

- **[build-push-action](https://github.com/marketplace/actions/build-and-push-docker-images):** Build and push Docker images


Your contributions and feedback make DockHub better for everyone! Thank you for being a part of our community. 🚀
