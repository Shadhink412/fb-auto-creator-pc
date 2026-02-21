# 📱 Facebook Account Creator Bot

Automated Facebook account creation using Android device via USB.  
Screen detection engine identifies UI states and handles the full registration flow.

---

## ⚙️ Requirements

| Requirement | Details |
|------------|---------|
| **Python** | 3.8+ |
| **OS** | Windows / Linux / Termux (Android) |
| **Android Device** | USB Debugging enabled |
| **ADB** | Installed and device visible (`adb devices`) |

## 📦 Installation

```bash
# Clone the repo
git clone https://github.com/yourusername/fb-account-creator.git
cd fb-account-creator

# Install dependencies
pip install requests uiautomator2 pyotp
```

## 🚀 Usage

### Step 1: Prepare Account Data

Create `data.csv` with the following columns:

```csv
first_name,last_name,mobile_number,email,email_password,password,birthday,gender
John,Doe,01712345678,john@gmail.com,apppassword123,MyPass@123,1995-03-15,Male
```

### Step 2: Connect Android Device

1. Enable **USB Debugging** on your Android phone
2. Connect via USB cable
3. Verify connection:
```bash
adb devices
```

### Step 3: Run the Bot

```bash
python main.py
```

On first run, you'll be prompted for:
- **Gmail Address** — for receiving OTP codes
- **Gmail App Password** — [Generate here](https://myaccount.google.com/apppasswords)

### Step 4: Profile Setup

After account creation, run:
```bash
python pro.py
```

---

## 📋 Features

- ✅ **Screen Detection Engine** — Automatically identifies Facebook UI screens
- ✅ **Auto OTP Handling** — Fetches OTP from Gmail via IMAP
- ✅ **Human-like Behavior** — Random delays, natural typing patterns
- ✅ **Permission Handling** — Auto-dismisses Android permission popups
- ✅ **Error Recovery** — Auto-restart on stuck screens
- ✅ **Progress Tracking** — Resumes from last account on restart
- ✅ **Ban Detection** — Detects account blocks early
- ✅ **Auto Dependencies** — Installs required packages automatically

## 📁 File Structure

```
├── main.py          # Main entry point (run this)
├── data.csv         # Account data (create this)
├── config.json      # Gmail config (auto-generated)
├── progress.txt     # Resume progress (auto-generated)
├── success.csv      # Created accounts (auto-generated)
└── pro.py           # Profile setup script
```

## ⚠️ Notes

- Facebook app must be installed on the Android device
- One account is created at a time
- Gmail App Password required (not regular password)
- IMAP must be enabled on the Gmail account
- Press `Ctrl+C` to gracefully stop at any time

## 📞 Support

For support or license activation, your HWID will be displayed when you first run the script.

---

**Made with ❤️**
