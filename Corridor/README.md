# Corridor TryHackMe Room Walkthrough 🚪

This repository contains the walkthrough for solving the **Corridor** TryHackMe room, focusing on **IDOR (Insecure Direct Object Reference)** vulnerabilities. The solution involves analyzing MD5 hashes and manipulating URLs to find the flag.

---

## How to Solve the Challenge 🧩

### Step 1: Initial Reconnaissance 🔍
Start by scanning the target IP address to discover open ports:
- Use tools like `nmap` to scan for services.
- You'll find port `80 (HTTP)` open, indicating a website.
  
![image](https://github.com/user-attachments/assets/a565107e-5a2e-4590-ba8b-32cf3a15403f)

---

### Step 2: Explore the Website 🌐
1. Visit the website: `http://<target-ip>` (e.g., `http://10.10.50.51`).
2. You'll see an image of a corridor with clickable doors.
3. Clicking a door redirects to URLs like:
   
http://10.10.50.51/c9f0f895fb98ab9159f51fd0297e236d

---

### Step 3: Analyze the URL 🧠
- Notice the string at the end of the URL (`c9f0f895fb98ab9159f51fd0297e236d`). It looks like a **hash**.

   ![image](https://github.com/user-attachments/assets/3a5520be-2551-496a-8475-52f5f514fa41)

-  Identify the hash format using resources like [ChatGPT](https://chat.openai.com) or online tools.
- You’ll discover it’s an **MD5 hash**.

---

### Step 4: Decode the Hash 🔓
- Decode the MD5 hash to find its original value. Use an online MD5 decryptor, such as:
- [10015.io MD5 Decryptor](https://10015.io/tools/md5-encrypt-decrypt)
- [MD5 Decrypt](https://md5decrypt.net/en/)

Example:
- Hash: `c9f0f895fb98ab9159f51fd0297e236d`
- Decoded text: `3`

---

### Step 5: Test Endpoints 🔗
1. Decode all the hashes from the clickable doors and note the results (`1, 2, 3, ..., 13`).
2. Guess the next endpoint by trying `14`:
- Convert `14` to an MD5 hash: `aab3238922bcc25a6f606eb525ffdc56`.
- Access the URL: `http://10.10.50.51/aab3238922bcc25a6f606eb525ffdc56`.

3. If no flag is found, try the endpoint for `0`:
- Convert `0` to MD5: `cfcd208495d565ef66e7dff9f98764da`.
- Visit: `http://10.10.50.51/cfcd208495d565ef66e7dff9f98764da`.

---

### Step 6: Find the Flag 🎉
- When accessing the correct endpoint, you’ll find a flag in this format:
  **flag{j7y**********}**

## Key Concepts and Tools 🛠️

### 1. **IDOR (Insecure Direct Object Reference)**
 - IDOR is a vulnerability that allows attackers to access unauthorized data by modifying identifiers in a URL, API, or similar.

### 2. **MD5 Hash**
 - A widely used cryptographic hash function producing a 32-character hexadecimal number.
 - **One-way**: MD5 cannot be reversed but can be cracked with databases or tools.

### 3. **Useful Tools**
 - [Nmap](https://nmap.org): For scanning open ports.
 - [10015.io](https://10015.io): For MD5 decryption and encryption.
 - [Hashcat](https://hashcat.net/hashcat/): For local hash cracking.

---

## Example Commands 🚀

To manually test MD5 encoding/decoding:
```python
import hashlib

# Encode a string to MD5
text = "0"
md5_hash = hashlib.md5(text.encode()).hexdigest()
print(md5_hash)  # Output: cfcd208495d565ef66e7dff9f98764da`.

