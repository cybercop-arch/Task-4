# Social Engineering Simulation

I conducted a controlled phishing simulation using GoPhish, an open-source phishing framework. The objective was to understand attacker methodologies, identify user behavioral patterns, and demonstrate the importance of security awareness in preventing credential theft and social engineering attacks.

This simulation was performed in a safe, isolated environment, and all participants involved were aware that it was a security test.

1. Tools & Environment

GoPhish v0.12+

Landing Page: Custom HTML login page

SMTP Server: Gmail SMTP with App Password

Operating System: Kali Linux

Browser: Chrome (Victim Testing)


2. Campaign Setup
 
2.1 Email Template

A realistic login-alert themed email was created, containing:

Organization-style header

Urgent message requesting login verification

Embedded phishing URL pointing to GoPhish landing page

2.2 Landing Page

A cloned login form was configured with:

Email & Password fields

“Capture Submitted Data” enabled

“Capture Passwords” enabled

Optional redirect to a safe URL

2.3 Sending Profile

Configured using:

SMTP Server: smtp.gmail.com:587

Authentication: Gmail app password

From Address: Legitimate-looking sender name

TLS: Automatically handled by Gmail

2.4 Target User Group

A single test email was used for the demonstration.


*Attack Flow Breakdown*

Email Delivered → Opened

User Clicked Link → Redirected to Fake Login Page

User Submitted Credentials → Captured by GoPhish

This simulation validates how quickly an attacker can compromise accounts through well-crafted social engineering.

3. Security Awareness Recommendations
3.1 Best Practices for Users

✔ Never click unknown links in emails.

✔ Verify the sender’s email domain.

✔ Hover over links to inspect URLs before clicking.

✔ Avoid entering credentials on unfamiliar websites.

✔ Enable Multi-Factor Authentication (MFA).

✔ Report suspicious emails to the security team immediately.


Conclusion

This phishing simulation successfully demonstrated:

How attackers craft convincing phishing emails

How easily credentials can be harvested

The importance of security awareness and proper email hygiene

By conducting this campaign, I gained hands-on experience in:

Social engineering simulation

Email delivery systems

Web cloning

Credential capture techniques

Analysis of phishing metrics

Security awareness enhancement

This exercise reinforces the critical need for organizations to prioritize cyber-awareness, strengthen employee training programs, and adopt multi-layered security controls.

<img width="1713" height="732" alt="image" src="https://github.com/user-attachments/assets/c69b8ab2-9f7a-4e4d-b1ce-5beee0ad0b5c" />
