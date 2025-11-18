<div align="right">

[English](./README.md) | [日本語](./README.ja.md)

</div>

# Download-macOS-Enhanced

A GitHub Action workflow to generate macOS installers directly from Apple's servers.

This project is a heavily modified and enhanced fork of the work from [Comp-Labs/Download-macOS](https://github.com/Comp-Labs/Download-macOS).

## ⚠️ Important Notice

This workflow consumes significant compute resources. To avoid concentrating the load on a single repository and to respect GitHub's Terms of Service, **please do not fork this repository directly.** Instead, please follow the steps below to create a new repository from this template. Additionally, avoid running the workflows excessively in a short period.

For details on GitHub Actions billing and usage limits, please refer to the [official documentation](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions).

## 🚀 Getting Started

### Step 1: Create Your Own Repository from This Template

1.  Click the green **`Use this template`** button at the top of this page and select **`Create a new repository`**.
2.  Choose a name for your new repository (e.g., `my-macos-factory`).
3.  Click the **`Create repository`** button. You now have a complete copy of this project in your own GitHub account.

### Step 2: (Required) Configure Repository Variables

Before running the workflows, you must first register your repository name and username as variables.

1.  In your newly created repository, navigate to the **`Settings`** tab.
2.  In the left sidebar, select **`Secrets and variables`** > **`Actions`**.
3.  Switch to the **`Variables`** tab and click the **`New repository variable`** button.
4.  Create the following **two variables** precisely as described:

    *   **First variable:**
        *   **Name:** `REPO_OWNER`
        *   **Value:** `Your GitHub username` (e.g., `your-id`)
    *   **Second variable:**
        *   **Name:** `REPO_NAME`
        *   **Value:** `The repository name you chose in Step 1` (e.g., `my-macos-factory`)

### Step 3: (Recommended) Enable the Options List Update Feature

To use the feature that easily updates the list of downloadable macOS versions, the workflow needs a Personal Access Token (PAT) to push changes to your repository.

1.  **Create a Personal Access Token (PAT).**
    *   Follow the [official GitHub guide](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic) to create a **Classic** PAT.
    *   Under **`Select scopes`**, you **must** check the boxes for **`repo`** and **`workflow`**.
    *   The generated token string (starting with `ghp_...`) **is displayed only once.** Be sure to copy and save it in a secure place.

2.  **Add the PAT as a Repository Secret.**
    *   In your repository, go to `Settings` > `Secrets and variables` > `Actions`.
    *   Ensure the **`Secrets`** tab is selected, and then click the **`New repository secret`** button.
    *   For **Name**, enter `AUTO_COMMIT_TOKEN`.
    *   In the **Secret** field, paste the PAT string you just copied.
    *   Click `Add secret` to save.

All configuration is now complete.

## ⚙️ How to Use the Workflows

*   **To Update the Version List:**
    From the `Actions` tab, manually run the `Update macOS Installer Options` workflow. If configured correctly, this workflow will update the choices in `generate-installer.yml` and commit the changes automatically.
    
    *(Note: You can also enable daily automatic updates by uncommenting the `schedule` block in the `update-options.yml` file. However, please be mindful of GitHub Actions usage limits.)*

*   **To Generate an Installer:**
    From the `Actions` tab, run the `Generate macOS Installer` workflow. Select a version from the list or enter one manually, choose your desired file type, and then run the workflow. The generated file will be available as a downloadable artifact on the workflow summary page.

## 💡 Download Tip

Downloading large files from GitHub can sometimes be slow with a standard web browser. For a faster and more robust download experience, we recommend using a download manager that supports parallel connections, such as [aria2](https://github.com/aria2/aria2).

## ⚖️ Disclaimer

This project is provided for educational and experimental purposes. The creator assumes no responsibility for any consequences arising from the use or execution of these workflows. Please use it at your own risk and avoid excessive execution.