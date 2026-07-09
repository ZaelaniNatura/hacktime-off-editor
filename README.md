# Hackatime Off-Editor Tracker

A lightweight GitHub Actions workflow to log Hackatime heartbeats without opening an IDE or code editor. 

This tool is perfect for tracking off-editor work like Ideation, Narrative Design, or Asset Creation directly from your browser, without requiring any local setup or background processes.

## Features
* **Zero Installation:** Runs entirely in the cloud via GitHub Actions.
* **Resource Efficient:** Requires no local background processes on your device.
* **Safety Lock:** Requires an explicit confirmation checkbox to prevent accidental runs and unwanted ghost projects on your dashboard.

---

## Setup Guide

Before using this tracker, you must add your Hackatime API Key to the repository secrets so the logged time routes to your profile.

1. **Fork** this repository to your own GitHub account.
2. Retrieve your API Key from your Hackatime account settings.
3. Configure the secret in your forked repository:
   * Navigate to the **Settings** tab.
   * On the left sidebar, go to **Secrets and variables** > **Actions**.
   * Click the **New repository secret** button.
   * **Name:** `HACKTIME_API_KEY`
   * **Secret:** *[Paste your API Key here]*
   * Click **Add secret**.

---

## How to Start Tracking

> [!WARNING]  
> **Verify Your Project Name**  
> Hackatime will automatically create a new project on your dashboard if you misspell the project name. Please verify your spelling before executing. The confirmation checkbox is required to prevent accidental typos from ruining your dashboard stats.

1. Go to the **Actions** tab in your repository.
2. On the left sidebar, select the **Start Hackatime Off-Editor** workflow.
3. Click the **Run workflow** dropdown button on the right side.
4. Carefully fill out the required parameters:
   * **Category:** Select your current activity type (e.g., Ideation).
   * **Project Name:** Type your exact project folder name.
   * **File Name:** Specify a virtual file name (defaults to `index.html`).
   * **Confirm:** Check this box to verify your inputs are correct.
5. Click the green **Run workflow** button.

*Note: The system includes a 15-second delay before sending the first heartbeat to allow time for cancellation if you spot a mistake.*

---

## How to Stop Tracking (Crucial)

Because this workflow runs in a continuous loop, **your time will keep tracking indefinitely until you manually stop it.** 

When you are done working:
1. Go to the **Actions** tab and click on the currently running workflow instance.
2. Click the **Cancel run** button in the upper right corner.
3. Wait for the status to change to "Canceled". Your session is now safely terminated.

---

## Feedback & Feature Requests

If you have ideas to improve this tool, want to request new categories, or have suggestions for new features:
* Open an **Issue** in this repository to share your thoughts and requests.
* Feel free to submit a **Pull Request** if you want to contribute directly to the code.
