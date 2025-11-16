# 🤖 Behaviour-Based CAPTCHA Bot Detection  
_A machine learning model that classifies users as human or bot using behavioural analytics and honeypot field detection._

## 📌 Overview
This project implements a **Random Forest Classifier** that identifies whether a user is a **human** or **bot** based on their behavioural interaction patterns while filling a form.  
Unlike traditional CAPTCHAs, this method uses **natural user behaviour**, which is extremely hard for bots to mimic.

This ML-powered CAPTCHA alternative is:
- 🔥 Faster and lightweight  
- 🔒 Harder for bots to bypass  
- 🙌 More user-friendly  
- 🤖 Effective even against modern AI-based bots  

---

## 🎯 Problem Statement
Conventional CAPTCHAs (text/image puzzles) are:
- Irritating to real users  
- Often insecure  
- Easy for advanced bots and GPT-based solvers  

This project replaces the outdated CAPTCHA with **behavioural biometrics**, allowing the system to detect bots silently.

---

## 🧩 Features Used for Behaviour Analysis

Below are the **exact behavioural attributes** used in the model:

---

### **1️⃣ Keystroke Dynamics**
| Feature | Description |
|---------|-------------|
| **Average Keystroke Interval** | Time gap between key presses. Humans are slower + inconsistent. |
| **Typing Speed** | Total characters / total typing time. |
| **Backspace Count** | Humans correct mistakes; bots rarely do. |
| **Key Press Variability** | Humans have natural rhythm variation; bots use constant timings. |

---

### **2️⃣ Mouse Movement Metrics**
| Feature | Description |
|---------|-------------|
| **Cursor Path Length** | Distance covered by mouse while filling the form. |
| **Cursor Speed** | Humans vary their speed; bots are linear and constant. |
| **Idle Time** | Humans pause while thinking; bots don’t. |
| **Pointer Jitter** | Tiny random movements natural to humans. |
| **Click Timing Patterns** | Bots click instantly; humans take time. |

---

### **3️⃣ Interaction Behaviour**
| Feature | Description |
|---------|-------------|
| **Field Focus Change Count** | Humans switch between fields naturally; bots follow a fixed order. |
| **Time Spent Per Field** | Humans take time to think; bots complete fields uniformly fast. |
| **Form Completion Time** | Same form takes variable time for humans, fixed for bots. |
| **Field Fill Order Pattern** | Bots fill in sequential predictable order. |

---

### **4️⃣ Honeypot Field Technique (Explained)**

A **honeypot** is a hidden input field placed inside the form:

```html
<input type="text" name="extra-info" id="trap-field" style="display:none">
