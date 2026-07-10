# Hackatime Off-Editor Tracker

A lightweight GitHub Actions workflow to log Hackatime heartbeats without opening an IDE or code editor.

This tool is perfect for tracking off-editor work like Ideation, Research, Narrative Design, Asset Creation, and other project tasks that never touch a text editor, directly from your browser, without requiring any local setup or background processes.

## Features

* **Zero Installation** — Runs entirely in the cloud via GitHub Actions.
* **Resource Efficient** — Requires no local background processes on your device.
* **Auto Stop** — Sessions automatically end after 80 minutes, so a forgotten tab won't quietly rack up hours.
* **Safety Lock** — Requires an explicit confirmation checkbox to prevent accidental runs and unwanted ghost projects on your dashboard.

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
> **Verify your project name before running.**
> Hackatime will automatically create a new project on your dashboard if you misspell it. Double check spelling for both **Project Name** and **File Name**, and make sure there's no trailing space or line break at the end of either field. The confirmation checkbox exists to remind you of this, but it won't catch a typo for you.

1. Go to the **Actions** tab in your repository.
2. On the left sidebar, select the **Start Hackatime Off-Editor** workflow.
3. Click the **Run workflow** dropdown button on the right side.
4. Carefully fill out the required parameters:
   * **Category** — Select your current activity: Ideation, Research, Narrative Design, Resource Creation, Asset Creation, Game Design, or Hardware Assembly.
   * **Project Name** — Type your exact project name, as it should appear on your Hackatime dashboard.
   * **File Name** — Specify a virtual file name. There's no default, so this needs to be filled in manually every run.
   * **Confirm** — Check this box once you've verified the fields above.
5. Click the green **Run workflow** button.

*Note: The workflow waits 20 seconds before sending the first heartbeat, giving you a window to cancel the run if something looks off.*

---

## How to Stop Tracking

Once started, the workflow keeps sending a heartbeat every minute until one of two things happens:

* **You stop it manually** — Go to the **Actions** tab, open the running workflow instance, and click **Cancel run** in the upper right corner. Wait for the status to change to "Canceled" and the session is done.
* **It stops itself after 80 minutes** — This is a built-in safety limit. The session ends on its own and logs a short message letting you know it's a good time to take a break.

Either way, no session runs longer than 80 minutes.

---

## Feedback & Feature Requests

If you have ideas to improve this tool, want to request new categories, or have suggestions for new features:

* Open an **Issue** in this repository to share your thoughts and requests.
* Feel free to submit a **Pull Request** if you want to contribute directly to the code.
