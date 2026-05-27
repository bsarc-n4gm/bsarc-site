---
title: "Winlink Exercise #002: Standard Templates & Winlink Check-in Forms"
date: 2025-11-17
draft: false
description: "Training exercise focusing on launching standard Winlink templates, navigating general ICS/EmComm forms, and executing automated check-in procedures."
---

📬 [← Return to Winlink Operations Dashboard](emergency-comms/winlink/)

---

### 🏛️ Brunswick County ARES Winlink Net — Session #002

* **Net Session Start:** Monday, November 17th at 12:01 AM
* **Net Session End:** Saturday, November 29th at 11:59 PM
* **Designated Net Control Station (NCS):** Send your completed Winlink data message to **`K1MJJ`** (or `K1MJJ@winlink.org`).

<div style="background-color: #fef8f5; border-left: 5px solid #f0a150; padding: 15px; margin: 20px 0; border-radius: 4px; font-family: sans-serif;">
  <strong style="color: #b05000;">🦃 Holiday Operations Notice:</strong> 
  <span style="color: #c07010; display: block; margin-top: 5px; font-size: 14px;">
    In observance of the Thanksgiving holiday, we will take this session at an easy, accessible pace. Because our operational roster serves volunteers with a wide variance of Winlink proficiency, we are securing our core foundations first. Advanced technical field deployments will follow soon!
  </span>
</div>

---

### 🎯 Scenario Framework
When tasked with establishing emergency staging communications for a **Served Agency** (such as local fire districts, shelters, or public safety checkpoints), you must formally report your deployment presence to the main Emergency Operations Center (EOC). This exercise trains operators to utilize standard software templates to transmit structured, lightweight check-in strings.

---

### 🛠️ Assigned Task Flow
Launch the browser-driven **Winlink Check-in** form template, populate your station location tracking details, input your local weather telemetry observations, and route the finished format string over a standard session link to **`K1MJJ`**.

#### Phase 1: Locating and Launching the Form Template
1. Launch your primary **Winlink Express** client.
2. From the top navigation bar, click on **Message** and select **New Message**.
3. Inside the new message window header, click on **Select Template**.
4. In the template selection folder layout, expand the **Standard Forms** directory.
5. Expand the **General Forms** subfolder directory tier.
6. Locate and double-click **`Winlink Check-in.txt`**. This actions the form engine to boot an interactive data screen inside your default web browser.

---

#### Phase 2: Interacting with the Form Interface

##### 🏷️ Form Header Setup
* Click on the **Setup** button located near the top of the browser page.
* In the text input popup prompt, carefully type exactly: `Brunswick County ARES Winlink Net`
* Click **OK** to lock the network ID string.

##### 📡 STATION Settings Block
* **Operation Incident/Exercise ID:** `Session 002`
* **Date/Time:** Click inside the date/time box to immediately snapshot and sync your computer's current real-time system stamp.
* **To:** `K1MJJ`
* **From:** `[Your Call Sign]`
* **Station Contact Name:** `[Your First and Last Name]`
* **Initial Operator:** `[Your Name, Your Call Sign]`

##### 🗓️ SESSION Parameters Block
* **Type:** Select `Exercise` from the radio options.
* **Service:** Select `Amateur`.
* **Band:** Select `Telnet`.
* **Session:** Select `Telnet`.

##### 📍 LOCATION Tracking Block
* **Location:** Input your complete residential/station street address.
* **Latitude & Longitude:** Input your home coordinates. *(Note: If you pre-configured your exact Maidenhead Grid Square details inside your global Winlink Express settings profile, this block will populate automatically).*

##### 💬 COMMENTS Data Box
Populate the comment block precisely across three separate lines:
* **Line 1:** `This is an exercise!!!`
* **Line 2:** `[Your Call Sign], [Your Name], [Your City], [Your County], [Your State]`
* **Line 3:** `[Current Temperature], [Wind Speed & Direction], [Current Barometer Reading at your home QTH]`

---

#### Phase 3: Final Form submission & Transmission Link
1. Once you double-check your station parameters, click the **Submit** button at the bottom of the webpage interface.
2. Click **OK** on any system acknowledgement or formatting popup prompts that validate your data payload.
3. Close the web browser tab or window.
4. Return to your Winlink Express message compose frame and verify that the core underlying data string has successfully generated and that **`K1MJJ`** sits in the **To:** box.
5. Click **Post to Outbox** on the top toolbar.
6. From the main screen dropdown list, change your session profile type to **Open Session: Telnet Winlink**.
7. In the newly launched session command block window, click **Start**.
8. Observe the data connection pipeline handshake, log the outbound verification index, and monitor until the system states your check-in payload has successfully cleared the outbound queue.

**Congratulations, you have successfully executed Exercise #002!**

---

### 🙋 Help Desk Support & Inquiries
If your template engine freezes, fails to launch the browser UI, or you encounter localized setting sync errors, please drop an inquiry over standard internet lines straight to Bob's address at [K1MJJ.Ham@gmail.com](mailto:K1MJJ.Ham@gmail.com).