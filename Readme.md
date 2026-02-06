# 🕵️‍♂️ Steganography Suite

A secure, client-side web application for Steganography. This tool allows users to hide secret text messages and files within innocent-looking images, protected by military-grade encryption.

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-GNU-green.svg)
![Technology](https://img.shields.io/badge/tech-HTML5%20%7C%20CSS3%20%7C%20JS-orange.svg)

## 📖 Overview

**Steganography Suite** runs entirely in the browser (no data is sent to a server). It utilizes **Least Significant Bit (LSB)** encoding to embed data into the pixels of an image. To ensure security, all hidden data is encrypted using **AES-256-GCM** before being embedded, making the hidden content irretrievable without the correct password.

## ✨ Key Features

* **📷 Image Steganography:** Hide sensitive data inside PNG, JPG, or JPEG images.
* **🔒 Military-Grade Encryption:** Optional password protection using **AES-GCM** with **PBKDF2** key derivation.
* **📝 Text & File Support:** Hide simple text messages or entire files (documents, images, PDFs) inside a host image.
* **⚡ Client-Side Processing:** All processing happens locally in your browser. No data ever leaves your device.
* **🎨 Modern UI:** Sleek, responsive dark-mode interface with drag-and-drop support.
* **🚀 Optimized Performance:** Non-blocking chunked processing ensures the browser doesn't freeze during large operations.

## 🛠️ Technology Stack

* **Core:** HTML5, CSS3, Vanilla JavaScript (ES6+)
* **Cryptography:** Web Crypto API (Native browser standard for cryptographic operations)
* **Styling:** Custom CSS with CSS Variables and Flexbox
* **Fonts:** Inter (via Google Fonts)

## 🚀 Getting Started

Since this is a client-side application contained within a single file, installation is instant.

### Prerequisites

* A modern web browser (Chrome, Firefox, Edge, Safari).

### Installation & Usage

1.  Download or clone this repository.
2.  Locate `encryption.html`.
3.  Double-click the file to open it in your web browser.

#### To Encode Data:
1.  Upload a **Host Image**.
2.  Enter your **Secret Text** or upload a **Secret File**.
3.  (Optional) Set a **Password**.
4.  Click **Encode Data** and download the resulting PNG image.

#### To Decode Data:
1.  Switch to the **Decode Data** tab.
2.  Upload the encoded image.
3.  Enter the password (if one was used).
4.  Click **Decode Data** to reveal the secrets.

## ⚙️ How It Works (Technical)

### 1. The Encoding Process (LSB)
The application reads the binary data of your secret message/file. It iterates through the pixels of the host image and modifies the **Least Significant Bit** of the Red, Green, Blue, and Alpha channels to match the bits of your secret data.
* *Result:* The changes to the image are so subtle that they are invisible to the human eye.

### 2. The Encryption Layer
Before encoding, the data is processed via the **Web Crypto API**:
* **Key Derivation:** Your password is salted and run through **PBKDF2** (100,000 iterations) to generate a secure cryptographic key.
* **Encryption:** The data is encrypted using **AES-GCM** (Galois/Counter Mode), which provides both confidentiality and integrity checks.

### 3. File Handling
* **Input:** Accepts JPG, PNG, and JPEG.
* **Output:** Always generates a **PNG** file.
    * *Why?* PNG is a lossless format. Formats like JPG use compression that "blurs" pixel data, which would destroy the hidden secret bits.

## ⚠️ Limitations & Notes

* **File Size:** The limit for host images is set to **10MB** to prevent browser crashes on low-memory devices.
* **Storage Capacity:** The amount of data you can hide depends on the resolution of the host image.
    * *Formula:* `(Width * Height * 3 channels) / 8` = Approx bytes available.
* **Image Compression:** **Do not compress** the resulting image (e.g., sending it via WhatsApp or Facebook Messenger often compresses images). This will corrupt the hidden data. Always share the image as a "File" or "Document".

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1.  Fork the project.
2.  Create your feature branch (`git checkout -b feature/AmazingFeature`).
3.  Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4.  Push to the branch (`git push origin feature/AmazingFeature`).
5.  Open a Pull Request.

## 📄 License

Distributed under the GNU License. See `LICENSE` for more information.
