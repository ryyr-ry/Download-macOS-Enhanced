---
name: Bug Report
about: Create a report to help us improve the template
title: "[BUG] A brief, descriptive title of the bug"
labels: bug
assignees: ''

---

**Thank you for reporting a bug!**
Please remember that you should be running the workflow in **your own repository** created from this template, not in the original `ryyr-ry/Download-macOS-Enhanced` repository.

---

**1. Describe the bug**
A clear and concise description of what the bug is.
*(e.g., "The ISO finalization step fails with a 'resource busy' error.")*

**2. To Reproduce**
Steps to reproduce the behavior in your repository:
1. Go to the 'Actions' tab.
2. Run the `Generate macOS Installer` workflow.
3. Use the following inputs:
   - **macOS Version:** `(e.g., Sonoma v14.5 or manual input)`
   - **File Type:** `(e.g., ISO)`
   - **Create Release Draft?:** `(e.g., true)`
4. The workflow fails at the '...' step.

**3. Expected behavior**
A clear and concise description of what you expected to happen.
*(e.g., "I expected the workflow to complete successfully and create a release draft.")*

**4. Link to the failed workflow run in YOUR repository**
This is the most important piece of information for debugging. Please provide a direct link to the failed workflow run.
*   **Example:** `https://github.com/YourUsername/your-repo-name/actions/runs/1234567890`

**5. Your Environment (please complete the following)**
*   **Repository URL:** `[Link to your repository, e.g., https://github.com/YourUsername/your-repo-name]`
*   **Commit Hash used:** `(Optional but helpful. You can find this on your repository's main page.)`

**6. Additional context**
Add any other context about the problem here, such as screenshots or specific error messages from the logs.