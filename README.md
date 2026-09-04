# 🎣 Phishing Awareness & Login Simulation

> ⚠️ **EDUCATIONAL / AUTHORIZED SECURITY TESTING ONLY**
>
> This project is a controlled phishing-awareness simulation created for cybersecurity education and learning purposes. It demonstrates how a deceptive login interface can imitate a trusted service and how submitted form data can be handled by a backend.
>
> **Never use this project against real users, organizations, or accounts without explicit authorization. Never enter real passwords or sensitive credentials into the application.**

---

## 📌 Overview

This project demonstrates the basic mechanics behind a **phishing-style login page** without relying on a dedicated phishing framework or automated phishing tool.

The application recreates a Microsoft-style sign-in interface using **HTML, CSS, and JavaScript**, while a lightweight **Flask backend** handles form submissions.

The project was developed to understand:

* How phishing pages imitate trusted login interfaces
* How frontend forms communicate with a backend
* How HTTP `POST` requests transmit form data
* How a Flask server receives submitted form fields
* How phishing simulations can be used for security awareness training
* Why users should verify URLs before entering credentials

The repository is intentionally designed as a **learning and awareness project**, not as a credential-theft system.

---

## 🎯 Project Objective

The primary objective of this project is to understand the technical concepts behind phishing attacks from a **defensive cybersecurity perspective**.

The simulation demonstrates the attack flow:

```text
User receives suspicious link
          ↓
User opens webpage
          ↓
Fake login interface appears
          ↓
User enters test credentials
          ↓
Browser sends POST request
          ↓
Flask backend receives form data
          ↓
Server processes the request
          ↓
User is redirected
```

Understanding this workflow helps security learners recognize the warning signs of phishing attacks and understand how credential-harvesting techniques operate.

---

## 🧠 Problem Statement

Phishing attacks frequently exploit **user trust** rather than technical vulnerabilities.

Attackers may create login pages that visually resemble trusted services and distribute them through malicious or deceptive links. Users who fail to verify the destination URL may unknowingly submit sensitive information.

This project demonstrates this concept in a controlled environment so that students and cybersecurity learners can understand:

> **How a visually convincing login page can manipulate users into submitting information.**

---

## 💡 How This Project Demonstrates the Problem

The frontend contains a Microsoft-style login interface with elements such as:

* Microsoft-style branding
* Email / phone / Skype input
* Password input
* "Keep me signed in" option
* Sign-in button
* Forgot password link
* Create account link
* Responsive layout
* Password visibility toggle

The login interface is implemented directly in HTML/CSS/JavaScript rather than being generated using a dedicated phishing framework.

When the form is submitted, JavaScript sends the entered form fields to the Flask backend through a `POST` request to `/login`.

---

## 🏗️ Architecture

```text
                   ┌─────────────────────┐
                   │       Browser       │
                   │                     │
                   │  HTML/CSS/JavaScript│
                   └──────────┬──────────┘
                              │
                              │ POST /login
                              │
                              ▼
                   ┌─────────────────────┐
                   │    Flask Backend    │
                   │      server.py      │
                   └──────────┬──────────┘
                              │
                              ▼
                   ┌─────────────────────┐
                   │ Form Data Processing│
                   │                     │
                   │ email / password    │
                   └──────────┬──────────┘
                              │
                              ▼
                   ┌─────────────────────┐
                   │  Educational Demo   │
                   │      Output         │
                   └─────────────────────┘
                              │
                              ▼
                   Redirect to Microsoft
```

The backend defines a `/login` endpoint that receives form data and processes it using Flask.

---

## 🛠️ Technology Stack

| Technology     | Purpose                                 |
| -------------- | --------------------------------------- |
| **HTML5**      | Login interface structure               |
| **CSS3**       | Interface styling and responsive design |
| **JavaScript** | Form handling and frontend interaction  |
| **Python**     | Backend programming                     |
| **Flask**      | Web server / backend framework          |
| **Gunicorn**   | Production WSGI server                  |
| **Render**     | Cloud deployment                        |

The repository's `requirements.txt` currently specifies Flask and Gunicorn.

---

## 📂 Project Structure

```text
Phishing_page/
│
├── phishing/
│   ├── index.html
│   ├── server.py
│   └── requirements.txt
│
├── image.png
│
└── README.md
```

### `index.html`

Contains the frontend login simulation.

It includes:

* Login form
* Microsoft-style interface
* CSS styling
* Password visibility toggle
* JavaScript form submission
* Redirect behavior

The current implementation contains approximately 309 lines of HTML/CSS/JavaScript.

### `server.py`

Contains the Flask backend.

It provides:

```text
/
```

for serving the login page and:

```text
/login
```

for processing form submissions.

### `requirements.txt`

Contains the Python dependencies:

```text
Flask
gunicorn
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/hitesh169/Phishing_page.git
```

### 2. Enter the project directory

```bash
cd Phishing_page
```

### 3. Enter the application directory

```bash
cd phishing
```

### 4. Create a virtual environment

```bash
python -m venv venv
```

### 5. Activate the virtual environment

#### Windows

```bash
venv\Scripts\activate
```

#### Linux / macOS

```bash
source venv/bin/activate
```

### 6. Install dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Running Locally

Start the Flask application:

```bash
python server.py
```

The application will start locally.

Open:

```text
http://127.0.0.1:5000
```

The backend is configured to serve `index.html` from the same application directory.

---

## 🔬 Demonstration Workflow

For an authorized educational demonstration:

1. Start the Flask server.
2. Open the application locally.
3. Observe the simulated login interface.
4. Use **dummy/test data only**.
5. Submit the form.
6. Observe how the frontend communicates with the backend.
7. Inspect the server-side processing.
8. Observe the redirect behavior.

### ⚠️ Use Dummy Data

Example:

```text
Email: test@example.com
Password: EDUCATIONAL_TEST_PASSWORD
```

**Do not use:**

* Real Microsoft accounts
* Real passwords
* Real employee credentials
* Other people's information
* Production credentials

---

## 🌐 Deployment

The project can also be deployed as a web application using a cloud hosting platform such as **Render**.

A typical deployment architecture is:

```text
Internet
   │
   ▼
Render
   │
   ▼
Gunicorn
   │
   ▼
Flask Application
   │
   ├── index.html
   └── /login
```

The repository includes Gunicorn as a dependency, allowing the Flask application to be served using a production WSGI server.

---

## 🔐 Security & Ethical Considerations

This project intentionally demonstrates a technique associated with real-world phishing attacks.

Therefore:

### ✅ Allowed Uses

* Cybersecurity education
* Personal lab environments
* Phishing-awareness demonstrations
* Security training
* Authorized penetration-testing exercises
* Academic projects
* Controlled security research

### ❌ Prohibited Uses

Do not use this project to:

* Steal credentials
* Collect real passwords
* Impersonate organizations without authorization
* Target unsuspecting users
* Conduct unauthorized phishing campaigns
* Distribute malicious links
* Access accounts belonging to other people
* Deploy against real organizations without written authorization

---

## 🛡️ Defensive Lessons

This project demonstrates several important phishing indicators.

### 1. Check the URL

A webpage may look legitimate while the domain is completely different.

Always inspect the actual domain before entering credentials.

### 2. Do Not Trust Visual Appearance

Attackers can reproduce the appearance of popular services using ordinary HTML and CSS.

A professional-looking page does **not** prove that the website is legitimate.

### 3. Verify the Domain

Before logging in, verify that the browser is actually communicating with the legitimate service.

### 4. Use Multi-Factor Authentication

MFA provides an additional layer of protection if a password is compromised.

### 5. Be Careful With Links

Do not blindly open login links received through:

* Email
* SMS
* Social media
* Messaging applications
* Unknown websites

---

## 📚 Cybersecurity Concepts Demonstrated

This project provides hands-on exposure to:

* Phishing
* Social engineering
* Credential harvesting concepts
* HTTP requests
* HTTP POST
* Web forms
* Client-server architecture
* Flask routing
* Frontend/backend communication
* Web deployment
* Security awareness
* Attack-simulation methodology

---

## 🔄 Request Flow

The frontend uses JavaScript to submit the login form to:

```text
POST /login
```

The request contains the form fields in URL-encoded form.

The Flask application receives these fields using:

```python
request.form.get(...)
```

and returns a JSON response after processing the request.

---

## 🚧 Limitations

This is an educational demonstration rather than a production authentication system.

Current limitations include:

* No real authentication system
* No database
* No secure credential storage
* No user account management
* No MFA implementation
* No phishing campaign management
* No analytics dashboard
* No email delivery system
* No threat-intelligence integration

These limitations are intentional because the objective is to demonstrate the basic mechanics of a phishing-style web interface.

---

## 🚀 Future Improvements

Possible **defensive/educational** improvements include:

* Add an awareness-training mode
* Replace credential collection with harmless simulated events
* Add a warning banner after form submission
* Create a phishing-awareness dashboard
* Record only non-sensitive training metrics
* Add URL/domain awareness exercises
* Add simulated phishing email examples
* Add detection rules for suspicious URLs
* Integrate the project with a SOC training environment
* Generate educational reports for security awareness exercises

---

## 🎓 Educational Value

This project demonstrates that creating a convincing phishing-style interface does not necessarily require a specialized phishing framework.

Basic web technologies such as:

```text
HTML
   +
CSS
   +
JavaScript
   +
Python/Flask
```

can be combined to understand the fundamental client-server behavior involved in a phishing simulation.

For a cybersecurity student, the more important lesson is not **how to steal credentials**, but **how these attacks work so they can be detected, prevented, and investigated.**

---

## 👨‍💻 Author

**Hitesh Aggarwal**

Cybersecurity Student | Aspiring SOC Analyst

GitHub:
https://github.com/hitesh169

---

## 📄 Disclaimer

This repository is provided strictly for **educational and authorized security-testing purposes**.

The author does not encourage, support, or authorize unauthorized phishing, credential theft, impersonation, fraud, or attacks against real users or organizations.

Use this project only in environments where you have explicit permission to perform security testing.

**Never submit real credentials to this application.**
