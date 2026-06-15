---
title: "Amateur Radio Satellites & ISS Communications"
description: "Learn how to track low-Earth orbit amateur radio satellites and contact the International Space Station directly from Brunswick County."
keywords: ["amateur radio satellites", "ISS tracking", "ARISS frequencies", "BSARC", "ham radio North Carolina"]
date: 2026-06-13
draft: false
layout: "single"
---

<div style="text-align: center; margin-top: 20px; margin-bottom: 10px;">
  <img src="/images/satellite-comms-thumb.webp" alt="Contesting & DXing: Radiosport" style="max-width: 400px; width: 100%; height: auto; border-radius: 6px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
</div>

# Tracking and Working Amateur Radio Satellites

Working amateur radio satellites and chasing the International Space Station (ISS) is one of the most thrilling aspects of modern ham radio. Using nothing more than a handheld dual-band transceiver (VHF/UHF) and a small, hand-held directional antenna, you can bridge voice and data contacts over hundreds of miles via orbital spacecraft passing directly over Brunswick County.

---

## 🛰️ The International Space Station (ARISS) Frequencies

The International Space Station maintains an active amateur radio station onboard operated by astronauts through the ARISS program (Amateur Radio on the International Space Station). The crew uses these specific frequencies for voice repeaters, automatic digital packets, and scheduled school STEM outreach events.

| Operation Mode | ISS Transmit Frequency (Your RX) | ISS Receive Frequency (Your TX) | Access Tone / Settings |
| :--- | :--- | :--- | :--- |
| **FM Voice Cross-Band Repeater** | `437.800 MHz` (UHF) | `145.990 MHz` (VHF) | `67.0 Hz` CTCSS Tone |
| **Packet Radio / UHF APRS** | `437.825 MHz` (UHF) | `437.825 MHz` (UHF) | 1200 Baud AFSK AX.25 |
| **STEM School Contact Link** | `145.800 MHz` (VHF) | `145.800 MHz` (VHF) | FM Voice Line (Simplex) |

---

## 📻 Getting Started with Equipment

You do not need a massive multi-axis tracking antenna farm in your yard to get started. A robust, portable station can be carried in a single backpack:

1. **The Transceiver:** A full-duplex dual-band handheld radio (like the Kenwood TH-D72A or Yaesu FT-4XR) or an all-mode field radio (like the Icom IC-705). Full-duplex is ideal because it allows you to hear your own downlinked voice return simultaneously, confirming you have opened the satellite repeater.
2. **The Antenna:** A handheld dual-band directional antenna. The **Arrow II** or **Alaskan Arrow** cross-Yagi antenna is the club favorite, separating your VHF elements and UHF elements onto a clean, lightweight handheld boom.
3. **Tracking Software:** Satellites move fast across the sky, with typical passes lasting only 10 to 15 minutes. Use mobile or desktop apps to calculate exactly when a satellite will rise above the horizon in Carolina Shores:
   * **Gpredict** (Free/Open Source for Zorin OS / Linux desktop)
   * **Heavens-Above** (Web & Mobile tracking engine)
   * **AmsatDroid** / **SatSat** (Mobile tracking apps)

---

## 🔄 Overcoming Doppler Shift

Because satellites travel at approximately 17,500 miles per hour in Low Earth Orbit (LEO), the radio frequency shifts as it approaches and pulls away from your station—exactly like the pitch change of a passing police siren. 

To stay cleanly inside the channel during a 10-minute voice pass, you must program memory channels into your radio to manually adjust your tuning:

* **Pass Entrance (Approaching):** Tune your receive radio slightly higher (**`437.810 MHz`**) as the compression pushes the wave.
* **Mid-Pass (Apex overhead):** Tune to the nominal center frequency (**`437.800 MHz`**).
* **Pass Exit (Receding):** Tune your receive radio slightly lower (**`437.790 MHz`**) as the expanding wave stretches out.

---

<div style="margin-top: 40px; padding: 20px; background-color: #f5f7f8; border-left: 4px solid #5e35b1; border-radius: 4px; font-family: sans-serif;">
  <strong>🚀 Looking for an ISS Pass?</strong> Keep your eyes on the BSARC club calendar and announcements channel. When a high-elevation orbital path cleanly intersects Calabash and Carolina Shores during club hours, members frequently assemble field tracking stations at the park to demonstrate active satellite tracking and voice capture live.
</div>