# 📻 Brunswick Shores Amateur Radio Club (BSARC) - Web Platform Manual

Welcome to the official station log and technical operating manual for the **BSARC Website Source Framework** (`n4gm.org`). This platform utilizes the **Hugo Static Site Generator** hosted entirely via **GitHub Pages** for ultra-fast, modern, database-free web operations.

---

🏗️ Web Framework Directory Topography

This tree documents the exact core structure of the live site framework. Files outside this map handle base compiling modules and should not be altered during routine administration:
Plaintext
```bash
/home/mark/bsarc-site/
├── data/                           # 📂 MASTER STRUCTURAL TEXT SHEETS (MAIN WORKSPACE)
│   ├── calendar.toml               # Chronological club activities & exam logs sheet
│   ├── forsale.toml                # Active ham radio swapfest marketplace entries
│   ├── homepage.toml               # Front dashboard text strings and net frequency lists
│   ├── members.toml                # Complete verified active club member registry table
│   ├── notice.toml                 # Tactical emergency alert banners config matrix
│   └── roster.toml                 # Elected corporate board roles and committee chairs
├── content/                        # 📄 PUBLIC WEBSITE EDITABLE CORE PAGES
│   ├── _index.md                   # Home screen metadata initialization routing anchors
│   ├── ares.md                     # Amateur Radio Emergency Service overview node
│   ├── arrl.md                     # American Radio Relay League affiliate profiles
│   ├── board.md                    # Officers & Volunteers list container layout
│   ├── bulletin-archive.md         # The main listing database page for past dispatches
│   ├── bulletins/                  # 🗞️ RAW WEEKLY DISPATCH MARKDOWN QUEUE
│   │   ├── bulletin-2026-01-05.md  # Individual weekly bulletin file source entry nodes
│   │   └── [ ... remains chronological ... ]
│   ├── calendar.md                 # Subpage layout container serving the Master Itinerary
│   ├── fcc-renewal.md              # Reference instructions guide for licensing renewals
│   ├── forsale.md                  # Equipment swapfest market marketplace hub route
│   ├── gallery.md                  # Media layout grid container for event pictures
│   ├── links.md                    # Extracted reference links collection catalog
│   ├── notice.md                   # Active Incident tactical timeline log page
│   ├── qsl-info.md                 # DX collection bureaus and confirmation routes
│   ├── repeaters.md                # Hardware coordinate lists for regional hf/vhf systems
│   ├── roster.md                   # Alpha directory membership roster table container
│   ├── skywarn.md                  # Severe weather spotter training notification link
│   ├── uunaa.md                    # Club history archive logs parameters sheet
│   └── welcome-kit.md              # Onboarding handbook kit guide line for new hams
├── layouts/                        # 🎨 PRODUCTION PRESENTATION OVERRIDE BLUEPRINTS
│   ├── index.html                  # Base template entry route initialization point
│   ├── _default/                   
│   │   ├── dashboard.html          # Main double-column index frame architecture layout
│   │   ├── single.html             # Base structural template loop styling single articles
│   │   └── _markup/                
│   │       └── render-link.html    # Specialized script mapping relative subpage URLs
│   └── shortcodes/                 # Presentation snippets triggered inside markdown pages
│       ├── bulletin_vault.html     # Compiles your stylized bulletin history archive blocks
│       ├── calendar_updated.html   # Sandbox parsing file for calendar processing tests
│       ├── club_calendar.html      # Automated 3-month homepage rolling upcoming window
│       ├── club_roster.html        # Loops elected board profiles and appointed task grids
│       ├── gallery_grid.html       # Auto-compiles horizontal multi-image layout matrix
│       ├── incident_log.html       # Chronological emergency tactical timeline logger element
│       ├── master_calendar.html    # Automated active future grids & past archive details drawer
│       ├── member_directory.html   # Logic loops compiling membership columns alphabetically
│       ├── repeater_table.html     # Compiles active infrastructure frequency logs metrics
│       ├── swap_listings.html      # Marketplace equipment listing card block template loop
│       └── toc.html                # Auto-generates interactive floating Tables of Contents
└── static/                         # 🖼️ PERMANENT UNCHANGING WEB GRAPHIC MEDIA VAULTS
    ├── images/                     # Club vectors, icons, badges, and seasonal banners
    │   ├── ares_logo.svg
    │   ├── arrl_logo.webp
    │   ├── bsarc_repeater_logo.webp
    │   ├── club_banner.webp
    │   ├── club_logo.webp
    │   ├── skywarn.svg
    │   └── www_icon.png
    ├── media/                      # Chronological event folders serving gallery matrices
    │   ├── 2008/oak-island-2008/
    │   ├── 2023/old-baldy-2023/
    │   ├── 2024/field-day-2024/
    │   └── 2025/cp-2025/
    └── pdf/                        # Legal charter bylaws and fillable application forms
        ├── amateur_test_sessions.pdf
        ├── ares_member_registration.pdf
        ├── arrl_band_plan.pdf
        ├── bsarc_articles_of_formation.pdf
        ├── bsarc_by_laws.pdf
        ├── bsarc_membership_application.pdf
        ├── bsarc_sro.pdf
        └── weekly_bulletin.pdf
```
---

📂 Data Sheets Reference Guide (/data/)

---
To guarantee seamless succession transitions for upcoming club officers and volunteers, the layout templates have been decoupled entirely from raw content. You do not need to understand HTML grid spacing, tables, or CSS layout code to update the website. Simply modify the structured text configuration parameters inside the files within the data/ folder:

### 🏠 1. Homepage Registry (`data/homepage.toml`)

Controls core text elements, scheduled routine radio nets, alternating monthly meeting coordinates, and backend repeater status variables displayed across the front screen dashboard columns.

#### 💡 Strict Formatting Rules:
* **String Wrapped Values:** All text descriptions, names, dates, and frequencies MUST remain fully nested inside double quotation marks (`"Value"`).
* **Booleans stay Lowercase:** Binary configuration options must be explicitly written in lowercase without quotation marks (`true` or `false`).
* **Syntax Blocks Type Legend:**
  * **Single Brackets `[like_this]`:** Defines a standalone configuration section that renders exactly **ONCE** on the page. Tweaking fields updates that specific location; do not duplicate these headers.
  * **Double Brackets `[[like_this]]`:** Defines an array map index. This acts as a repeater list. You can cleanly copy/paste a full block section to add an extra line entry row automatically.

#### 📦 Individual Table Sections Reference:

* **🖼️ Seasonal Header Banner (`[banner]`):** Sets the graphic asset path and description for your centerpiece top header background layout.
  * `image` -> Targets your current active season layout vector (e.g., `"/images/club_banner_spring.webp"`). To shift seasons on the live server, move the comment hash (`#`) to toggle out paths.
  * `alt` -> Alternate screen-reader metadata string descriptive wrapper.
* **📝 Welcome Greetings Matrix (`[welcome]`):** Standard text entry fields updating the dashboard primary landing header.
  * `heading` & `subheading` -> Primary layout bold text headers.
  * `text` -> The primary background context paragraph block welcoming new newcomers.
  * `last_updated` -> Text string stamping your maintenance cycles directly onto the dashboard.
* **🎙️ Routine Net Lists (`[[nets]]`):** Repeated data loops populating your "Club Net Schedules" index frame table.
  * Keys include `name`, `freq`, and `time`. To add a net, duplicate a complete `[[nets]]` array chunk and drop it directly below the previous item.
* **🏛️ Meeting Alternation Schedules (`[meetings.monthly]`, `[[meetings.locations]]`, & `[meetings.breakfast]`):** Coordinates text frames and automates the alternating location table outputs.
  * `[meetings.monthly].text` -> Handles descriptive text regarding general operations and Zoom email distribution notices.
  * `[[meetings.locations]]` -> Multi-row tracking map evaluating months (e.g., `months = "Jan, Mar, May..."`) against the facility `name` and `address`. Hugo iterates over these loops to draw the alternate schedule matrix card blocks automatically.
  * `[meetings.breakfast].text` -> Updates the day, hour, and restaurant address mapping logs for the informal mid-week gatherings.
* **⚡ Repeater Infrastructure Metrics (`[[repeaters]]`):** Feeds technical specifications directly into your active dashboard hardware column block lists.
  * Keys require exact parameter lines: `frequency`, `offset`, `tone`, `location`, and `notes`. To add or decommission a repeater, simply add or remove an entire `[[repeaters]]` bracket matrix array stack block.

### 📅 2. Event Itinerary Almanac (`data/calendar.toml`)

Manages your deep annual club activity schedule, scheduled Volunteer Examiner (VE) testing milestones, regional hamfests, public service deployments, and special club functions.

#### 💡 Strict Formatting Rules:
* **System Date Target (`date = "YYYY-MM-DD"`):** Text format string matching strict syntax (e.g., `"2026-06-27"`). The site layouts utilize this exact string to run mathematical sorting loops.
* **Homepage Rolling 90-Day Window:** The landing column automatically filters the data array, hiding items scheduled further out than **90 days from today** to maintain a compact dashboard view.
* **Display Date (`display_date = "text"`):** Dictates exactly what text label prints on screen to users (e.g., `"January 24-25"` or `"June 10"`).
* **Isolated Hour Tag (`time = "text"`):** Isolates the meeting hour cleanly across table headers (e.g., `"6:00 PM"`). Leave as empty quotes `""` if not applicable.
* **String Values:** All text parameters must be securely wrapped inside double quotation marks (`""`).

#### 🛠️ Automated Smart-Link Badge Engine (Routing Rules):
The shortcode template evaluates your parameters line-by-line to render optimized UI badges on the fly. Every parameter key must be defined—use empty quotation marks `""` if a link or path is missing.

* **🔒 Secure Zoom Meeting Toggle (`zoom_meeting = true/false`):** Set to `true` (lowercase, no quotes) to automatically overlay a secure, unclickable lock shield layout over the event card. This warns bots and displays a notice instructing members to retrieve the link out of their private email dispatch.
* **❌ Event Cancellations (`canceled = true/false`):** Setting to `true` forces an immediate crimson alert border, strikes a line across titles, masks action links, and appends an alert banner reading: `🚫 Called off due to scheduling logistics.`
* **📻 On-Air / Net Badges:** If the `location` field text includes keywords like *"Air"*, *"Net"*, *"Remote"*, or *"Conference"*, the system auto-seals the card into a clean, unclickable info badge.
* **📍 Physical Venue GPS Routing:** If the `location` field contains a standard facility street address, the template intercepts the string and automatically generates an interactive blue action button linked directly to **Google Maps GPS Navigation**.
* **🌐 External Web Info Links (`link_url = "https://..."`):** If populated with an active web link, the card automatically generates a blue **"🌐 Visit Event Website"** interactive action shortcut.
* **📄 Media Flyer Downloads (`flyer_path = "/pdf/flyer.pdf"`):** If populated with a relative file pathway pointing to your static directory vault, the card automatically hooks up an orange **"📄 View Event Flyer (PDF)"** download target button.

#### 📁 Chronological Pipeline Archiving:
Events today or in the future group themselves under bold text chapter headers corresponding to the month and year of operation. The exact millisecond an event date passes, the shortcode layout engine automatically strips the card layout, compiles it down into a simplified table row entry, and relocates it inside a collapsible accordion history drawer at the bottom of the page to eliminate scrolling clutter indefinitely.

🔄 3. Swapfest Marketplace Dashboard (`data/forsale.toml`)

Manages the interactive equipment marketplace rosters. Copied entries must explicitly containerize every layout key to prevent data parsing crashes.

    price = "$500" -> Standard cash price entry string formatting wrapper.

    sold = true -> Fades out the item listing card background, slashes a strike-through line across titles, strips off email action links, and attaches a red ❌ SOLD flag.

    free = true -> Instantly bypasses cash price rendering and introduces a premium purple highlight banner block reading 🎁 FREE TO GOOD HOME.

🚨 4. Tactical Emergency Notices (`data/notice.toml`)

Allows individual appointed Emergency Coordinators (ECs) or PIO operators to issue broadcast advisories without accessing full website settings.

    active = true -> Drops a thick, beautiful alert message block right at the top of the main homepage content column. Set to false to clear the notice away.

    color = "danger" -> Swaps styles instantly based on severity fields. Options include:

        "danger" -> Bold crimson red block for heavy weather developments, Skywarn flags, or cancelled meetings.

        "warning" -> Amber yellow block for local advisories, upcoming dues deadlines, or routine test reminders.

        "info" -> Calm ocean blue banner block for general special event news.

    link_button_active = true -> Draws an action button inside the alert that maps out to a deep subpage (/notice/). This page parses your ongoing chronological line-by-line [[updates]] log feed timeline wire as an activation window unfolds.

🗞️ 5. Automated Weekly Bulletins Pipeline (`/content/bulletins/`)

Weekly updates compiled by the Club Secretary are handled through an automated multi-file content queue execution framework:

1. Creating a New Dispatch

To broadcast a brand-new weekly update, simply create a fresh, individual Markdown source file directly inside your content/bulletins/ folder path using the date naming convention (e.g., bulletin-2026-05-21.md). Paste this exact front matter block at the absolute top:
Markdown

```text
---
title: "Weekly Bulletin: Write Your Core Focus Headline Here"
date: 2026-05-21
draft: false
---
```

### 📡 Active Dispatch Updates Go Here...

2. How the Automated Sorting Framework Operates

The system completely handles site logistics dynamically based on your Front Matter parameters:

    The Homepage Spotlight: The system loops through your bulletins directory, isolates the file with the newest calendar date stamp parameter, and prints its summary block live inside the homepage sidebar 🗞️ Secretary's Desk panel module window automatically.

    The Historical Vault Landing Hub: The moment a newer bulletin file is uploaded, older dispatches are automatically transitioned down into your running master listing database subpage at /bulletin-archive/. They group themselves inside a custom chronological index block marked with highly visible 📅 Week of [Date] indicator badges without an admin ever having to update links manually!

👥 6. Membership Database (`data/members.toml`)

Manages the complete active alphabetical membership roster directory table.

    To add an entry, copy a full [[member]] block and paste it at the bottom.

    Fields map automatically to columns on the public index directory block. Keep strings wrapped in quotation marks.

🏛️ 7. Leadership & Committees (`data/roster.toml`)

Controls elected Board positions and appointed task chairs independently from the raw membership roster.

    [[officers]] -> Manages the core Board of Directors.

    [[committees]] -> Manages event chairs, food teams, trustees, and specialized volunteer roles.


📝 Operators Syntax Rules Checklist

    Always Seal String Paths: Every textual input entry value MUST be nested safely inside double quotation marks ("Value").

    Booleans stay Lowercase: Logistical true/false logic parameter tags must remain fully lowercase and completely free of quotes (true or false).

    Sanitize Arrays: Bullet points inside data specification loops (specs = [ "Line 1", "Line 2" ]) must be fully comma-separated to keep the parser engine from throwing syntax exceptions.

Brunswick Shores Amateur Radio Club — Securing Reliable Communications for Southeastern North Carolina Since 2026.
