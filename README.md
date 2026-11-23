CyberDefenders – FakeGPT Lab

Category: Malware Analysis
Difficulty: Easy
Status: Completed – 10/10 Questions

1. Lab Overview

In this lab, I analyzed a malicious Chrome extension designed to steal sensitive user information and browser credentials.

The investigation focused on examining the extension's source code, identifying its data collection techniques, understanding its anti-analysis behavior, and determining how stolen information is encrypted and exfiltrated to an external domain.

2. Investigation Findings & Evidence

Q1 – URL Obfuscation

Finding: Base64

The extension uses Base64 encoding to obfuscate target URLs.

Evidence:

<img width="1418" height="748" alt="Screenshot (13)" src="https://github.com/user-attachments/assets/d4aa73a5-1bbc-4be9-bae3-4f8854308222" />


Q2 – Targeted Website

Finding: "www.facebook.com"

The extension monitors Facebook to target user accounts and sensitive information.

Evidence:

<img width="1420" height="748" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/07f3db1e-db9c-4a8b-936c-b122e6dfcf2e" />



<img width="1920" height="956" alt="Screenshot (9)" src="https://github.com/user-attachments/assets/a1d73739-837a-4723-9b37-e51425d798cd" />



Q3 – Data Exfiltration Element

Finding: "<img>"

The extension uses HTML image elements to transmit stolen data.

Evidence:

<img width="1419" height="742" alt="Screenshot (10)" src="https://github.com/user-attachments/assets/f0492387-48a9-4050-bed2-17dde5196df4" />


Q4 – Anti-Analysis Condition

Finding: "navigator.plugins.length === 0"

The extension checks the browser environment and can deactivate itself when this condition is met.

Evidence:


<img width="1415" height="746" alt="Screenshot (11)" src="https://github.com/user-attachments/assets/1d632062-590a-4328-aa21-dc22409cced6" />


Q5 – Form Monitoring

Finding: "submit"

The extension captures form submission events to monitor user input.

Evidence:


<img width="1420" height="754" alt="Screenshot (12)" src="https://github.com/user-attachments/assets/e3afdec4-faea-4faf-85a9-ee9798c2be5b" />


Q6 – Keystroke Monitoring

Finding: "keydown"

The extension captures keyboard input through the keydown event.

Evidence:

<img width="1420" height="745" alt="Screenshot (15)" src="https://github.com/user-attachments/assets/d60884bb-0692-4b59-b491-8fdda1efb9b0" />


Q7 – Exfiltration Domain

Finding: "Mo.Elshaheedy.com"

The identified domain used to transmit collected information.

Evidence:

<img width="1920" height="1080" alt="Screenshot (16)" src="https://github.com/user-attachments/assets/7a6e20bf-1cdb-4071-acdf-ca994e206755" />


Q8 – Credential Theft Function

Finding: "exfiltrateCredentials(username, password)"

The function is responsible for exfiltrating usernames and passwords.

Evidence:

<img width="1920" height="1080" alt="Screenshot (17)" src="https://github.com/user-attachments/assets/95ec8297-4e5c-476a-b525-ce0bb7abb56f" />


Q9 – Encryption Algorithm

Finding: AES

The extension encrypts collected data before sending it.

Evidence:

<img width="1422" height="742" alt="Screenshot (14)" src="https://github.com/user-attachments/assets/f408b372-d1ab-4925-928d-17e8efd6849d" />


Q10 – Session Information

Finding: Cookies

The extension accesses cookies to store or manipulate session-related and authentication information.

Evidence:

<img width="1920" height="1080" alt="Screenshot (18)" src="https://github.com/user-attachments/assets/3c49699c-382f-4ab6-9e82-ed996edd3c56" />


3. Indicators of Compromise (IOCs)

Indicator| Value
Target Website| www.facebook.com
Exfiltration Domain| Mo.Elshaheedy.com
Encoding| Base64
Encryption| AES
Exfiltration Element| "<img>"
Input Monitoring| keydown
Form Monitoring| submit
Session Data| Cookies

4. Tools Used

- ExtAnalysis
- CRX Viewer
- JavaScript Source Code Analysis

5. Conclusion

This lab demonstrated how malicious Chrome extensions can steal credentials and sensitive browser information through keystroke monitoring, form interception, and cookie access.

It also highlighted the use of Base64 obfuscation, AES encryption, and covert data exfiltration techniques.

Key Learning Outcomes:

- Browser extension malware analysis.
- Credential theft identification.
- JavaScript code inspection.
- Data exfiltration analysis.
- Anti-analysis technique identification.

Platform: CyberDefenders
Lab: FakeGPT
Result: 10/10 Questions Solved
