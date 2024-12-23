# 🚀 **Tutorial: Setting Up a Self-Hosted Runner for GitHub Actions**

## 📝 **Prerequisites**
1. VPS or server with SSH access.
2. An existing GitHub repository to use.

---

## 🏁 **Step 1: GitHub Preparation**

1. **Access GitHub**
   - Log into your GitHub account.
   - Select the repository where you want to use the self-hosted runner.

2. **Access Repository Settings**
   - On the repository page, click **Settings**.
   - Select **Actions** from the left sidebar, then click **Runners**.

3. **Add Self-Hosted Runner**
   - Click the **Add runner** button.
   - Select **Linux** as the operating system.
   - GitHub will provide instructions for installing and configuring the runner on your server.

---

## 🖥️ **Step 2: Setting Up the Self-Hosted Runner on Server**

1. **Update System**
   Before starting, ensure your system is up-to-date and install required tools by running the following command:
   ```bash
   sudo apt update && sudo apt upgrade -y && sudo apt install curl tar -y

## ⬇️ Step 3: Download Runner
   EXAMPLE: (Use sudo if permission denied)

   mkdir actions-runner && cd actions-runner

   curl -o actions-runner-linux-x64-2.310.0.tar.gz -L https://github.com/actions/runner/releases/download/v2.310.0/actions-runner-linux-x64-2.310.0.tar.gz

   tar xzf ./actions-runner-linux-x64-2.310.0.tar.gz

## 🔑 Step 4: Register Runner
    Return to the GitHub page and copy the command to register your runner.
    The command typically looks like this: ./config.sh --url https://github.com/username/repo --token YOUR_TOKEN

## ▶️ Step 5: Start Runner
   ./run.sh (this runs in the interface, if you press ctrl + c the runner will stop)

   It's recommended to use svc.sh files if you want the service to run in the background and keep the runner service always alive:

   sudo ./svc.sh install && sudo ./svc.sh start && sudo ./svc.sh status

## 🏁 Step 6: Create Workflow and Complete...
