# 🚀 Deploy a React App on Ubuntu EC2 with PM2

This guide helps you deploy a React app (built with Vite or Create React App) on an Ubuntu EC2 instance using PM2 and serve.

---

## 🛠️ 1. Update and Upgrade System Packages

```bash
sudo apt update
sudo apt upgrade -y
```

---

## 📦 2. Install Node.js, npm, Git, and PM2

```bash
sudo apt install nodejs npm git -y
sudo npm install -g pm2
```

> PM2 is a production process manager that keeps your app running and auto-restarts on failure or reboot.

---

## 🔄 3. Clone Your React App from GitHub

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
```

> Replace the URL with your own repository link.

---

## 🧱 4. Install Dependencies & Build the App

```bash
npm install
npm run build
```

> This generates a `build/` folder (or `dist/` if you're using Vite) containing your production-ready files.

---

## 🌐 5. Install `serve` Globally

```bash
sudo npm install -g serve
```

> `serve` is a lightweight static file server used to host your build folder.

---

## 🚀 6. Serve React Build with PM2

Run the following command to start the static server using PM2:

```bash
pm2 start "serve -s build -l 3000" --name frontend-app
```

> If you're using Vite, replace `build` with `dist`:
```bash
pm2 start "serve -s dist -l 3000" --name frontend-app
```

---

## 💾 7. Save and Enable PM2 Autostart on Reboot

```bash
pm2 save
pm2 startup
```

---


