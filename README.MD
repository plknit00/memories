# Password-Protected Memories Website

## Overview

This project is a simple password-protected memories website that:

- Loads encrypted memories (text + optional images) from a file (`memories.txt`)
- Displays 9 random memories at a time in a sticky-note style 3x3 grid
- Allows scrambling the displayed memories to reshuffle them
- Provides an **Add Memory** page to add new memories and get an updated encrypted string
- Uses AES encryption (via CryptoJS) to protect your memories behind a password

---

## How to Set Up and Test Locally

### 1. Clone or Download the Project

Make sure you have all these files in the same folder:

- `index.html` — main memories page
- `add-memory.html` — page to create encrypted memories string
- `memories.txt` — contains the encrypted memories string (initially can be empty)

---

### 2. Run a Local Web Server

You need to serve the files over HTTP (not just open `index.html` directly) to avoid browser security restrictions with `fetch()`.

If you have Python installed, open a terminal/command prompt, navigate to your project folder, then run:

- For Python 3.x:

```bash
python3 -m http.server 8000

## Access the Website

- Open your web browser and go to:

http://localhost:8000/index.html


- The page will prompt you to enter your password to decrypt and view memories.

- If `memories.txt` is empty or missing, you will get a notification to add some memories.

---

## Add Memories

- On the main page, click the **Add Memory** button, or open directly:

http://localhost:8000/add-memory.html

- Enter your password and the memory texts you want to add. You can also optionally add image URLs per memory.

- Click **Add Memories & Re-encrypt**.

- The page will generate an encrypted string representing all your memories.

- Copy the encrypted string.

- Open `memories.txt` in a text editor and replace its contents with the copied encrypted string. Save the file.

- Reload the main page (`index.html`), enter your password, and your memories should display.

---

## Additional Details and Notes

- **Password:** The password you enter is the encryption key. Keep it safe and consistent, or you won’t be able to decrypt your memories.

- **Encrypted File:** `memories.txt` must only contain the encrypted string — no extra spaces or blank lines.

- **Batch Adds:** The add-memory page supports adding multiple memories at once.

- **Display:** The main page shows 9 memories at a time in a neat 3x3 grid. You can shuffle (“Scramble Memories”) to see different memories if you have more than 9.

- **Images:** You can include optional image URLs for memories. Images show below the text and can be clicked for a larger view.

- **Local Server:** You must serve the files over HTTP (not `file://`) because browser security blocks `fetch()` from local files.

---

## Hosting on GitHub Pages

- GitHub Pages only supports static files (HTML, CSS, JS).

- All encryption/decryption happens in your browser — no server-side code.

- Commit the encrypted `memories.txt` file to your repo (do **NOT** commit or share your password).

- Access your site at:

https://<your-github-username>.github.io/<repo-name>/index.html

- Remember to update `memories.txt` with your encrypted data whenever you add memories.
```
