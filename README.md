<p align="center">
  <img src="static/images/club_logo.webp" alt="BSARC Logo" width="200">
</p>


## 📻 Brunswick Shores Amateur Radio Club (BSARC) - Web Platform Manual

Welcome to the official station log and technical operating manual for the **BSARC Website Source Framework** (`n4gm.org`). This platform utilizes the **Hugo Static Site Generator** hosted entirely via **GitHub Pages** for ultra-fast, modern, database-free web operations.

---

### 1. 🏗️ Web Framework Directory Topography

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
To guarantee seamless succession transitions for upcoming club officers and volunteers, the layout templates have been decoupled entirely from raw content. You do not need to understand HTML grid spacing, tables, or CSS layout code to update the website. Simply modify the structured text configuration parameters inside the files within the `data/` folder:

### 🏠 2. Homepage Registry (`data/homepage.toml`)

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

### 📅 3. Event Itinerary Almanac (`data/calendar.toml`)

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

### 📻 4. Equipment Rooms & Marketplace Hub

This module manages the physical holdings, member trade listings, and club asset liquidations. It ties two separate database logs together under a unified interface: member gear updates in data/forsale.toml and official club holdings in data/equipment.toml.
## 💰 PART A: Member Swapfest Marketplace (`data/forsale.toml`)

Manages personal buy/sell/trade listings for regional hams. The template dynamically parses your text rules to morph the layout of individual equipment cards.
#### 💡 Strict Formatting Rules:

   * String Wrapped Values: All descriptive text, names, callsigns, prices, and notes MUST be wrapped in double quotation marks (`"text"`).

   * Booleans stay Lowercase: Toggles must be written strictly in lowercase without quotation marks (`true` or `false`).

   * Sanitize specification Arrays (`specs = [...]`): Feature bullet points must be grouped inside bracket arrays, and every line string must be separated by a comma. Leaving off a trailing comma will immediately crash the Hugo build engine during a deployment run.

## 📝 How to Update a Member Item Status:

   * 💰 Standard Cash Price Item: Set `sold = false` and `free = false`. Input the target dollar value inside the path: `price = "$500"`.

   * 🎁 Free / Gift Item: Set `sold = false` and `free = true`. Clear out the price line to empty quotes (`price = ""`). The site will automatically overlay a purple banner reading 🎁 FREE.

   * ❌ Closed / Sold Item: Set `sold = true` and `free = false`. Leave the original price string intact as an historical reference. The layout engine automatically fades out the item card, slashes a strike-through line across titles, appends a red ❌ SOLD badge, and strips out the contact hyperlink to protect members from post-sale spam.

## 📋 PART B: Master Club Asset & Inventory Room (`data/equipment.toml`)

Manages the physical equipment vault, active member loan pools, permanent repeater deployments, and club liquidations using an interactive, searchable DataTables grid on the website.

#### 🚀 Zero-Code Excel Manager Workflow:
To protect the website layout from formatting or text quotation errors, **editors do not need to alter the TOML data file using text editors**. 

1. Pull the latest repository updates down to your workbench local terminal using `git pull origin main`.
2. Open the master repository inventory utility spreadsheet located inside the project tree at: `/.admin/equipment_vault.xlsm`.
3. Update rows, structural tracking parameters, location metrics, status types, or operational event notes inside the standard table rows.
4. Click the prominent custom physical macro action button: `🚀 Generate Web Inventory File`.
5. Bypassing volatile clipboard syntax traps, the system automatically sanitizes strings, reformats background calendar serial tokens, and prompts you to export a perfect file named exactly `equipment.toml`.
6. Save your modified Excel spreadsheet tracker cell values directly inside the `/.admin/` directory.
7. Stage and commit both files simultaneously using your workspace terminal console so that the background tracker and live site stay in perfect lockstep:
   ```bash
   git add .admin/equipment_vault.xlsm data/equipment.toml
   git commit -m "chore(inventory): synchronize master excel metrics sheet and compile production toml data structures"
   git push origin main

## 📝 Standardized Asset Status & Button Actions Reference Guide:

The interactive web database monitors the `status` string value of each asset block to dynamically establish reservation blocks and context-aware member communication shortcuts:

   * `status = "Available"` -> The asset is ready for deployment inside the locker closet. Generates an automated blue [Borrow 🏷️] button. Clicking this triggers a member's local email engine to compose a pre-formatted loan request directly to the active Equipment Manager.

   * `status = "Reserved"` -> Locked for a member booking or specific upcoming event. Requires a companion calendar field value format line: reserved_date = "MM/DD/YY". The layout engine blocks public checkouts, swaps active link buttons for a locked [Hold Active 🔒] label, and appends a text warning badge to the grid: 🗓️ Reserved until MM/DD/YY.

   * `status = "Official Use Only"` -> The gear is permanently reserved for Field Day, emergency communication deployments, or specific club ops. Blocks borrowing actions and lists a clean grey [Club Events 🎪] identifier note.

   * `status = "For Sale"` -> Cleared by the board as club surplus gear for liquidation. Requires a target valuation pricing field block line: price = "$X". The database layer immediately handles two automated actions:

       1. It generates an orange [Purchase 💰] action route linking directly to the surplus checkout desk.

       2. It mirrors the asset card layout automatically to the top section of the public marketplace page under an authoritative header callout: 🏢 Club Surplus Equipment.

   * `status = "Checked Out"` -> Gear is currently out on loan to a member. Blocks borrow text buttons.

   * `status = "In Use"` -> Asset is actively deployed at a remote repeater facility or digital gateway node.

   * `status = "Donated"` -> Asset has been successfully sold off, gifted, or permanently decommissioned.

### 🚨 5. Tactical Emergency Notices & Incident Logs (`data/notice.toml`)

Allows appointed Emergency Coordinators (ECs), Net Control Stations (NCS), or Public Information Officers (PIOs) to issue real-time broadcast alert advisories directly across the site framework without modifying template layouts or single page source codes. 

#### 💡 Strict Formatting Rules:
* **String Wrapped Values:** All text descriptions, timestamps, headings, messages, and color options MUST be nested inside double quotation marks (`"text"`).
* **Booleans stay Lowercase:** Binary true/false logic flags must be written in lowercase without quotes (`true` or `false`).

#### 🛠️ Homepage Broadcast Configuration Keys:
The front-end dashboard evaluates these global keys right at the top of the main layout row to intercept user focus during critical situations:

* `active = true/false` -> Setting to `true` instantly draws a thick, high-contrast visual callout banner right at the top of the homepage content column. Set to `false` to cleanly strip the alert box off the screen when stand-down orders are issued.
* `color = "text"` -> Swaps the visual CSS stylesheet profile immediately to map incident severity. Options include:
  * `"danger"` -> **Crimson Red Block:** Used for active Skywarn activations, severe weather warnings, safety operational flags, or immediate meeting cancellations.
  * `"warning"` -> **Amber Yellow Block:** Used for active localized radio training advisories, upcoming dues deadlines, or general routine testing reminders.
  * `"info"` -> **Ocean Blue Block:** Used for special event news, public hamfest caravans, or casual club announcements.
* `heading = "text"` & `message = "text"` -> Controls the primary bold alert title line and the summarizing message paragraph text on the landing screen.
* `link_button_active = true/false` -> Setting to `true` draws an interactive navigation button right inside the alert banner container block.
* `link_button_text = "text"` -> Customizes the button's action text (e.g., `"🔗 View Live Incident Log"`), which deep-links users straight into the dedicated `/notice/` subpage route.

#### 📝 Real-Time Incident Timeline Log (`[[updates]]`):
When a tactical incident unfolds or Skywarn operators are tracking an event, the dedicated **`/notice/`** page builds a reverse-chronological, step-by-step rolling timeline wire using these list arrays.

* ** Roster Matrix Keys:** Every log entry block requires `timestamp` (e.g., `"May 20, 2026 - 11:30 AM"`) and `log_text` (e.g., `"Primary net operations shifted to backup..."`).
* **Maintenance & Deployment Policy:** To add a status update during an event, copy a complete block from `[[updates]]` through its `log_text` line, paste it at the bottom of the document sheet, and fill in the fields. The shortcode engine loops through the arrays to compile an organized emergency log wire automatically.

### 🗞️ 6. Automated Weekly Bulletins Pipeline (`/content/bulletins/`)

Manages the digital broadcasting and long-term storage of the club's weekly informational updates. By using a multi-file automated architecture, the Secretary avoids editing dense page layouts or manual index tables when updating weekly nets, training news, swap items, or roster updates.

#### 📝 Front Matter Syntax & File Initialization:
To dispatch a brand-new weekly bulletin update, create an individual Markdown file directly inside `content/bulletins/` named with standard system date syntax (e.g., `bulletin-2026-05-18.md`). 

Every bulletin file MUST begin with this exact metadata configuration block at the absolute top:
```markdown
---
title: "Weekly Bulletin: New HF SSB Net, ARES Rotations & Welcome Julia KR4LQQ"
date: 2026-05-18
draft: false
---
```

   * Metadata Fields: `title` sets the bold index heading, `date` runs the automated chronological sorting timeline math, and setting `draft = false` unlocks the asset for the live compilation engine.

📋 Component Layout Blocks Structure:

To maintain typographic and layout consistency across the archive repository, utilize standard Markdown formatting elements to represent incoming email data fields:

   * 📡 Local Net Tables: Rendered via standard Markdown table alignment delimiters to chart ARES Net Control Station (NCS) schedules, frequencies, and repeater parameters clearly.

   * 🛍️ Swapfest & Marketplace Logs: Houses unique member trade rows (such as station estate liquidations or antenna switches), linking contact information directly to emails or phone numbers.

   * 👋 New Member Welcomes: Structured inside high-contrast metadata rows highlighting new calls, roster assignments, and licensing classes (e.g., Technician, General, Amateur Extra).

   * 🔗 Reference Anchor Links: Standard link formatting blocks routing visitors directly out to the club's Groups.io reflector email loop, Facebook community portal, NWS Skywarn training entry matrices, and fillable ARRL commission applications.

🏗️ Dual-Column Automated Sorting Pipeline Logic:

The Hugo site compiler reads the front matter variables of the bulletins queue directory on the fly to completely automate web distribution pathways without manual administrative intervention:

   1. The Homepage Spotlight Desk Module: The system loops through the `content/bulletins/` folder, isolates the file containing the newest chronological date parameter, automatically grabs its headline title and top text snippet (`{{ .Summary }}`), and displays it right inside the homepage sidebar 🗞️ Secretary's Desk dashboard block automatically.

   2. The Historical Vault Archive (`content/bulletin-archive.md`): The centerpiece archive hub page calls your custom presentation snippet shortcode `{{< bulletin_vault >}}`. This shortcode runs a backend template loop sorting through all older dispatches, grouping them cleanly by month/year, and stamping them with high-visibility 📅 Week of [Date] chronological indicator badges to form a zero-maintenance, searchable index loop.


### 👥 7. Membership Database (`data/members.toml`)

Manages the complete active alphabetical membership roster directory table displayed on the public interface. 

#### 💡 Strict Formatting Rules:
* **String Wrapped Values:** All personal names, callsigns, and structural positions MUST be nested inside double quotation marks (`"text"`).
* **Roster Category Positions:** Standard classification assignments for the `position` field include: `"Member"`, `"Member Family"`, `"Associate"`, `"President"`, `"Vice President"`, `"Secretary"`, or `"Treasurer"`.

#### 🗄️ Automated MS Access Database Sync Pipeline:
Instead of manually typing individual text structures when the Secretary updates the master logs, your administrators can utilize an automated query output pipeline inside Microsoft Access:

1. Open your master **BSARC Membership MS Access Database**.
2. Click the **Create** tab on the top ribbon banner and select **Query Design**.
3. Close the "Add Tables" pop-up, right-click the empty workspace canvas window, and choose **SQL View**.
4. Paste this exact SQL conversion script into the editor pane (*Assuming your primary database table is named `Roster` and uses fields `LastName`, `FirstName`, `CallSign`, and `Class`*):

```sql
SELECT '[[member]]' & Chr(13) & Chr(10) & 
       'name = "' & [LastName] & ', ' & [FirstName] & '"' & Chr(13) & Chr(10) & 
       'call = "' & [CallSign] & '"' & Chr(13) & Chr(10) & 
       'position = "' & [Class] & '"' AS TomlOutput
FROM Roster
ORDER BY LastName, FirstName;
```
5. Click Run (the red exclamation mark ❗️ symbol on the top ribbon).

6. Access will generate a single column titled `TomlOutput`. Click the column header to select all entries, hit `Ctrl` + `C` to copy, open up `data/members.toml` in VS Code, clear out any old rows, and hit `Ctrl` + `V` to paste the complete structured file perfectly!

📦 Manual Individual Entry Addition (Alternative):

If adding a quick single entry off-cycle, copy a single block segment and drop it at the absolute bottom of the database list:

```ini,toml
[[member]]
name = "Applegate, Ted"
call = "KB4ERV"
position = "Member"
```

### 🏛️ 8. Leadership & Committees (`data/roster.toml`)

Controls elected corporate Board positions and appointed task committee chairs independently from the raw membership database. This file feeds data directly into the public `content/board.md` page template view.

#### 💡 Strict Formatting Rules:
* **String Wrapped Values:** Every organizational title, volunteer name, and alphanumeric callsign assignment MUST be enclosed in double quotation marks (`"text"`).
* **Positional Term Limits & Reassignments:** To adjust an executive board assignment or reassign a volunteer committee chair when elections wrap up, **simply rewrite the text string inside the quotation marks**. No layout structures or shortcode loops need to be edited.
* **Lowercase Call Signs Integration:** The site template formatting scripts automatically run callsign text strings through an internal capitalizing filter—meaning you can type callsigns in lowercase or uppercase here and they will always display cleanly in bold uppercase blocks on the public web page.

#### 📦 Individual Table Array Sections Reference:
This data sheet utilizes two separate **Arrays of Tables** (double bracket headers) to loop through roles and dynamically build clean, visually balanced rosters with soft drop-shadow alignments:

* **🎖️ Section 1: Elected Club Officers (`[[officers]]`):** Manages the core executive Board of Directors.
  * *Keys required per block:* `role`, `name`, and `callsign`.
  * *Roster Management:* Array fields explicitly track core positions required by bylaws (e.g., `role = "President"`, `role = "Treasurer"`, etc.). Keep the sequence organized chronologically or by rank hierarchy layout.
* **🏛️ Section 2: Appointed Committees & Task Volunteers (`[[committees]]`):** Tracks ongoing operational chairs, equipment managers, and multi-member volunteer groups (such as your field deployment kitchen teams).
  * *Keys required per block:* `role`, `name`, and `callsign`.
  * *Multi-Member Support:* To assign multiple operators to a unified group operation (e.g., listing four different members under `role = "Field Day Food Team"`), simply create four individual `[[committees]]` block containers using identical text values for the `role` line. The layout shortcode engine will group them perfectly on the output layout block dynamically.

#### 🛠️ Manual Data Entry Block Addition:
To provision a brand-new volunteer team chair or log an additional task role during active seasons, copy a block module section and paste it right at the absolute bottom of your file layout tree:
```toml
[[committees]]
role = "Emergency Operations Coordinator"
name = "Mark Sergent"
callsign = "KA4EVR"
```

### 📸 9. Activities & Media Gallery Pipeline (`content/gallery.md`)

Manages the visual documentation vault of club deployments, activations, and holiday parties. The framework utilizes a **Zero-Maintenance Asset Shortcode**—meaning admins never have to write HTML image links or style grids manually when uploading photo albums.

#### 📁 Step 1: Uploading Images via the Filesystem
When club members submit photographs from a recent operation, the administrator must stage the raw image assets directly inside the static media vault structure:

1. Navigate on your file manager workbench to your local project directory at:
   `static/media/`
2. Create a new subfolder organized strictly by the **Year** (if it doesn't already exist), and then a folder for the specific **Event** using clean, hyphenated names:
   * ❌ *Bad name:* `static/media/2026/Field Day Photos/` (Spaces break web links)
   * 🟢 *Good name:* `static/media/2026/field-day-2026/`
3. Convert your raw submitted camera photos to a web-optimized image format (like `.jpg` or `.webp`) and paste them straight into that directory folder. 

#### 📄 Step 2: Provisioning an Accordion Folder in `gallery.md`
Once your photographs are staged inside the filesystem directory, open up **`content/gallery.md`** in VS Code to append a matching collapsible HTML accordion drawer module box.

Find the appropriate year chapter header line block, or create a new one (e.g., `## 📅 2026 Events`), and copy/paste this exact layout snippet block right below it:

```html
<details style="margin-bottom: 15px; border: 1px solid #e0e0e0; border-radius: 8px; background: #ffffff; box-shadow: 0 2px 4px rgba(0,0,0,0.02);">
  <summary style="font-size: 16px; font-weight: bold; padding: 12px 16px; cursor: pointer; outline: none; color: #1976d2; display: flex; align-items: center; gap: 8px; user-select: none;">
    ⛺ ARRL Field Day (Calabash Park)
  </summary>
  <div style="padding: 0 16px 16px 16px; border-top: 1px solid #eeeeee; background: #fafafa;">
    {{< gallery_grid year="2026" event="field-day-2026" >}}
  </div>
</details>
```

🛠️ Explaining the Shortcode Variables

The backend shortcode logic maps parameters to your filesystem structure on the fly:

   * `year="2026"` -> Instructs the system to dive into the `static/media/2026/` directory.

   * `event="field-day-2026"` -> Instructs the system to target the exact subfolder.

The custom `{{< gallery_grid >}}` engine script will automatically scan the specified folder layout, count how many photos are inside, compile a responsive, beautifully padded fluid grid gallery row set, and wrap each picture in an advanced click-to-expand hyperlink popout module wrapper instantly!

### 🌐 10. Web Directory Resources Manual (`content/links.md`)

Manages the comprehensive "Useful Radio Links" directory subpage. This page serves as a centralized jumping-off point for club members to quickly find technical tools, federal licensing portals, emergency training platforms, and surrounding regional ham clubs.

#### 💡 Content Structure & Layout Rules:
* **Float Right Graphic Asset:** The top margin features a floating layout graphic (`/images/www_icon.png`). Just like the club logo on other pages, it uses a soft drop shadow filter and is configured to float cleanly on the right text margin. The primary introduction automatically wraps around it like a high-end column spread.
* **Category Segmentation:** Links are organized under themed, bold horizontal rules (`---`) and clean `###` header chapters (e.g., `### Technical Tools & Calculators`). This visual breakdown groups scattered web items into easily scannable sections.
* **Typographic Icon Accents:** To maintain visual harmony with the homepage dashboard, every hyperlink line begins with an expressive Windows 11 emoji icon shortcut (such as 🧮 for calculators, 📡 for federal agencies, and 🗼 for repeaters/clubs).

#### 🛠️ Adding or Editing Hyperlinks:
To modify an existing resource link or introduce a new amateur radio asset to the public list, open **`content/links.md`** and utilize standard Markdown hyperlink syntax:

```text
* 🧭 [Descriptive Anchor Text Label](https://www.target-website-url.com/) — Brief sentence explaining what this asset provides or how it supports the hobby.
```

* Always Verify Protocol Paths: Ensure all outside URLs are explicitly prefix-mapped using `http://` or `https://` inside the parentheses. Missing the protocol string will cause the web browser to treat the target as a broken internal page route instead of navigating to the external web server.

* Sorting Policy: When adding links under a specific category heading, maintain an alphabetical sorting pattern based on the text inside the bracket anchors. This helps members quickly browse the index vault without needing a search function.

---

## 📝 Operators Syntax Rules Checklist

To maintain 100% server uptime and prevent your remote GitHub Actions compilation pipeline from throwing syntax exception execution errors, every editor must run their changes through this quick checklist before executing a `git push`:

### 1. 🧵 Always Seal String Paths
Every text variable description field layout input value MUST be nested safely inside double quotation marks (`"Your Text Value Here"`). 
* ❌ *Bad syntax:* `name = Mark Sergent`
* 🟢 *Good syntax:* `name = "Mark Sergent"`

### 2. 🎛️ Booleans Stay Lowercase
Logistical true/false layout tracking status toggle switches must remain completely lowercase and free of quotation marks. Wrapping a boolean in quotes turns it into text string data, which completely breaks the automated shortcode logic loops.
* ❌ *Bad syntax:* `zoom_meeting = "true"` or `sold = True`
* 🟢 *Good syntax:* `zoom_meeting = true` or `sold = false`

### 3. 🧼 Sanitize Array Blocks (`[ ... ]`)
Bullet point technical lists inside specification loops (such as your marketplace `specs` lines) must be completely enclosed in square brackets, with **every individual line segment separated by a comma**. Leaving off a trailing comma will immediately crash the Hugo build engine.
* ❌ *Bad syntax:*
  ```toml
  specs = [
    "Line Item 1"
    "Line Item 2"
  ]
  ```
  🟢 Good syntax:
  ```Ini, TOML

   specs = [
     "Line Item 1",
     "Line Item 2"
  ]
  ```

### 🛠️ Fail-Safe Troubleshooting Field Guide

If your updates push up to the GitHub server but the live pages throw a **404 Not Found** error or elements break, check for these three common web-development deployment traps:
#### 🚨 1. The Project Sub-Directory (BaseURL) Asset Trap

When you test the site locally via your sandbox sandbox link, you are running at the root domain level (`http://localhost:1313/`). Hardcoded assets like an image path pointing to `/images/logo.png` or a document at `/pdf/application.pdf` render perfectly.

However, your production server hosts the platform as a Project Repository Sub-folder `(https://bsarc-n4gm.github.io/bsarc-site/)`. If you use a hardcoded forward slash (`/`) at the beginning of an asset link, the browser skips your repository folder and tries to find it on the absolute root domain, triggering a 404 error.

   * **The Permanent Fix:** Always pass your custom markdown links and layout file asset references through Hugo's native pipeline handlers or base layouts to let the build engine evaluate relative URLs automatically:

       * In layout files, append `| relURL`: `<img src="{{ "images/logo.png" | relURL }}">`

       * In markdown files, use clean relative syntax paths without the leading slash: `[Download Application](pdf/bsarc_membership_application.pdf)`

#### 🚨 2. The Strict Case-Sensitivity Enforcement

Windows and macOS file environments are case-insensitive, meaning they look at club_logo.webp, Club_Logo.WEBP, and Club_Logo.webp as the exact same file. Local test environments will render them all flawlessly.

GitHub Pages hosts your live platform on **Linux Servers, which are strictly case-sensitive.** If your filename on disk is `club_logo.webp` but your text configuration code inside `homepage.toml` targets `Club_Logo.webp`, the local sandbox server will show the image perfectly, but the live live production site will completely drop the asset and throw a broken graphic link.

   * The Permanent Fix: Always write data values matching the exact case of filenames resting on disk.

#### 🚨 3. Maintain Git Logs Discipline (Conventional Commits)

To ensure the historical timeline remains granular and easily auditable by incoming club technology directors, never use generic message lines like `git commit -m "update"`. Follow the industry-standard Conventional Commits imperative guidelines:

   * Syntax Structure: `type(scope): message as a command`

   * Real Project Production Examples:

       * `feat(calendar): automate past event archiving inside accordion toggle drawer`

       * `fix(bulletins): remove legacy routing folder path intersecting conflicts`

       * `style(sidebar): reposition full calendar itinerary launch card to bottom`

       * `docs(readme): expand membership toml instructions with access sql report query`

---

## Brunswick Shores Amateur Radio Club — Securing Reliable Communications for Southeastern North Carolina Since 2026.
