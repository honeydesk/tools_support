# **CI/CD Pipeline for Heroku Deployment using GitHub Actions and Docker**

This document outlines the steps and configurations required to set up a Continuous Integration/Continuous Deployment (CI/CD) pipeline for deploying a web application to Heroku using GitHub Actions and Docker.

---

## **1. GitHub: Version Control and Repository Hosting**

Your application's source code is maintained on a Git repository hosted on GitHub.

* **Repository Management:** Ensure your application's source code is pushed from your local environment to your remote GitHub repository (e.g., `ml-project`).

---

## **2. Heroku: Application Setup**

* **Heroku Account & App Creation:**
    * Log in to your Heroku account.
    * Create a new application on the Heroku dashboard. This will be the target for your deployments.

---

## **3. Heroku & GitHub: Managing Secrets for Deployment**

To enable GitHub Actions to interact with your Heroku account, you need to securely expose Heroku credentials as secrets within your GitHub repository.

* **Extract Heroku Information:** Gather the following details from your Heroku account:
    * `Heroku_email`: Your Heroku account email (e.g., `honeywarid@gmail.com`)
    * `Heroku_API_key`: Your Heroku API key (found in Account Settings) (e.g., `6ce296ff-ade3-49c4-81d3-f59f28i84c12`)
    * `Heroku_APP_Name`: The exact name of your Heroku application (e.g., `ml-regression_tool2`)

* **Configure GitHub Secrets:**
    * Navigate to your GitHub repository's **Settings > Secrets and variables > Actions**.
    * Add new repository secrets for each of the extracted Heroku details. These secrets will be securely available to your GitHub Actions workflows.

---

## **4. GitHub: Defining the CI/CD Workflow (`main.yaml`)**

The core of your CI/CD pipeline is defined in a GitHub Actions workflow file, typically named `main.yaml`, located within the `.github/workflows/` directory of your repository.

* **Workflow Definition:**
    * Create the file `.github/workflows/main.yaml`.
    * This YAML file specifies the automated steps, triggers, jobs, and actions for your deployment pipeline.
    * It will contain the logic for building your Docker image and deploying it to Heroku.

---

## **5. GitHub: Triggering and Monitoring the CI/CD Pipeline**

Once your `main.yaml` is configured, you can initiate and monitor your deployment.

* **Initial Workflow Execution:**
    * **Manual Trigger:** You can manually trigger the workflow by navigating to the "Actions" tab in your GitHub repository and clicking "Run workflow" or a similar "build" button.
    * **Troubleshooting:** It's common for the initial execution to fail due to configuration issues. Review the workflow logs in GitHub Actions to identify and resolve any build or deployment failures.

* **Successful Re-execution:**
    * After updating your code and addressing any errors, re-run the failed job(s) or the entire workflow.
    * A successful execution indicates that your application has been successfully built and deployed to Heroku.

---

## **6. GitHub & Heroku: Verification of the successful running of the application**

After initiating a deployment, it's crucial to verify its success on both GitHub and Heroku.

* **Verify on GitHub:**
    * Check the "Actions" tab in your GitHub repository to confirm that the CI/CD pipeline executed successfully and the deployment job completed without errors.

* **Verify on Heroku:**
    * Access your Heroku application's URL to ensure that the web application is up and running as expected.

---

## **7. GitHub: Automated Continuous Deployment**

One of the key benefits of a CI/CD pipeline is automated deployments.

* **Automatic Triggers:** Once the pipeline is established, subsequent code pushes (e.g., `git push`) to the configured branch (often `main` or `master`) in your GitHub repository will automatically trigger the defined GitHub Actions workflow.
* **Seamless Updates:** This automation ensures that any changes made in your GitHub repository are automatically built and redeployed to your Heroku application, providing continuous integration and deployment.

---

## **8. Heroku: Application Management**

* **Stop the Heroku App:** If needed, you can stop your Heroku application through the Heroku dashboard.
* **Delete the Heroku App:** To remove your application entirely, you can delete it from your Heroku dashboard.

---

