# Simulated Phishing Attack Using GoPhish for Awareness and Testing

<div align="center">
  <img src="Gophish/Gophish logo.png">
</div>

This project demonstrates how to simulate a phishing attack using [GoPhish](https://getgophish.com/), an open-source phishing framework. The goal is to help security professionals and organizations understand phishing techniques and improve their awareness and response.

---

## 1. Introduction

Phishing is one of the most common and dangerous cyber threats where attackers trick users into revealing sensitive information. This project demonstrates a simulated phishing attack using GoPhish, an open-source phishing toolkit. It helps security professionals assess how users respond to phishing emails in a controlled environment. The goal is to understand the tactics used by attackers and train users to identify suspicious emails.

---

## 2. Setup Process

<details>
<summary><strong>2.1 Launching GoPhish</strong></summary>

```bash
gophish
```

Once GoPhish is set up, it provides default login credentials and a link to access the dashboard.  
<img src="Gophish/Launching Gophish.png" width="900" height="600">

</details>

---

<details>
<summary><strong>2.2 GoPhish Dashboard</strong></summary>

You will configure the following before launching a campaign:

- Sending Profile
- Landing Page
- Email Template
- Users & Groups

**Pre-requisite**: You’ll need an [App Password from your Google Account](https://support.google.com/accounts/answer/185833?sjid=453660624339540911-NC) (2FA must be enabled).  
<img src="Gophish/Go phish dashboard.png" width="900" height="600">

</details>

---

<details>
<summary><strong>2.3 Creating a Sending Profile</strong></summary>

Fill in:

- Attacker email
- SMTP server settings
- App password

This allows GoPhish to send test emails.  
<img src="Gophish/Creating a sending profile.jpg" width="900" height="600">

<img src="Gophish/Testing email from Send profile.png" width="900" height="600">

</details>

---

<details>
<summary><strong>2.4 Setting Up a Landing Page</strong></summary>

This is the page a victim sees after clicking the phishing link.  
We use a Google login template prebuilt in Kali Linux:

```bash
cd /usr/share/set/src/html/templates/google
ls
open index.template
```
<img src="Gophish/Index.html page of google.png" width="900" height="600">

Right-click and “View Page Source”  
Copy the HTML and paste it into the **Landing Page > Import Site** section in GoPhish.  
<img src="Gophish/Html code for index.html.png" width="900" height="600">

<img src="Gophish/Landing page.png" width="900" height="600">

</details>

---

<details>
<summary><strong>2.5 Creating an Email Template</strong></summary>

We use a real Google Security Alert email as bait.

Steps:
- Open the email
- Click 3 dots > “Show original”

<img src="Gophish/Sample Email template.png" width="900" height="600">

- Copy the HTML
- Paste into **Email Template > Import Email**  
<img src="Gophish/Creating email template.png" width="900" height="600">

</details>

---

<details>
<summary><strong>2.6 Creating Users/Groups</strong></summary>

Add target emails under **Users & Groups**.  
In this test, a single Gmail account is used for both attacker and target.  
<img src="Gophish/Creating a user group.png" width="900" height="600">

</details>

---

## 3. Launching the Attack

Go to **Campaigns** in the dashboard.  
Verify your settings, then click **Launch Campaign**.  
<img src="Gophish/Launching attack.png" width="900" height="600">

---

## 4. Target’s Perspective

The target receives an email crafted using the email template.

<img src="Gophish/phishing email.png" width="900" height="600">

On clicking the phishing link:
- They are redirected to the fake landing page (Google login clone)
- URL is clearly different from Google’s official domain

<img src="Gophish/After clicking the link.png" width="900" height="600">
  
- Victim may unknowingly submit credentials  
<img src="Gophish/User entering credentials.png" width="900" height="600">

---

## 5. Attacker’s Dashboard

The dashboard shows the campaign timeline:

- Email sent
- Email opened
- Link clicked
- Credentials submitted

Additional info includes:
- Target’s device type
- Browser used  
<img src="Gophish/Dashboard details.png" width="900" height="600">

Clicking **View Details** reveals the credentials entered by the target.  
<img src="Gophish/Grabbed credentials.png" width="900" height="600">

---

## 6. Conclusion

This project provided hands-on experience with simulating phishing attacks using GoPhish. By observing how users interact with phishing emails, organizations can better prepare their workforce. Such exercises are essential for increasing security awareness.

---

### 6.1 How to Prevent Phishing Attacks

- Always verify the sender’s email address before clicking any links.
- Do not click on suspicious or unexpected attachments or links.
- Enable multi-factor authentication (MFA) wherever possible.
- Keep your browser, antivirus, and operating system updated.
- Attend regular cybersecurity awareness training sessions.

---

> **Disclaimer:** This project was done for educational and awareness purposes only. Do not attempt phishing activities on others without legal authorization.
