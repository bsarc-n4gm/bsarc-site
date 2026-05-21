Here is the fully updated and streamlined **`README.md`** file for your project repository.

It has been tailored to focus exactly on what your administrators and club officers need to manage day-to-day operations—specifically reflecting our new secure `zoom_meeting` boolean toggles, the custom multi-file `bulletins/` publishing architecture, and your clean, standalone `bulletin-archive.md` page routing.

Open **`README.md`** in VS Code and replace its entire contents with this copy-and-paste ready manual:

```markdown
# 📻 Brunswick Shores Amateur Radio Club (BSARC) - Web Platform Manual

Welcome to the official station log and technical operating manual for the **BSARC Website Source Framework** (`n4gm.org`). This platform utilizes the **Hugo Static Site Generator** paired with the customized **Ananke Theme** to compile an ultra-fast, modern, database-free web application hosted entirely via **GitHub Pages**.

---

## 🛠️ Quick Start Station Commands

To test modifications locally or deploy updates directly to the live server, open your Zorin terminal workspace at `/home/mark/bsarc-site` and execute these specific command line strings:

### 1. Launch Local Testing Sandbox Server
```bash
hugo server --bind 0.0.0.0 --baseURL [http://192.168.68.109](http://192.168.68.109) --port 1313 -D

```

* **Local Sandbox URL:** Open Firefox and navigate to `http://localhost:1313/`
* **Local Network IP Scaling:** View real-time layout rendering across mobile devices or tablets on your garage network via `http://192.168.68.109:1313/`.
* **Live-Reload Automation:** Any text content or data sheet modification saved inside VS Code will instantly recompile in milliseconds and automatically update your open browser window.

### 2. Lock in a Change Milestone & Push Live

```bash
git add .
git commit -m "docs(bulletins): publish weekly bulletin for current timeline"
git push origin main

```

* Pushing changes to the master `main` branch immediately alerts your automated GitHub Actions server compiler. The remote production pipeline will rebuild the entire platform and deploy your updates to the web within 30 seconds automatically.

---

## 📂 Data Sheets Reference Guide (`/data/`)

To guarantee seamless succession transitions for upcoming club officers and volunteers, the website's templates have been completely decoupled from the data blocks. **Administrators do not need to understand HTML grid spacing, tables, or CSS layouts to update core content.** Simply modify the structured text keys inside the files within the `data/` folder:

### 🏠 1. Homepage Registry (`data/homepage.toml`)

Controls text blocks, schedules, and active information cards displayed across the front screen grid rows.

* `[banner]` -> Modifies paths for seasonal background pictures and alternate text labels.
* `[welcome]` -> Houses your primary landing greetings headline text body.
* `[[nets]]` -> Updates the active rows inside your main screen "Club Net Schedules" data table layout.

### 📅 2. Event Itinerary Almanac (`data/calendar.toml`)

Manages your club activity calendar, VE testing milestones, hamfests, and community field deployments.

* **Strict Date Formatting (`date = "YYYY-MM-DD"`):** This layout variable field must remain fully standardized (e.g., `"2026-06-27"`). The site uses this parameter string to automate date-sorting logic math behind the scenes.
* **Automated Calendar Archiving:** Events scheduled for today or the future will cleanly group themselves by month under bold text headings at the top of the calendar. The millisecond an event date passes, the shortcode engine automatically shifts it into a clean, collapsible accordion history drawer at the bottom of the page to eliminate scroller clutter.
* **🔒 Secure Zoom Meeting Toggle (`zoom_meeting = true/false`):** To safeguard your remote conferencing windows from automated bots or web-scraping utilities, set this key parameter to `true` (lowercase, no quotation marks) on any meeting block. The website code will intercept the flag and print a professional, unclickable lock icon notice instructing members to check their private club email bulletin for the hidden meeting link.

### 🔄 3. Swapfest Marketplace Dashboard (`data/forsale.toml`)

Manages the equipment marketplace cards.

* `sold = true` -> Fades out the item listing card background, strikes a line across titles, strips off email paths, and attaches a bold red **❌ SOLD** flag automatically.
* `free = true` -> Overrides cash pricing brackets and introduces a purple highlight banner block reading **🎁 FREE TO GOOD HOME**.

### 🚨 4. Tactical Emergency Notices (`data/notice.toml`)

Allows individual appointed Emergency Coordinators (ECs) or PIO operators to issue broadcast advisories right at the top of the main content column.

* `active = true` -> Drops a thick, beautiful alert message block right at the top of the main homepage. Set to `false` to clear the notice away.
* `color = "danger"` -> Swaps styles instantly based on severity fields: `"danger"` (crimson red block), `"warning"` (amber yellow block), or `"info"` (ocean blue block).

---

## 🗞️ Automated Weekly Bulletins Pipeline (`/content/bulletins/`)

Weekly updates compiled by the Club Secretary are handled through an **automated multi-file content queue execution framework** rather than updating a single massive PDF link document:

### 1. Creating a New Dispatch

To broadcast a brand-new weekly update, simply create a fresh, individual Markdown source file directly inside your **`content/bulletins/`** folder path using the date naming convention (e.g., `bulletin-2026-05-21.md`). Paste this exact front matter block at the absolute top:

```markdown
---
title: "Weekly Bulletin: Write Your Core Focus Headline Here"
date: 2026-05-21
draft: false
---

### 📡 Active Dispatch Updates Go Here...

```

### 2. How the Automated Sorting Framework Operates

The system completely handles site logistics dynamically based on your Front Matter parameters:

* **The Homepage Spotlight:** The system loops through your bulletins directory, isolates the file with the newest calendar date stamp parameter, and prints its summary block live inside the homepage sidebar **🗞️ Secretary's Desk** panel module window automatically.
* **The Historical Vault Landing Hub:** The moment a newer bulletin file is uploaded, older dispatches are automatically transitioned down into your running master listing database subpage at `/bulletin-archive/`. They group themselves inside a custom chronological index block marked with highly visible **📅 Week of [Date]** indicator badges without an admin ever having to update links manually!

---

## 📝 Operators Syntax Rules Checklist

1. **Always Seal String Paths:** Every textual input entry value MUST be nested safely inside double quotation marks (`"Value"`).
2. **Booleans stay Lowercase:** Logistical true/false logic parameter tags must remain fully lowercase and completely free of quotes (`true` or `false`).
3. **Sanitize Arrays:** Bullet points inside data specification loops (`specs = [ "Line 1", "Line 2" ]`) must be fully comma-separated to keep the parser engine from throwing syntax exceptions.

---

*Brunswick Shores Amateur Radio Club — Securing Reliable Communications for Southeastern North Carolina Since 2026.*

```

---

### 🚀 Lock it Into Your Git Logs

Save this new blueprint manual. Open up your terminal command line and execute the sync commands to push the updated project manual safely to the GitHub servers:

```bash
git add README.md
git commit -m "docs(readme): update system manual to track secure zoom toggles and bulletins architecture"
git push origin main

```

Your documentation is now completely aligned with the premium website platform you have engineered!