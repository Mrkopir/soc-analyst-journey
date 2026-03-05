# How Websites Work - TryHackMe

## 1. Sensitive Data Exposure

Sometimes developers forget to remove sensitive or important information from the frontend source code. This data can be visible in HTML, JavaScript, or even inside comments.

An attacker can inspect the page source code and find exposed credentials, hidden links, API keys, or other confidential information. By using this data, the attacker may gain unauthorized access to different parts of the web application.

That is why reviewing the page source code is an important step when testing a website for security issues.

## 2. HTML Injection

HTML Injection is a vulnerability that can change the UI of a website. It works similarly to XSS, but it is usually much simpler and less dangerous.