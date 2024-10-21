# TryHackMe - OhSINT Walkthrough

This repository contains a step-by-step guide and solution for the TryHackMe **OhSINT** room. The challenge focuses on using OSINT (Open Source Intelligence) techniques to extract valuable information from a single image file.

---

### Challenge Description

The task is to gather various pieces of information based on an image file and some additional online investigation. Each question tests your ability to uncover details about a user through open-source data.

---

### Questions and Answers

1. **What is this user's avatar of?**
   - Use the command below to extract metadata from the image file:
     ```bash
     exiftool image.jpg
     ```
   - In the metadata, you will find the author's name: `Owoodflint`.
   - Search `Owoodflint` on the internet and click the first result, which should lead to their Twitter profile. The user's avatar is a ****.
     ![image](https://github.com/user-attachments/assets/461eaafb-67b4-4ac6-8489-136b2810aec3)


2. **What city is this person in?**
   - On the same Twitter profile, the user has posted location coordinates in BSSID form.
   - Copy the BSSID and go to [wigle.net](https://wigle.net).
   - Use the **advanced search** feature, paste the BSSID, and click on the map to find the city. The person is in ****.
     ![image](https://github.com/user-attachments/assets/53a86bee-8659-41b3-a2a6-737874eac209)  

3. **What is the SSID of the WAP he connected to?**
   - On the map, click on "View in interactive." Look for the SSID that matches the BSSID found earlier. The correct SSID is **uniliver-related**.

4. **What is his personal email address?**
   - Search for `Owoodflint` on GitHub, and you will find their GitHub profile.
   - In the GitHub repository or their profile's README, you will find the email address: ****.
  ![image](https://github.com/user-attachments/assets/1b6956b1-9d41-4deb-b170-d4e2cb4867f1)

5. **What site did you find his email address on?**
   - The email address was found on ****.
   - Use your thinking.

6. **Where has he gone on holiday?**
   - In the GitHub profile, there is a blog link. Open the blog, and you will find a mention of a recent holiday to ****.

7. **What is the person's password?**
   - Inspect the blog’s HTML source code. The password is hidden within the source: ****.
![image](https://github.com/user-attachments/assets/c3c9d254-3ff3-4957-afd4-432da1eb5ee9)

---

### Tools Used

- **ExifTool**: To extract metadata from the image.
- **Wigle.net**: For searching WiFi networks and locations based on BSSID.
- **Google Search**: To track the user’s online presence.
- **GitHub**: To find personal details like email and blog posts.
- **Browser Developer Tools**: For inspecting source code and discovering hidden information.

---

### Conclusion

The OhSINT challenge demonstrates how much information can be uncovered from seemingly insignificant data such as a single image file. By utilizing OSINT tools and techniques, we can uncover sensitive personal information and details about an individual. This serves as a reminder to be cautious about the data we share online.

---

### Disclaimer

This walkthrough is for educational purposes only. Ensure you have permission before extracting or analyzing data about others. The purpose is to raise awareness about privacy risks and improve security practices.

---

### References

- [ExifTool](https://exiftool.org/)
- [Wigle.net](https://wigle.net/)
- [TryHackMe OhSINT Room](https://tryhackme.com/room/ohsint)
