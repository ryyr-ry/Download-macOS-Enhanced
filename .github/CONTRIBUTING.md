# Contributing to Download-macOS-Enhanced

First off, thank you for considering contributing! We truly appreciate your help in making this project better.

This project follows a slightly different contribution workflow due to its nature as a GitHub Actions template. Instead of forking, you will create your own repository from the template to test your changes.

## Contribution Workflow

1.  **Create your own repository from the template.**
    *   Click the **`Use this template`** button on the main repository page and create a new repository in your own account. This will be your personal development and testing environment.

2.  **Configure your new repository.**
    *   Follow the "Getting Started" steps in the `README.md` to set up your repository variables (`REPO_OWNER`, `REPO_NAME`) and secrets (`AUTO_COMMIT_TOKEN`). This is crucial for running the workflows.

3.  **Clone your new repository (not a fork).**
    *   `git clone https://github.com/YourUsername/your-new-repo-name.git`

4.  **Create a feature branch.**
    *   `git checkout -b your-feature-name`

5.  **Make your changes.**
    *   Improve the code, fix a bug, or enhance the documentation. You can test your changes by running the workflows in your own repository, ensuring everything works as expected.

6.  **Commit and push your changes.**
    *   `git commit -m "feat: Describe your awesome new feature"`
    *   `git push origin your-feature-name`

7.  **Open a Pull Request to the original repository.**
    *   Navigate back to the original repository (`ryyr-ry/Download-macOS-Enhanced`).
    *   Go to the "Pull requests" tab and click **"New pull request"**.
    *   You should see a banner that says "Compare across forks". Click it.
    *   For the "head repository", select your new repository (`YourUsername/your-new-repo-name`) and choose your feature branch.
    *   Provide a clear title and description for your pull request, explaining the changes you've made.

This process ensures that all testing is done within your own account's resource limits and maintains a clean and consistent workflow for all users and contributors.

## Reporting Bugs

If you find a bug and don't wish to fix it yourself, please [open an issue](https://github.com/ryyr-ry/Download-macOS-Enhanced/issues/new?template=bug_report.md). Be sure to provide as much detail as possible, including logs from your workflow runs, so we can reproduce and fix the problem.