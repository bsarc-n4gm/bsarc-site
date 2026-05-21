PDFs.
📝 The Blueprint: Copy and Paste into your README.md
Markdown

# 📻 Brunswick Shores Amateur Radio Club (BSARC) - Web Platform Manual

Welcome to the official station log and technical operating manual for the **BSARC Website Source Framework** (`n4gm.org`). This platform utilizes the **Hugo Static Site Generator** paired with the customized **Ananke Theme** to compile an ultra-fast, modern, database-free web application hosted entirely via **GitHub Pages**.

---

## 🛠️ Quick Start Station Commands

To test modifications locally or deploy updates directly to the live server, open your Zorin terminal workspace at `/home/mark/bsarc-site` and execute these specific command line strings:

### 1. Launch Local Testing Sandbox Server
```bash
hugo server --bind 0.0.0.0

    Local URL: Open Firefox and navigate to http://localhost:1313/

    Network URL: View layout scaling on tablets or smartphones using your local garage network IP layout (e.g., http://192.168.68.109:1313/).

    The sandbox features Live-Reloading—any text edit saved in VS Code will instantly refresh the browser view in milliseconds without needing to restart the process.

2. Lock in a Change Milestone & Push Live
Bash

git add .
git commit -m "type(scope): descriptive command message here"
git push origin main

    Pushing your commits to the master main branch immediately kicks off an automated cloud compiler actions sequence. The live servers at www.n4gm.org will complete rendering your new layout within 30 seconds automatically.

📂 Data Sheets Reference Guide (/data/)

To guarantee seamless succession transitions for upcoming club officers and volunteers, the layout templates have been decoupled entirely from raw content. You do not need to understand HTML grid spacing, tables, or CSS layout code to update the website. Simply modify the structured text configuration parameters inside the files within the data/ folder:
🏠 1. Homepage Registry (data/homepage.toml)

Controls core text elements, routine net schedules, and background info markers displayed on the front screen dashboard layout.

    [banner] -> Alters the primary background header picture graphic path layout asset and alternate text descriptions.

    [welcome] -> Houses the landing page greetings text, subtitle notes, and modification dates.

    [[nets]] -> List array containing your weekly Shrimp NET and AUXCOM parameters. To add an entire new routine net, copy a group blocks section from [[nets]] to time and paste it directly underneath.

    [[repeaters]] -> Updates the core infrastructure logs panel in your sidebar column.

📅 2. Event Itinerary Almanac (data/calendar.toml)

Manages your deep annual club activity schedule, club contests, and VE testing sessions.

    Real Date Parameters (date = "YYYY-MM-DD"): This is a mandatory strict format parameter (e.g., "2026-06-27"). The homepage shortcode uses this to automate date-math tracking loops.

    Homepage Rolling 3-Month Window: The home screen automatically filters and hides any event further out than 90 days from today, keeping the landing column clear and compact.

    Homepage Completed Window: When an event passes, it automatically moves into a grey "Recent Completed Events" trailing panel listing for 3 loops before dropping off into history.

    The Master Calendar Subpage (/calendar/): Displayed by clicking the centerpiece router button block. This page bypasses all window limits and generates your complete year-by-year agenda grouped neatly under bold month chapters.

    Smart Link Routing Badge Engine:

        If you populate the zoom_url = "https://..." line, the card automatically converts its location block into a clickable green 💻 Join Zoom Video Meeting action button.

        If the location field contains strings like "On the Air" or "Remote", it seals into a stable gray information badge.

        If it is a physical asset name or address, it automatically maps the string into a high-contrast blue button link routing directly out to Google Maps GPS Navigation.

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

👥 5. Membership Database (data/members.toml)

Manages the complete active alphabetical membership roster directory table.

    To add an entry, copy a full [[member]] block and paste it at the bottom.

    Fields map automatically to columns on the public index directory block. Keep strings wrapped in quotation marks.

🏛️ 6. Leadership & Committees (data/roster.toml)

Controls elected Board positions and appointed task chairs independently from the raw membership roster.

    [[officers]] -> Manages the core Board of Directors.

    [[committees]] -> Manages event chairs, food teams, trustees, and specialized volunteer roles.

🏗️ Folder Hierarchy Topography
Plaintext

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

    Sanitize Arrays: Bullet points inside spec loops (specs = [ "Line 1", "Line 2" ]) must be fully comma-separated to keep the parser engine from throwing syntax exception errors.

Brunswick Shores Amateur Radio Club — Securing Reliable Communications for Southeastern North Carolina Since 2026.