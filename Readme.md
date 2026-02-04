# 🕵️‍♂️ Steganographic Encryption Suite

A modern, browser-based **steganography tool** that allows you to **securely hide text or files inside images**, with optional **password-based encryption**, and later extract them safely — all **client-side**.

No servers. No uploads. Your data stays with you.

---

## ✨ Features

- 🖼️ Hide secret **text messages** inside images  
- 📎 Hide **entire files** (any format) inside images  
- 🔐 Optional **AES-256-GCM encryption** with password protection  
- 🔓 Extract hidden data from encoded images  
- ⚡ Fully **client-side** (runs in your browser)  
- 🎨 Clean, modern UI with drag & drop support  
- 📊 Progress indicators for large files  
- 🧠 Efficient chunk-based processing for performance  

---

## 🧰 Tech Stack

- **HTML5**
- **CSS3 (Modern UI + Dark Theme)**
- **Vanilla JavaScript**
- **Canvas API**
- **Web Crypto API**
  - PBKDF2 (SHA-256)
  - AES-GCM (256-bit)

---

## 🚀 How It Works

### Encoding (Hiding Data)
1. Select a **host image** (PNG/JPG/JPEG)
2. Enter:
   - A secret message **and/or**
   - A secret file
3. (Optional) Add a **password**
4. The data is:
   - Encrypted (if password provided)
   - Converted to binary
   - Embedded into the **least significant bits (LSB)** of image pixels
5. Download the encoded image

### Decoding (Extracting Data)
1. Upload the encoded image
2. Enter the password (if used)
3. Extract and view:
   - Hidden text
   - Download hidden files

---

## 📁 Project Structure
