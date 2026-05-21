# 📻 Brunswick Shores Amateur Radio Club (BSARC) - Web Platform Manual

Welcome to the official station log and technical operating manual for the **BSARC Website Source Framework** (`n4gm.org`). This platform utilizes the **Hugo Static Site Generator** paired with the customized **Ananke Theme** to compile an ultra-fast, modern, database-free web application hosted entirely via **GitHub Pages**.

---

📂 Data Sheets Reference Guide (/data/)

To guarantee seamless succession transitions for upcoming club officers and volunteers, the layout templates have been decoupled entirely from raw content. You do not need to understand HTML grid spacing, tables, or CSS layout code to update the website. Simply modify the structured text configuration parameters inside the files within the data/ folder:
🏠 1. Homepage Registry (data/homepage.toml)

Controls core text elements, routine net schedules, and background info markers displayed on the front screen dashboard layout.

    [banner] -> Alters the primary background header picture graphic path layout asset and alternate text descriptions.

    [welcome] -> Houses the landing page greetings text, subtitle notes, and modification dates.

    [[nets]] -> List array containing your weekly Shrimp NET and AUXCOM parameters. To add an entire new routine net, copy a group blocks section from [[nets]] to time and paste it directly underneath.

    [[repeaters]] -> Updates the core infrastructure logs panel in your sidebar column.

📅 2. Event Itinerary Almanac (data/calendar.toml)

Manages your club activity calendar, VE testing milestones, hamfests, and community field deployments.

    Strict Date Formatting (date = "YYYY-MM-DD"): This layout variable field must remain fully standardized (e.g., "2026-06-27"). The site uses this parameter string to automate date-sorting logic math behind the scenes.

    Automated Calendar Archiving: Events scheduled for today or the future will cleanly group themselves by month under bold text headings at the top of the calendar. The millisecond an event date passes, the shortcode engine automatically shifts it into a clean, collapsible accordion history drawer at the bottom of the page to eliminate scroller clutter.

    🔒 Secure Zoom Meeting Toggle (zoom_meeting = true/false): To safeguard your remote conferencing windows from automated bots or web-scraping utilities, set this key parameter to true (lowercase, no quotation marks) on any meeting block. The website code will intercept the flag and print a professional, unclickable lock icon notice instructing members to check their private club email bulletin for the hidden meeting link.

🔄 3. Swapfest Marketplace Dashboard (data/forsale.toml)

Manages the interactive equipment marketplace rosters. Copied entries must explicitly containerize every layout key to prevent data parsing crashes.

    price = "$500" -> Standard cash price entry string formatting wrapper.

    sold = true -> Fades out the item listing card background, slashes a strike-through line across titles, strips off email action links, and attaches a red ❌ SOLD flag.

    free = true -> Instantly bypasses cash price rendering and introduces a premium purple highlight banner block reading 🎁 FREE TO GOOD HOME.

🚨 4. Tactical Emergency Notices (data/notice.toml)

Allows individual appointed Emergency Coordinators (ECs) or PIO operators to issue broadcast advisories without accessing full website settings.

    active = true -> Drops a thick, beautiful alert message block right at the top of the main homepage content column. Set to false to clear the notice away.

    color = "danger" -> Swaps styles instantly based on severity fields. Options include:

        "danger" -> Bold crimson red block for heavy weather developments, Skywarn flags, or cancelled meetings.

        "warning" -> Amber yellow block for local advisories, upcoming dues deadlines, or routine test reminders.

        "info" -> Calm ocean blue banner block for general special event news.

    link_button_active = true -> Draws an action button inside the alert that maps out to a deep subpage (/notice/). This page parses your ongoing chronological line-by-line [[updates]] log feed timeline wire as an activation window unfolds.

🗞️ 5. Automated Weekly Bulletins Pipeline (/content/bulletins/)

Weekly updates compiled by the Club Secretary are handled through an automated multi-file content queue execution framework:
1. Creating a New Dispatch

To broadcast a brand-new weekly update, simply create a fresh, individual Markdown source file directly inside your content/bulletins/ folder path using the date naming convention (e.g., bulletin-2026-05-21.md). Paste this exact front matter block at the absolute top:
Markdown

---
title: "Weekly Bulletin: Write Your Core Focus Headline Here"
date: 2026-05-21
draft: false
---

### 📡 Active Dispatch Updates Go Here...

2. How the Automated Sorting Framework Operates

The system completely handles site logistics dynamically based on your Front Matter parameters:

    The Homepage Spotlight: The system loops through your bulletins directory, isolates the file with the newest calendar date stamp parameter, and prints its summary block live inside the homepage sidebar 🗞️ Secretary's Desk panel module window automatically.

    The Historical Vault Landing Hub: The moment a newer bulletin file is uploaded, older dispatches are automatically transitioned down into your running master listing database subpage at /bulletin-archive/. They group themselves inside a custom chronological index block marked with highly visible 📅 Week of [Date] indicator badges without an admin ever having to update links manually!

👥 6. Membership Database (data/members.toml)

Manages the complete active alphabetical membership roster directory table.

    To add an entry, copy a full [[member]] block and paste it at the bottom.

    Fields map automatically to columns on the public index directory block. Keep strings wrapped in quotation marks.

🏛️ 7. Leadership & Committees (data/roster.toml)

Controls elected Board positions and appointed task chairs independently from the raw membership roster.

    [[officers]] -> Manages the core Board of Directors.

    [[committees]] -> Manages event chairs, food teams, trustees, and specialized volunteer roles.

🏗️ Folder Hierarchy Topography (Relative)

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


📝 Operators Syntax Rules Checklist

    Always Seal String Paths: Every textual input entry value MUST be nested safely inside double quotation marks ("Value").

    Booleans stay Lowercase: Logistical true/false logic parameter tags must remain fully lowercase and completely free of quotes (true or false).

    Sanitize Arrays: Bullet points inside data specification loops (specs = [ "Line 1", "Line 2" ]) must be fully comma-separated to keep the parser engine from throwing syntax exceptions.

Brunswick Shores Amateur Radio Club — Securing Reliable Communications for Southeastern North Carolina Since 2026.