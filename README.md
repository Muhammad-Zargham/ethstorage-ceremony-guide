# Ceremony
Eth storage ceremony is live.!
# 🚀 EthStorage V1 Trusted Setup Ceremony (Community Guide)

This guide helps you participate in the **EthStorage V1 Trusted Setup Ceremony** on **Ubuntu 22.04**.

---

## 📌 Requirements
- Ubuntu 22.04 VPS (2 vCPU, 4GB RAM, 30GB+ SSD recommended)  
- SSH access  
- GitHub account (≥ 1 month old)  
- At least 1 public repository  
- Follow ≥ 5 accounts & have ≥ 1 follower  
- Allow p0tion to access GitHub Gists (for auth)

---

## 🛠 Step-by-Step Setup

### 1️⃣ Update & Install Dependencies
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y curl git build-essential
2️⃣ Install Node.js v18 & npm v9.2
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt install -y nodejs
sudo npm install -g npm@9.2
3️⃣ Check Versions
node -v
npm -v
4️⃣ Create Temporary Directory
mkdir ~/trusted-setup-tmp && cd ~/trusted-setup-tmp
5️⃣ Install Phase2 CLI
npm install -g @p0tion/phase2cli
6️⃣ Verify CLI Installation
phase2cli --version
7️⃣ Authenticate with GitHub
phase2cli auth
7.5️⃣ Install screen (Recommended)
sudo apt install -y screen
8️⃣ Contribute to the Ceremony
screen -S ceremony phase2cli contribute -c ethstorage-v1-trusted-setup-ceremony
🧹 Cleanup After Contribution
phase2cli clean
phase2cli logout
cd ~ && rm -rf ~/trusted-setup-tmp

🖥 Screen Session Controls

Detach: CTRL + A then D

Notes

After contribution, wait for your queue. The tool will handle your turn when it arrives.

Destroy VPS after use for security if desired.


---

# Add a screenshot / proof of `screen` install (do this on Day 2 before / after contribution)
If your VPS is headless, save the terminal output as text and also take a screenshot from your local SSH window.

**On VPS (capture text output):**
```bash
sudo apt update
sudo apt install -y screen |& tee ~/screen-install-output.txt
screen -ls |& tee -a ~/screen-install-output.txt
# the file is at ~/screen-install-output.txt


Copy to your local machine and add to repo
# from your local machine:
scp user@VPS_IP:~/screen-install-output.txt ./ethstorage-ceremony-guide/screenshots/

# (optional) take a screenshot of your terminal window on your local PC and save as:
# ./ethstorage-ceremony-guide/screenshots/screen-install.png

Commit & push

git add screenshots/screen-install-output.txt screenshots/screen-install.png
git commit -m "Add screen install output + screenshot"
git push

Then update README to reference the screenshot:

![screen install output](screenshots/screen-install.png)

Reattach: screen -r ceremony
