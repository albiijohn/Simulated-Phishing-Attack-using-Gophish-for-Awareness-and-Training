# Simulated Phishing Attack Using GoPhish for Awareness and Testing

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
<image tag>

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
<image tag>

</details>

---

<details>
<summary><strong>2.3 Creating a Sending Profile</strong></summary>

Fill in:

- Attacker email
- SMTP server settings
- App password

This allows GoPhish to send test emails.  
<image tag>

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

Right-click and “View Page Source”  
Copy the HTML and paste it into the **Landing Page > Import Site** section in GoPhish.  
<image tag>

</details>

---

<details>
<summary><strong>2.5 Creating an Email Template</strong></summary>

We use a real Google Security Alert email as bait.

Steps:
- Open the email
- Click 3 dots > “Show original”
- Copy the HTML
- Paste into **Email Template > Import Email**  
<image tag>

</details>

---

<details>
<summary><strong>2.6 Creating Users/Groups</strong></summary>

Add target emails under **Users & Groups**.  
In this test, a single Gmail account is used for both attacker and target.  
<image tag>

</details>

---

## 3. Launching the Attack

Go to **Campaigns** in the dashboard.  
Verify your settings, then click **Launch Campaign**.  
<image tag>

---

## 4. Target’s Perspective

The target receives an email crafted using the email template.

On clicking the phishing link:
- They are redirected to the fake landing page (Google login clone)
- URL is clearly different from Google’s official domain  
- Victim may unknowingly submit credentials  
<image tag>

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
<image tag>

Clicking **View Details** reveals the credentials entered by the target.  
<image tag>

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
