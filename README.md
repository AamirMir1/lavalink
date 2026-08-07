# Lavalink Setup Guide (Clear & Beginner-Friendly)

Follow step by step. Don’t skip anything.

---

## Requirements

- Java 17+
- Lavalink.jar
- application.yml

---

## Step 1: Install Java

### Windows

1. Open browser
2. Go to: [https://www.azul.com/downloads/?package=jdk](https://www.azul.com/downloads/?package=jdk)
3. Download **Windows x64 (.msi)**
4. Install it (Next → Install)
5. Make sure **Add to PATH** is enabled

Check:

```bash
java -version
```

✔ If version shows → OK\
❌ If error → reinstall properly

---

### Linux

Open terminal and run:

- **Ubuntu / Debian**

```bash
sudo apt update
sudo apt install default-jdk
```

- **Fedora / CentOS**

```bash
sudo dnf install java-latest-openjdk-devel
```

- **Arch**

```bash
sudo pacman -S jdk-openjdk
```

Check:

```bash
java -version
```

---

## Step 2: Find Your IP

### Windows

```cmd
ipconfig
```

Find this line:

```
IPv4 Address : 192.168.x.x
```

👉 That number is your IP

---

### Linux

```bash
ip a
```

Find:

```
inet 192.168.x.x/24
```

👉 Your IP = part before `/`\
Example:

```
192.168.1.5
```

---

## Step 3: Where to Use IP

You MUST use the same IP in **both places**:

### application.yml

```yaml
server:
  port: 2333
  address: "YOUR_IP"
```

### Bot config

```js
host: "YOUR_IP";
```

---

### Important

- Same PC → use `127.0.0.1`
- Different PC/VPS → use your real IP
- If IP doesn’t match → bot won’t connect

---

## Step 4: Start Lavalink

```bash
java -jar Lavalink.jar
```

---

## Step 5: YouTube Login (Very Important)

When you start Lavalink:

👉 Terminal will show **many logs**\
👉 You don’t need all of them

---

### What to find

Look for a line like this:

```
Go to https://www.google.com/device and enter code XXXX-XXXX
```

---

### Important understanding

- You do NOT create this code
- Lavalink automatically generates it
- Your code will be **different** every time

Example:

```
MGR-XFX-WFQM
```

---

### What you do

1. Open: [https://www.google.com/device](https://www.google.com/device)
2. Enter **the exact code from YOUR terminal**
3. Login with Google

---

### If you don’t see the code

- Scroll up in terminal
- Or restart Lavalink

---

### After login

Terminal will show:

```
Refresh token: 1//xxxxxxxxxxxx
```

👉 This is VERY important\
👉 Copy it exactly

---

## Step 6: Save Token

Open `application.yml`

Add:

```yaml
refreshToken: "YOUR_TOKEN"
skipInitialization: true   //set the skipInitialization to true
```

Save file.

---

## Step 7: Restart Lavalink

```bash
java -jar Lavalink.jar
```

---

## Step 8: Connect Bot

```js
const nodes = [
  {
    host: "YOUR_IP", // which you have added in host in application.yml file
    port: 2333,
    password: "youshallnotpass",
    secure: false,
  },
];
```

---

## Common Mistakes

- Using wrong IP
- Copying example code instead of real one
- Not saving token
- Not restarting server

---

## Final Result

If everything is correct:

✔ Lavalink running\
✔ YouTube connected\
✔ Bot connected\
✔ Music working

---
