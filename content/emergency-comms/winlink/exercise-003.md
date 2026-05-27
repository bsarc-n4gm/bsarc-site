---
title: "Winlink Exercise #003: Winlink Catalog Requests & Image Attachments"
date: 2025-12-01
draft: false
description: "Training exercise focusing on utilizing the Winlink catalog system, handling satellite image retrieval, and managing RF payload file restrictions."
---

📬 [← Return to Winlink Operations Dashboard](emergency-comms/winlink/)

---

### 🏛️ Brunswick County ARES Winlink Net — Session #003

* **Net Session Start:** Monday, December 1st at 12:01 AM
* **Net Session End:** Saturday, December 13th at 11:59 PM
* **Designated Net Control Station (NCS):** Send your completed Winlink data message to **`K1MJJ`** (or `K1MJJ@winlink.org`).

<div style="background-color: #e3f2fd; border-left: 5px solid #2196f3; padding: 15px; margin: 20px 0; border-radius: 4px; font-family: sans-serif;">
  <strong style="color: #0d47a1;">🎄 Operational Notice:</strong> 
  <span style="color: #1565c0; display: block; margin-top: 5px; font-size: 14px;">
    Exercise #004 will launch in January. The leadership team wishes all our local volunteers a festive, safe Holiday Season! For now, let us sharpen our digital data skills with Exercise #003.
  </span>
</div>

---

### 🎯 Training Objectives
* Begin navigating and requesting files through the automated **Winlink Catalog**.
* Practice attaching local binary graphic files (.JPG) to structured Winlink message payloads.
* Observe physical payload file constraints and understand why optimizing size limits is vital when routing images across tight RF data pipelines.

---

### 🛠️ Assigned Task Flow
Draft and execute a standard Winlink message containing a retrieved satellite graphic attachment, answer the four core operational assessment questions, and route the final data package to **`K1MJJ`**.

#### Phase 1: Requesting and Retrieving the Satellite Photo
1. Open your Winlink client and navigate to **Settings &rarr; Winlink Catalog Requests**.
2. Scan the available directories for **`Sat_Pixs`** and select it.
3. In the center pane, locate **`GOES 16 Pic of U.S. Southeastern & Gulf States`** and double-click to select it.
4. Verify that **`SESTATE.JPG`** appears in the rightmost window pane.
5. Click the **Post Request** button.
6. Open your **Outbox** and confirm that a system generation query message is waiting from you to the recipient **`INQUIRY`**.
7. Initiate a session via **Telnet or RF** (your choice) to push the request out to the gateway network.
8. Wait a few moments for the automated servers to compile your image, then start a new session to pull down the reply message containing your satellite photo.

#### Phase 2: Analyzing the System Response
* Read the text message header provided by the Winlink Service regarding the underlying photo parameters.
* Click on the attached `SESTATE.JPG` graphic to review it, noting the exact timestamp and coverage parameters.
* **Save the photo file directly to your computer local drive.**

---

### 💡 Pro-Tip: Accessing the Image Optimization Guide
Before proceeding to the submission step, we highly recommend pulling down the native optimization instructions:
* Return to **Settings &rarr; Winlink Catalog Requests** and select **`WL2K_Help`**.
* Search the center pane for **`Photo.Reduce`**, double-click it, and click **Photo Request**.
* Route the request and read the resulting documentation to understand client-side compression tools.

---

### 📥 Phase 3: Final Message Generation & Submission
1. Open a fresh, standard message window in your Winlink client.
2. Address the message to **`K1MJJ`**.
3. **Attach the satellite photo** you previously saved to your station computer.
4. Observe the current size readout (in Kilobytes) of your attachment box:
   * *Experiment:* Attempt to scale or adjust the size parameters wider.
   * *Observation:* Watch the color code configuration changes inside the size indicator box.
   * *Adjustment:* Reset the size scale down until the indicator box background shifts safely back to **White**.
5. Clear the text field and copy/paste the following template, filling out your station's field data completely:

```text
EXERCISE: BRUNSWICK COUNTY EMCOMM WINLINK NET SESSION #003

[FIELD ASSESSMENT ANSWERS]
1. What did the Winlink Service have to do to the file before it sent it to you?
   - [Answer Here]

2. What is the new size layout of the photo in pixels after the Winlink Service modified it?
   - [Answer Here]

3. What does the shifting color indication window mean as you manually increase the size of the attachment?
   - [Answer Here]

4. In your opinion, why is it critical to keep data attachments as small as possible, especially if you are forced to route the packet via VHF/HF RF links?
   - [Answer Here]

[STATION OPERATIONS METRICS]
- Primary Session Routing Method Used: [e.g., Telnet / VHF Packet / VARA HF]
- Station Home QTH Latitude: [Your Latitude]
- Station Home QTH Longitude: [Your Longitude]