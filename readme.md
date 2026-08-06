# 🎵 Lavalink Server Setup Guide (Super Beginner Friendly)

This guide is written for people with **zero coding knowledge**.
Just follow each step exactly.

---

# 📌 What You’ll Do

✔ Install Java
✔ Setup network correctly
✔ Run Lavalink
✔ Complete YouTube login
✔ Connect to your bot

---

# ☕ STEP 1: Install Java

Lavalink **needs Java 17+**.

### ✔ Check if already installed

```bash
java -version
```

If it shows a version → skip install
If not → install it

---

# 🌐 STEP 2: IMPORTANT — Find Your IP (Read Carefully)

This is where many users get confused.

---

## 🪟 Windows (Very Clear Method)

Run:

```cmd
ipconfig
```

Now you will see multiple sections like:

```
Wireless LAN adapter Wi-Fi:
   IPv4 Address . . . . . . . . . . : 192.168.1.5
```

👉 **You ONLY need this line:**

- **IPv4 Address**

👉 Ignore:

- IPv6 Address
- Subnet Mask
- Default Gateway

✔ Your IP will look like:

- `192.168.x.x`
- OR `10.x.x.x`

---

## 🐧 Linux (Very Clear Method)

Run:

```bash
ip a
```

You will see many blocks like:

```
2: wlan0: ...
    inet 192.168.1.5/24
```

👉 **You ONLY need the line with:**

- `inet`

Example:

```
inet 192.168.1.5/24
```

✔ Your IP is:

```
192.168.1.5
```

---

## ⚠️ What to IGNORE

Do NOT use:

- `127.0.0.1` (local only)
- `lo` interface
- anything with `127.x.x.x`

---

## ✔ Which IP Should You Use?

- Same PC bot → use `127.0.0.1`
- Different PC / VPS / VPN → use your real IP (from above)

---

# ▶️ STEP 3: Start Lavalink

Run:

```bash
java -jar Lavalink.jar
```

---

# 🔐 STEP 4: YouTube Authorization (IMPORTANT — READ)

When you run Lavalink, the terminal will show **a LOT of logs**.

👉 Don’t panic — this is normal.

---

## 🔍 What You Are Looking For

Somewhere in those logs, you will see something like:

- A message telling you to visit a link
- A code (example: `ABCD-EFGH`)

It may look like:

```
Go to https://www.google.com/device and enter code XXXX-XXXX
```

---

## 👉 What You Should Do

1. Open this link:

```
https://www.google.com/device
```

2. Enter the code shown in your terminal

3. Login with a Google account

---

## ⚠️ Important Tips

- Use a **new / spare account**
- This step happens **only once**
- Logs may scroll fast — scroll up if needed

---

## ✅ After Login

Go back to terminal.

You will now see something like:

```
Refresh token: 1//0gxxxxxxxxxxxx
```

👉 This long code is VERY IMPORTANT

---

# 📝 STEP 5: Save the Token

1. Open `application.yml`

2. Find:

```
refreshToken:
```

3. Add your token:

```
refreshToken: "YOUR_TOKEN_HERE"
```

---

4. Find:

```
skipInitialization: false
```

Change to:

```
skipInitialization: true
```

---

5. Save file
6. Restart Lavalink

---

# 🤖 STEP 6: Connect to Your Bot

```js
const fallbackLavalinkNodes = [
  {
    host: "YOUR_IP_HERE",
    port: 2333,
    password: "youshallnotpass",
    secure: false,
  },
];
```

---

# 🔒 Security Tips

- Change default password
- Don’t expose server publicly
- Avoid `0.0.0.0`

---

# ✅ DONE!

✔ Lavalink running
✔ YouTube connected
✔ Bot ready 🎶

---

# ❗ Common Mistakes

- Using wrong IP
- Not saving token
- Not restarting server
- Copying wrong line from logs

---

# 🎉 Final Result

Your bot can now play music using Lavalink 🚀
