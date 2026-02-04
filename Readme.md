🕵️‍♂️ Steganography Suite
A powerful, client-side web application for secure Steganography. This tool allows users to hide secret text messages and files within innocent-looking images, protected by military-grade encryption.

📖 Overview
Steganography Suite runs entirely in the browser (no data is sent to a server). It utilizes Least Significant Bit (LSB) encoding to embed data into the pixels of an image. To ensure security, all hidden data is encrypted using AES-256-GCM before being embedded, making the hidden content irretrievable without the correct password.

✨ Key Features
📷 Image Steganography: Hide sensitive data inside PNG, JPG, or JPEG images.

🔒 Military-Grade Encryption: Optional password protection using AES-GCM with PBKDF2 key derivation.

📝 Text & File Support: Hide simple text messages or entire files (documents, images, PDFs) inside a host image.

⚡ Client-Side Processing: All processing happens locally in your browser. No data ever leaves your device.

🎨 Modern UI: Sleek, responsive dark-mode interface with drag-and-drop support.

🚀 Optimized Performance: Non-blocking chunked processing ensures the browser doesn't freeze during large operations.

🛠️ Technology Stack
Core: HTML5, CSS3, Vanilla JavaScript (ES6+)

Cryptography: Web Crypto API (Native browser standard for cryptographic operations)

Styling: Custom CSS with CSS Variables and Flexbox (No external CSS frameworks)

Fonts: Inter (via Google Fonts)

🚀 Getting Started
Since this is a client-side application contained within a single file, installation is instant.

Prerequisites
A modern web browser (Chrome, Firefox, Edge, Safari).

Usage
Download the encryption.html file.

Double-click to open it in your web browser.

To Encode:

Upload a "Host Image".

Enter your secret text or upload a secret file.

(Optional) Set a password.

Click Encode Data and download the resulting image.

To Decode:

Switch to the Decode Data tab.

Upload the encoded image.

Enter the password (if one was used).

Click Decode Data to reveal the secrets.

⚙️ How It Works (Technical)
1. The Encoding Process (LSB)
The application reads the binary data of your secret message/file. It iterates through the pixels of the host image and modifies the Least Significant Bit of the Red, Green, Blue, and Alpha channels to match the bits of your secret data.

Result: The changes to the image are so subtle that they are invisible to the human eye.

2. The Encryption Layer
Before encoding, the data is processed via the Web Crypto API:

Key Derivation: Your password is salted and run through PBKDF2 (100,000 iterations) to generate a secure cryptographic key.

Encryption: The data is encrypted using AES-GCM (Galois/Counter Mode), which provides both confidentiality and integrity checks.

3. File Handling
Input: Accepts JPG, PNG, and JPEG.

Output: Always generates a PNG file.

Why? PNG is a lossless format. Formats like JPG use compression that "blurs" pixel data, which would destroy the hidden secret bits.

⚠️ Limitations & Notes
File Size: The limit for host images is set to 10MB to prevent browser crashes on low-memory devices.

Storage Capacity: The amount of data you can hide depends on the resolution of the host image.

Formula: (Width * Height * 3 channels) / 8 = Approx bytes available.

Image Compression: Do not compress the resulting image (e.g., sending it via WhatsApp or Facebook Messenger often compresses images). This will corrupt the hidden data. Always share the image as a "File" or "Document".

🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

Fork the project.

Create your feature branch (git checkout -b feature/AmazingFeature).

Commit your changes (git commit -m 'Add some AmazingFeature').

Push to the branch (git push origin feature/AmazingFeature).

Open a Pull Request.

📄 License
Distributed under the MIT License. See LICENSE for more information.

Built with ❤️ for privacy and security.
