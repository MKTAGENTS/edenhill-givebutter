<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Thanks & Giving Speakeasy · Givebutter Implementation Guide</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
:root {
  --gold: #C9A96E;
  --gold-light: #DFC28E;
  --ink: #0E0E0C;
  --ink-mid: #161614;
  --ink-soft: #1E1E1C;
  --rule: #2A2A26;
  --text: #E8E4DC;
  --muted: #8A8578;
  --dim: #4A4A44;
  --green: #7ABB8A;
  --green-bg: #1C2E22;
  --green-border: #3A6A4A;
  --red: #CC6666;
  --blue: #6A9ECC;
  --blue-bg: #1A2A3A;
  --blue-border: #3A6A9E;
  --warn: #E8A87C;
  --warn-bg: #2E2218;
  --warn-border: #8A6A4A;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body {
  background: var(--ink);
  color: var(--text);
  font-family: 'DM Sans', sans-serif;
  font-size: 15px;
  line-height: 1.7;
  -webkit-font-smoothing: antialiased;
}

/* ── HEADER ── */
.header {
  padding: 48px 40px 40px;
  border-bottom: 1px solid var(--rule);
  max-width: 1100px;
  margin: 0 auto;
}
.eyebrow {
  font-size: 9px;
  letter-spacing: 5px;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 12px;
}
.header h1 {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(32px, 5vw, 52px);
  font-weight: 300;
  line-height: 1.15;
  color: #F0EDE6;
  margin-bottom: 8px;
}
.header h1 em { font-style: italic; font-weight: 300; }
.header-sub {
  color: var(--muted);
  font-size: 14px;
  letter-spacing: 0.3px;
}
.header-meta {
  display: flex;
  gap: 24px;
  margin-top: 20px;
  flex-wrap: wrap;
}
.meta-tag {
  font-size: 11px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--gold);
  padding: 6px 14px;
  border: 1px solid var(--rule);
  border-radius: 2px;
}

/* ── LAYOUT ── */
.wrap {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 40px;
}

/* ── SECTION ── */
.section {
  padding: 48px 0;
  border-bottom: 1px solid var(--rule);
}
.section:last-child { border-bottom: none; }
.sec-num {
  font-size: 9px;
  letter-spacing: 5px;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 8px;
}
.sec-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(24px, 3.5vw, 36px);
  font-weight: 400;
  color: #F0EDE6;
  margin-bottom: 6px;
}
.sec-desc {
  color: var(--muted);
  font-size: 14px;
  margin-bottom: 28px;
  max-width: 640px;
}

/* ── STEP CARDS ── */
.step {
  background: var(--ink-mid);
  border: 1px solid var(--rule);
  border-radius: 3px;
  padding: 28px 32px;
  margin-bottom: 16px;
  position: relative;
}
.step-num {
  position: absolute;
  top: 28px;
  right: 32px;
  font-size: 11px;
  letter-spacing: 3px;
  color: var(--dim);
  font-weight: 600;
}
.step h3 {
  font-family: 'DM Sans', sans-serif;
  font-size: 16px;
  font-weight: 600;
  color: var(--text);
  margin-bottom: 10px;
}
.step p, .step ul {
  color: #B5B0A6;
  font-size: 14px;
  line-height: 1.7;
}
.step ul {
  padding-left: 20px;
  margin-top: 8px;
}
.step li { margin-bottom: 4px; }
.step li::marker { color: var(--gold); }

/* ── COPY BLOCKS ── */
.copy-block {
  background: var(--ink-soft);
  border: 1px solid var(--rule);
  border-left: 3px solid var(--gold);
  border-radius: 2px;
  padding: 20px 24px;
  margin: 16px 0;
  position: relative;
}
.copy-label {
  font-size: 9px;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: var(--gold);
  margin-bottom: 10px;
  display: block;
}
.copy-text {
  color: var(--text);
  font-size: 14px;
  line-height: 1.8;
  white-space: pre-wrap;
  font-family: 'DM Sans', sans-serif;
}
.copy-btn {
  position: absolute;
  top: 16px;
  right: 16px;
  background: var(--ink);
  border: 1px solid var(--rule);
  color: var(--muted);
  font-size: 10px;
  letter-spacing: 2px;
  text-transform: uppercase;
  padding: 5px 12px;
  cursor: pointer;
  border-radius: 2px;
  transition: all 0.2s;
  font-family: 'DM Sans', sans-serif;
}
.copy-btn:hover {
  border-color: var(--gold);
  color: var(--gold);
}
.copy-btn.copied {
  border-color: var(--green-border);
  color: var(--green);
}

/* ── INFO BOXES ── */
.info-box {
  border-radius: 3px;
  padding: 16px 20px;
  margin: 16px 0;
  font-size: 13px;
  line-height: 1.6;
}
.info-box.tip {
  background: var(--green-bg);
  border: 1px solid var(--green-border);
  color: var(--green);
}
.info-box.warn {
  background: var(--warn-bg);
  border: 1px solid var(--warn-border);
  color: var(--warn);
}
.info-box.note {
  background: var(--blue-bg);
  border: 1px solid var(--blue-border);
  color: var(--blue);
}
.info-box strong { color: inherit; }

/* ── TIER CARDS ── */
.tier-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 16px;
  margin-top: 16px;
}
.tier-card {
  background: var(--ink-mid);
  border: 1px solid var(--rule);
  border-radius: 3px;
  padding: 24px;
  position: relative;
}
.tier-card.featured {
  border-color: var(--gold);
}
.tier-card.featured::before {
  content: '★ TOP TIER';
  position: absolute;
  top: -1px;
  right: 16px;
  background: var(--gold);
  color: var(--ink);
  font-size: 8px;
  letter-spacing: 2px;
  padding: 3px 10px;
  border-radius: 0 0 3px 3px;
  font-weight: 700;
}
.tier-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 22px;
  color: #F0EDE6;
  margin-bottom: 2px;
}
.tier-price {
  font-size: 13px;
  color: var(--gold);
  letter-spacing: 1px;
  font-weight: 600;
  margin-bottom: 12px;
}
.tier-card ul {
  list-style: none;
  padding: 0;
}
.tier-card li {
  font-size: 13px;
  color: #B5B0A6;
  padding: 4px 0;
  padding-left: 16px;
  position: relative;
}
.tier-card li::before {
  content: '·';
  position: absolute;
  left: 0;
  color: var(--gold);
  font-weight: bold;
}

/* ── UNDERWRITING TABLE ── */
.uw-table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 16px;
}
.uw-table th {
  text-align: left;
  font-size: 9px;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--muted);
  padding: 10px 16px;
  border-bottom: 1px solid var(--rule);
}
.uw-table td {
  padding: 10px 16px;
  font-size: 14px;
  color: var(--text);
  border-bottom: 1px solid #1A1A18;
}
.uw-table td:last-child {
  color: var(--gold);
  font-weight: 600;
  text-align: right;
}
.uw-table tr:hover td { background: rgba(201,169,110,0.03); }

/* ── CHECKLIST ── */
.checklist {
  list-style: none;
  padding: 0;
  margin-top: 12px;
}
.checklist li {
  padding: 8px 0 8px 28px;
  position: relative;
  font-size: 14px;
  color: #B5B0A6;
  border-bottom: 1px solid #1A1A18;
}
.checklist li::before {
  content: '☐';
  position: absolute;
  left: 0;
  color: var(--muted);
  font-size: 16px;
}
.checklist li:last-child { border-bottom: none; }

/* ── TOC ── */
.toc {
  display: flex;
  flex-wrap: wrap;
  gap: 0;
  border-bottom: 1px solid var(--rule);
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 40px;
  position: sticky;
  top: 0;
  background: var(--ink);
  z-index: 100;
}
.toc a {
  font-size: 10px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--muted);
  text-decoration: none;
  padding: 14px 16px;
  transition: color 0.2s;
  white-space: nowrap;
}
.toc a:hover { color: var(--gold); }

/* ── PRINT ── */
@media print {
  body { background: #fff; color: #111; }
  .toc { display: none; }
  .copy-btn { display: none; }
  .step, .tier-card, .copy-block { border-color: #ddd; background: #fafafa; }
  .copy-text, .step p, .step li, .tier-card li { color: #333; }
}

/* ── RESPONSIVE ── */
@media (max-width: 700px) {
  .header, .wrap { padding-left: 20px; padding-right: 20px; }
  .toc { padding: 0 16px; overflow-x: auto; }
  .step { padding: 20px; }
  .step-num { display: none; }
  .tier-grid { grid-template-columns: 1fr; }
}
</style>
</head>
<body>

<!-- HEADER -->
<div class="header">
  <div class="eyebrow">EdenHill Communities · Givebutter Implementation Guide</div>
  <h1>Thanks &amp; Giving <em>Speakeasy</em></h1>
  <div class="header-sub">Copy-ready campaign setup for Givebutter · November 20, 2026 · McKenna Center</div>
  <div class="header-meta">
    <span class="meta-tag">Event Campaign</span>
    <span class="meta-tag">Tickets + Sponsorships</span>
    <span class="meta-tag">Casino Night + Auction</span>
  </div>
</div>

<!-- TOC -->
<nav class="toc">
  <a href="#setup">Setup</a>
  <a href="#details">Event Details</a>
  <a href="#story">Story Copy</a>
  <a href="#tickets">Tickets</a>
  <a href="#sponsorships">Sponsorships</a>
  <a href="#underwriting">Underwriting</a>
  <a href="#donations">Donations</a>
  <a href="#sharing">Sharing &amp; SEO</a>
  <a href="#emails">Emails</a>
  <a href="#launch">Launch Checklist</a>
</nav>

<!-- ═══════════════════════════════════════════ -->
<!-- SECTION 01: ACCOUNT & CAMPAIGN SETUP -->
<!-- ═══════════════════════════════════════════ -->
<div class="section" id="setup">
  <div class="wrap">
    <div class="sec-num">Section 01</div>
    <div class="sec-title">Account &amp; Campaign Setup</div>
    <div class="sec-desc">Create the Event campaign in Givebutter and connect payout information before building anything else.</div>

    <div class="step">
      <span class="step-num">01</span>
      <h3>Create the Event Campaign</h3>
      <p>From your Givebutter dashboard, click <strong>+ New Campaign</strong> → select <strong>Start an Event</strong>.</p>
      <ul>
        <li><strong>Campaign Title:</strong> Thanks & Giving Speakeasy 2026</li>
        <li><strong>Peer-to-Peer:</strong> Leave unchecked (not needed for this event)</li>
        <li>Click <strong>Create Campaign</strong></li>
      </ul>
    </div>

    <div class="step">
      <span class="step-num">02</span>
      <h3>Verify Payout Information</h3>
      <p>Go to <strong>Account Settings → Payouts</strong> and confirm EdenHill Communities' bank account is connected. You cannot publish or accept payments without valid payout info.</p>
      <div class="info-box tip"><strong>Tip:</strong> If this is EdenHill's first Givebutter campaign, you'll need the EIN, a bank account, and an authorized signer to complete setup.</div>
    </div>

    <div class="step">
      <span class="step-num">03</span>
      <h3>Fee Structure Decision</h3>
      <p>Under <strong>Settings → Tips or Fees</strong>, choose your model:</p>
      <ul>
        <li><strong>Option A — Optional Donor Tips (recommended):</strong> 0% platform fee. Donors are asked to leave an optional tip for Givebutter. EdenHill keeps 100% of funds raised. Standard 2.9% + 30¢ payment processing still applies.</li>
        <li><strong>Option B — Platform Fees:</strong> 3% platform fee if you don't want donors asked to tip. You can absorb or pass through to donors.</li>
      </ul>
      <div class="info-box note"><strong>Recommendation:</strong> For a gala-style event with high-dollar sponsorships, Option A (donor tips) is standard. Most donors decline the tip at checkout — Givebutter covers processing fees if they do.</div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════ -->
<!-- SECTION 02: EVENT DETAILS -->
<!-- ═══════════════════════════════════════════ -->
<div class="section" id="details">
  <div class="wrap">
    <div class="sec-num">Section 02</div>
    <div class="sec-title">Event Details Configuration</div>
    <div class="sec-desc">Navigate to the Event tab in your campaign settings. Fill in each field using the copy below.</div>

    <div class="step">
      <span class="step-num">01</span>
      <h3>Event Tab → Event Details</h3>
      <ul>
        <li><strong>Event type:</strong> In Person</li>
        <li><strong>Event name:</strong> Thanks & Giving Speakeasy</li>
        <li><strong>Start Date & Time:</strong> November 20, 2026 at 6:00 PM (CST)</li>
        <li><strong>End Date & Time:</strong> November 20, 2026 at 10:00 PM (CST)</li>
        <li><strong>Enable Event Reminders:</strong> ON (sends 24hr and 1hr reminders to ticketholders)</li>
        <li><strong>In-Person Location:</strong> McKenna Center (enter full street address)</li>
        <li><strong>Keep Location Details Private:</strong> OFF — guests need the address to attend</li>
      </ul>
    </div>

    <div class="step">
      <span class="step-num">02</span>
      <h3>Event Details Field — Copy Below</h3>
      <p>Paste this into the "Event details" text box. This appears on the campaign page and on ticket receipts.</p>

      <div class="copy-block">
        <span class="copy-label">Event Details Copy</span>
        <button class="copy-btn" onclick="copyText(this)">Copy</button>
        <div class="copy-text">Join EdenHill Communities for an unforgettable evening at the Thanks & Giving Speakeasy — a 1920s-inspired night of gratitude, generosity, and glamour.

WHAT TO EXPECT:
• Casino gaming tables (roulette, craps, blackjack)
• Open bar & gourmet dining
• Live entertainment
• Whodunit mystery experience
• Giving Wall & silent auction
• Commemorative gifts & Bootlegger's Survival Kits

ATTIRE: 1920s Speakeasy / Cocktail Attire encouraged — think flapper dresses, fedoras, suspenders, and jazz-age glamour.

PARKING: Complimentary parking available at McKenna Center.

All proceeds support EdenHill Communities and our mission to provide exceptional care and enriching life experiences for our residents.</div>
      </div>
    </div>

    <div class="step">
      <span class="step-num">03</span>
      <h3>Details Tab — Campaign Fields</h3>
      <ul>
        <li><strong>Campaign Title:</strong> Thanks & Giving Speakeasy 2026</li>
        <li><strong>Subtitle:</strong> A Night of Gratitude, Generosity & Glamour</li>
        <li><strong>Goal:</strong> Set your fundraising target (total from sponsorships + tickets + donations + underwriting)</li>
        <li><strong>Theme Color:</strong> Use the gold from the event branding: <code>#C9A96E</code></li>
        <li><strong>Cover Photo:</strong> Upload the branded event graphic (1200 x 630px recommended). Use Image 4 or 5 (the speakeasy logo with the 1920s photo background — duotone versions)</li>
      </ul>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════ -->
<!-- SECTION 03: STORY COPY -->
<!-- ═══════════════════════════════════════════ -->
<div class="section" id="story">
  <div class="wrap">
    <div class="sec-num">Section 03</div>
    <div class="sec-title">Campaign Story</div>
    <div class="sec-desc">This is the main narrative block on your campaign page. It appears below the cover photo and goal bar. Paste into Details → Story.</div>

    <div class="copy-block">
      <span class="copy-label">Campaign Story — Full Copy</span>
      <button class="copy-btn" onclick="copyText(this)">Copy</button>
      <div class="copy-text">Step through the secret door and into an evening you won't forget.

EdenHill Communities invites you to the Thanks & Giving Speakeasy — a roaring 1920s casino night where gratitude meets generosity, and every guest walks away a winner.

On November 20, 2026, the McKenna Center transforms into a jazz-age speakeasy complete with casino gaming tables, live entertainment, craft cocktails, and a Whodunit mystery experience that will keep you guessing all night.

WHY YOUR SUPPORT MATTERS

EdenHill Communities is dedicated to providing exceptional care and enriching life experiences for our residents. Proceeds from the Thanks & Giving Speakeasy directly fund programs, services, and care enhancements that make EdenHill a place our residents are proud to call home.

Every ticket purchased, every sponsorship secured, and every dollar raised at the tables goes directly toward strengthening our community.

HOW TO GET INVOLVED

🎟️ Purchase Tickets — Reserve your seat and join us for an incredible evening.
🤝 Become a Sponsor — Elevate your company's visibility while investing in our mission.
🎰 Underwrite an Experience — Put your name on one of the night's signature attractions.
💛 Make a Donation — Can't attend? Your generosity still makes a difference.

Whether you're rolling dice at the craps table, solving the mystery, or simply raising a glass to gratitude — you're making a real impact in the lives of our residents.

We'll see you at the speakeasy. Don't forget the password.</div>
    </div>

    <div class="info-box tip"><strong>Formatting tip:</strong> Givebutter's Story editor supports rich text. Use bold for the subheadings (WHY YOUR SUPPORT MATTERS, HOW TO GET INVOLVED) and keep the emoji for visual breaks. You can also embed images between sections.</div>
  </div>
</div>

<!-- ═══════════════════════════════════════════ -->
<!-- SECTION 04: TICKETS -->
<!-- ═══════════════════════════════════════════ -->
<div class="section" id="tickets">
  <div class="wrap">
    <div class="sec-num">Section 04</div>
    <div class="sec-title">Ticket Configuration</div>
    <div class="sec-desc">Navigate to Event → Tickets to create ticket types. Create each ticket below as a separate ticket type in Givebutter.</div>

    <div class="info-box warn"><strong>Important:</strong> Set ticket quantities based on venue capacity. If McKenna Center has a max cap, divide it across ticket types to prevent overselling. Remember: sponsorship packages include tickets — subtract those from general availability.</div>

    <div class="step">
      <span class="step-num">01</span>
      <h3>General Admission Ticket</h3>
      <ul>
        <li><strong>Ticket Name:</strong> General Admission</li>
        <li><strong>Price:</strong> [Set your per-person ticket price — typically $75–$150 for this type of gala]</li>
        <li><strong>Quantity Available:</strong> [Set based on capacity minus sponsored seats]</li>
        <li><strong>Description:</strong></li>
      </ul>
      <div class="copy-block">
        <span class="copy-label">General Admission Description</span>
        <button class="copy-btn" onclick="copyText(this)">Copy</button>
        <div class="copy-text">Your ticket to the speakeasy. Includes admission to the Thanks & Giving Speakeasy, open bar, gourmet dinner, casino gaming chips, live entertainment, and the Whodunit mystery experience. Cocktail or 1920s attire encouraged.</div>
      </div>
    </div>

    <div class="step">
      <span class="step-num">02</span>
      <h3>VIP Table Ticket (Optional — if selling individual VIP)</h3>
      <ul>
        <li><strong>Ticket Name:</strong> VIP Table for 8</li>
        <li><strong>Price:</strong> [Set your VIP table price]</li>
        <li><strong>Quantity Available:</strong> [Number of VIP tables available]</li>
        <li><strong>Description:</strong></li>
      </ul>
      <div class="copy-block">
        <span class="copy-label">VIP Table Description</span>
        <button class="copy-btn" onclick="copyText(this)">Copy</button>
        <div class="copy-text">Reserved seating for 8 guests with open bar and table service. Includes full event access, casino gaming chips for each guest, commemorative gift, and the complete speakeasy experience. Perfect for corporate groups and friends who want to celebrate together.</div>
      </div>
    </div>

    <div class="step">
      <span class="step-num">03</span>
      <h3>Custom Fields for All Tickets</h3>
      <p>Under <strong>Tools → Custom Fields</strong>, add the following questions to collect at checkout:</p>
      <ul>
        <li><strong>Dietary Restrictions</strong> (text field) — "Please list any dietary restrictions or allergies."</li>
        <li><strong>Table Seating Preference</strong> (text field) — "Would you like to be seated with anyone specific? List names if so."</li>
        <li><strong>1920s Name</strong> (text field, optional) — "Choose your speakeasy alias for the evening (optional — for fun!)."</li>
      </ul>
    </div>

    <div class="step">
      <span class="step-num">04</span>
      <h3>Promo Codes (Optional)</h3>
      <p>If EdenHill wants to offer complimentary or discounted tickets to board members, major donors, or staff:</p>
      <ul>
        <li>Navigate to <strong>Event → Promo Codes</strong></li>
        <li>Create codes like <code>BOARD2026</code> or <code>STAFF2026</code> with 100% discount</li>
        <li>Set quantity limits per code to control distribution</li>
      </ul>
      <div class="info-box note"><strong>Note:</strong> Promo codes apply to the entire purchase total. You cannot apply them to individual ticket types at this time.</div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════ -->
<!-- SECTION 05: SPONSORSHIPS -->
<!-- ═══════════════════════════════════════════ -->
<div class="section" id="sponsorships">
  <div class="wrap">
    <div class="sec-num">Section 05</div>
    <div class="sec-title">Sponsorship Packages</div>
    <div class="sec-desc">Create each sponsorship level as a separate ticket type with detailed descriptions. This is where the major revenue lives — make these descriptions compelling.</div>

    <div class="info-box warn"><strong>How to structure in Givebutter:</strong> Create each sponsorship as a <strong>Ticket</strong> under Event → Tickets. Set limited quantities (e.g., 1–3 per tier). Sponsorship "tickets" won't generate individual event tickets for each included guest — you'll manage guest lists separately. Alternatively, use the <strong>Suggested Donation Amounts</strong> under Tools → Donation Settings to present them as donation tiers instead of tickets. Choose whichever workflow fits your ops.</div>

    <div class="tier-grid">
      <!-- BEE'S KNEES -->
      <div class="tier-card featured">
        <div class="tier-name">The Bee's Knees</div>
        <div class="tier-price">$15,000</div>
        <ul>
          <li>Center-stage roped VIP lounge with dedicated server</li>
          <li>Triple casino chip vouchers for each guest</li>
          <li>10 event tickets with full experience inclusions</li>
          <li>Deluxe Bootlegger's Survival Kit for each guest</li>
          <li>Recognition during presentation</li>
          <li>Company logo prominently displayed on event photo banner</li>
          <li>Company name/logo on event website, ticket & social media pages</li>
          <li>Tagged social media highlight post</li>
          <li>Recognition in EdenHill Annual Impact Report</li>
          <li>First right of renewal for 2027</li>
        </ul>
      </div>

      <!-- CAT'S MEOW -->
      <div class="tier-card">
        <div class="tier-name">The Cat's Meow</div>
        <div class="tier-price">$10,000</div>
        <ul>
          <li>Priority reserved seating with table service access</li>
          <li>Triple casino chip vouchers for each guest</li>
          <li>8 event tickets with full experience inclusions</li>
          <li>Premium Bootlegger's Survival Kit</li>
          <li>Recognition during presentation</li>
          <li>Company logo displayed on event photo banner</li>
          <li>Company name/logo on event website, ticket & social media pages</li>
          <li>Tagged social media highlight post</li>
          <li>Recognition in EdenHill Annual Impact Report</li>
        </ul>
      </div>

      <!-- GUILDED CIRCLE -->
      <div class="tier-card">
        <div class="tier-name">The Guilded Circle</div>
        <div class="tier-price">$5,000</div>
        <ul>
          <li>Reserved preferred seating with table service</li>
          <li>Double casino chip vouchers for each guest</li>
          <li>8 event tickets with full experience inclusions</li>
          <li>Standard Bootlegger's Survival Kit</li>
          <li>Recognition during presentation</li>
          <li>Company logo displayed on event photo banner</li>
          <li>Company name/logo on event website, ticket & social media pages</li>
          <li>Recognition in EdenHill Annual Impact Report</li>
        </ul>
      </div>

      <!-- UPTOWN SET -->
      <div class="tier-card">
        <div class="tier-name">The Uptown Set</div>
        <div class="tier-price">$3,500</div>
        <ul>
          <li>Recognition in EdenHill Annual Impact Report</li>
          <li>Company name/logo on event ticket & Facebook</li>
          <li>Reserved seating for 8 with open bar</li>
          <li>Commemorative gift for each guest</li>
          <li>Casino chip vouchers for each guest</li>
        </ul>
      </div>

      <!-- VELVET RESERVE -->
      <div class="tier-card">
        <div class="tier-name">The Velvet Reserve</div>
        <div class="tier-price">$1,500</div>
        <ul>
          <li>Reserved seating for 8 with open bar</li>
          <li>Commemorative gift for each guest</li>
          <li>Casino chip voucher for each guest</li>
        </ul>
      </div>
    </div>

    <h3 style="margin-top:32px; font-family:'Cormorant Garamond',serif; font-size:22px; color:#F0EDE6; font-weight:400; margin-bottom:16px;">Sponsorship Ticket Descriptions — Copy-Ready</h3>

    <div class="copy-block">
      <span class="copy-label">The Bee's Knees — $15,000</span>
      <button class="copy-btn" onclick="copyText(this)">Copy</button>
      <div class="copy-text">The ultimate speakeasy experience. Your company takes center stage with a roped VIP lounge, dedicated server, and 10 tickets to the full Thanks & Giving experience. Triple casino chip vouchers, Deluxe Bootlegger's Survival Kits, prominent logo placement on the event photo banner, social media highlight post, and recognition during the evening's presentation and in EdenHill's Annual Impact Report. Includes first right of renewal for 2027.</div>
    </div>

    <div class="copy-block">
      <span class="copy-label">The Cat's Meow — $10,000</span>
      <button class="copy-btn" onclick="copyText(this)">Copy</button>
      <div class="copy-text">Priority reserved seating with table service for 8 guests, plus triple casino chip vouchers and Premium Bootlegger's Survival Kits. Your company logo on the event photo banner, website, ticket, and social media pages. Includes tagged social media highlight post, recognition during the evening's presentation, and a feature in EdenHill's Annual Impact Report.</div>
    </div>

    <div class="copy-block">
      <span class="copy-label">The Guilded Circle — $5,000</span>
      <button class="copy-btn" onclick="copyText(this)">Copy</button>
      <div class="copy-text">Reserved preferred seating with table service for 8 guests, double casino chip vouchers, and Standard Bootlegger's Survival Kits. Company logo on event photo banner, website, ticket, and social media pages. Recognition during the evening's presentation and in EdenHill's Annual Impact Report.</div>
    </div>

    <div class="copy-block">
      <span class="copy-label">The Uptown Set — $3,500</span>
      <button class="copy-btn" onclick="copyText(this)">Copy</button>
      <div class="copy-text">Reserved seating for 8 with open bar, commemorative gifts, and casino chip vouchers for every guest. Company name and logo featured on the event ticket and Facebook page, plus recognition in EdenHill's Annual Impact Report.</div>
    </div>

    <div class="copy-block">
      <span class="copy-label">The Velvet Reserve — $1,500</span>
      <button class="copy-btn" onclick="copyText(this)">Copy</button>
      <div class="copy-text">Reserved seating for 8 with open bar, a commemorative gift for each guest, and casino chip vouchers. A perfect way to gather your team for a great cause and an unforgettable evening.</div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════ -->
<!-- SECTION 06: UNDERWRITING -->
<!-- ═══════════════════════════════════════════ -->
<div class="section" id="underwriting">
  <div class="wrap">
    <div class="sec-num">Section 06</div>
    <div class="sec-title">Putting on the Ritz — Underwriting</div>
    <div class="sec-desc">These are individual experience sponsorships. Create each as a separate ticket type OR as suggested donation amounts, depending on how you want them displayed.</div>

    <table class="uw-table">
      <thead>
        <tr>
          <th>Underwriting Opportunity</th>
          <th style="text-align:right">Investment</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>Food Sponsor</td><td>$8,000</td></tr>
        <tr><td>Bar Sponsor</td><td>$8,000</td></tr>
        <tr><td>Roulette Table</td><td>$2,200</td></tr>
        <tr><td>Craps Table</td><td>$1,700</td></tr>
        <tr><td>Blackjack Table</td><td>$1,500</td></tr>
        <tr><td>Ballroom Sponsor</td><td>$1,250</td></tr>
        <tr><td>Bottle Toss Sponsor</td><td>$1,000</td></tr>
        <tr><td>Signature Cocktail Sponsor</td><td>$1,000</td></tr>
        <tr><td>Whodunit Experience Sponsor</td><td>$750</td></tr>
        <tr><td>Winners Sponsor</td><td>$500</td></tr>
        <tr><td>Giving Wall Sponsor</td><td>$250</td></tr>
        <tr><td>Flashbulb Sponsor (Photography)</td><td>$200</td></tr>
      </tbody>
    </table>

    <div class="copy-block" style="margin-top:24px;">
      <span class="copy-label">Underwriting Section Description — for Campaign Story or Ticket Group Header</span>
      <button class="copy-btn" onclick="copyText(this)">Copy</button>
      <div class="copy-text">PUTTING ON THE RITZ — Underwriting Opportunities

Want your name on the night's most memorable moments? Underwrite one of the speakeasy's signature experiences. From the casino tables to the signature cocktail, each underwriting opportunity puts your brand front and center while directly supporting EdenHill Communities. All underwriters receive recognition at their sponsored experience and in event materials.</div>
    </div>

    <div class="info-box tip"><strong>Setup tip:</strong> Create each underwriting item as a ticket with a quantity of 1 (exclusive sponsorship). Name them clearly — e.g., "Underwrite: Roulette Table — $2,200." Set each to the exact price. When someone purchases, it auto-closes as sold out.</div>
  </div>
</div>

<!-- ═══════════════════════════════════════════ -->
<!-- SECTION 07: DONATIONS -->
<!-- ═══════════════════════════════════════════ -->
<div class="section" id="donations">
  <div class="wrap">
    <div class="sec-num">Section 07</div>
    <div class="sec-title">Donation Settings</div>
    <div class="sec-desc">Configure Tools → Donation Settings to accept standalone donations from supporters who can't attend or want to give above their ticket/sponsorship.</div>

    <div class="step">
      <h3>Suggested Donation Amounts</h3>
      <p>Under <strong>Tools → Donation Settings → Suggested Amounts</strong>, set the following tiers:</p>
      <ul>
        <li><strong>$50</strong> — "Buy a round for the house"</li>
        <li><strong>$100</strong> — "Fund a Bootlegger's Survival Kit"</li>
        <li><strong>$250</strong> — "Sponsor a guest's full evening"</li>
        <li><strong>$500</strong> — "Support resident programming"</li>
        <li><strong>Other</strong> — Allow custom amount (keep enabled)</li>
      </ul>
      <p style="margin-top:12px;">Set <strong>Frequency</strong> to One-time only (disable recurring — this is event-specific fundraising).</p>
    </div>

    <div class="step">
      <h3>Fund Designation (Optional)</h3>
      <p>If EdenHill wants to track where donations go, create Funds under <strong>Tools → Fund Settings</strong>:</p>
      <ul>
        <li>General Fund</li>
        <li>Resident Programs</li>
        <li>Capital Improvements</li>
      </ul>
      <p>Toggle <strong>Display fund selection</strong> ON if you want donors to choose. Otherwise, set a default fund and hide the selector.</p>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════ -->
<!-- SECTION 08: SHARING & SEO -->
<!-- ═══════════════════════════════════════════ -->
<div class="section" id="sharing">
  <div class="wrap">
    <div class="sec-num">Section 08</div>
    <div class="sec-title">Sharing &amp; SEO Settings</div>
    <div class="sec-desc">Navigate to the Sharing tab. These settings control how your campaign appears when shared on social media and in search results.</div>

    <div class="step">
      <h3>Campaign Link</h3>
      <p>Set your custom URL to something clean and memorable:</p>
      <div class="copy-block">
        <span class="copy-label">Recommended Campaign URL</span>
        <button class="copy-btn" onclick="copyText(this)">Copy</button>
        <div class="copy-text">givebutter.com/ThanksAndGivingSpeakeasy</div>
      </div>
      <p style="margin-top:8px;">Alternative options: <code>givebutter.com/EdenHillSpeakeasy</code> or <code>givebutter.com/EdenHill2026</code></p>
    </div>

    <div class="step">
      <h3>SEO Settings</h3>
      <div class="copy-block">
        <span class="copy-label">SEO Title</span>
        <button class="copy-btn" onclick="copyText(this)">Copy</button>
        <div class="copy-text">Thanks & Giving Speakeasy 2026 | EdenHill Communities</div>
      </div>
      <div class="copy-block">
        <span class="copy-label">SEO Description</span>
        <button class="copy-btn" onclick="copyText(this)">Copy</button>
        <div class="copy-text">Join EdenHill Communities on November 20, 2026 for the Thanks & Giving Speakeasy — a 1920s casino night featuring gaming tables, live entertainment, gourmet dining, and a Whodunit mystery experience. Purchase tickets, become a sponsor, or make a donation to support our residents.</div>
      </div>
      <ul style="margin-top:12px;">
        <li><strong>SEO Image:</strong> Upload the event graphic (the branded logo with duotone photo background — 1200 x 630px)</li>
      </ul>
    </div>

    <div class="step">
      <h3>QR Code</h3>
      <p>Download the <strong>Scan-to-Donate QR code</strong> from the Sharing tab. Use this on:</p>
      <ul>
        <li>Printed sponsorship packets</li>
        <li>Table displays at the event</li>
        <li>Email signatures leading up to the event</li>
        <li>Posters and flyers</li>
      </ul>
    </div>

    <div class="step">
      <h3>Widget Embed (for EdenHill's website)</h3>
      <p>Under <strong>Sharing → Widgets</strong>, create an embeddable widget to install on EdenHill's website. This lets visitors purchase tickets and donate directly from your site without being redirected to Givebutter.</p>
      <div class="info-box note"><strong>Note:</strong> The widget supports ticket sales and donations. The goal bar and story section won't appear in the embedded widget — only on the full Givebutter campaign page.</div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════ -->
<!-- SECTION 09: THANK YOU & EMAILS -->
<!-- ═══════════════════════════════════════════ -->
<div class="section" id="emails">
  <div class="wrap">
    <div class="sec-num">Section 09</div>
    <div class="sec-title">Thank You Message &amp; Email Communications</div>
    <div class="sec-desc">Configure the automatic receipt message and plan your email outreach.</div>

    <div class="step">
      <h3>Custom Thank You Message</h3>
      <p>Under <strong>Settings → Thank You Message</strong>, paste this custom message. It will appear in all receipt emails from this campaign.</p>
      <div class="copy-block">
        <span class="copy-label">Thank You Message — Receipt Email</span>
        <button class="copy-btn" onclick="copyText(this)">Copy</button>
        <div class="copy-text">Thank you for your generous support of the Thanks & Giving Speakeasy!

Your contribution directly impacts the residents of EdenHill Communities — funding programs, services, and care enhancements that enrich lives every day.

We can't wait to welcome you to the speakeasy on November 20th. Keep an eye on your inbox for event details, dress code inspiration, and your official speakeasy password.

Questions? Contact us at [INSERT EMAIL] or [INSERT PHONE].

With gratitude,
The EdenHill Communities Team</div>
      </div>
    </div>

    <div class="step">
      <h3>Post-Purchase Confirmation Email (for non-attending donors)</h3>
      <p>If you're using Givebutter's email tools, create a follow-up for donation-only supporters:</p>
      <div class="copy-block">
        <span class="copy-label">Donation-Only Thank You</span>
        <button class="copy-btn" onclick="copyText(this)">Copy</button>
        <div class="copy-text">Thank you for your generous donation to EdenHill Communities!

Even though you can't join us at the speakeasy this year, your support makes the evening — and our mission — possible. We'll share photos and highlights from the event so you can see your impact in action.

Your gift is tax-deductible to the extent allowed by law. A formal acknowledgment letter will follow.

Warmly,
The EdenHill Communities Team</div>
      </div>
    </div>

    <div class="step">
      <h3>Suggested Email Campaign Timeline</h3>
      <p>Use Givebutter's built-in email tools (or your existing email platform) for these touchpoints:</p>
      <ul>
        <li><strong>8 weeks out (late September):</strong> Save the Date announcement + sponsorship push</li>
        <li><strong>6 weeks out (mid-October):</strong> Tickets on sale + early bird messaging</li>
        <li><strong>4 weeks out (late October):</strong> Sponsorship deadline reminder + underwriting availability</li>
        <li><strong>2 weeks out (early November):</strong> Final ticket push + "tables filling up" urgency</li>
        <li><strong>1 week out:</strong> Event details reminder + dress code inspiration + parking info</li>
        <li><strong>Day before:</strong> "See you tomorrow" excitement builder (Givebutter auto-sends reminders if enabled)</li>
        <li><strong>Day after:</strong> Thank you + impact teaser + photos</li>
        <li><strong>1 week after:</strong> Full impact report + donor acknowledgment</li>
      </ul>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════ -->
<!-- SECTION 10: LAUNCH CHECKLIST -->
<!-- ═══════════════════════════════════════════ -->
<div class="section" id="launch">
  <div class="wrap">
    <div class="sec-num">Section 10</div>
    <div class="sec-title">Pre-Launch Checklist</div>
    <div class="sec-desc">Run through every item before clicking Publish. Once published and accepting payments, you cannot un-publish.</div>

    <div class="step">
      <h3>Account &amp; Configuration</h3>
      <ul class="checklist">
        <li>Payout information connected and verified</li>
        <li>Fee structure selected (tips vs. platform fee)</li>
        <li>Campaign type set to Event</li>
        <li>Time zone set to CST</li>
      </ul>
    </div>

    <div class="step">
      <h3>Event Details</h3>
      <ul class="checklist">
        <li>Event type: In Person</li>
        <li>Event name, date, start/end time entered</li>
        <li>Event details copy pasted in</li>
        <li>Location entered (McKenna Center full address)</li>
        <li>Event reminders enabled</li>
      </ul>
    </div>

    <div class="step">
      <h3>Campaign Page</h3>
      <ul class="checklist">
        <li>Title and subtitle set</li>
        <li>Fundraising goal entered</li>
        <li>Theme color set (#C9A96E)</li>
        <li>Cover photo uploaded (1200 x 630px)</li>
        <li>Story copy pasted and formatted</li>
      </ul>
    </div>

    <div class="step">
      <h3>Tickets &amp; Sponsorships</h3>
      <ul class="checklist">
        <li>General admission ticket created with price and quantity</li>
        <li>VIP table ticket created (if applicable)</li>
        <li>All 5 sponsorship tiers created with descriptions</li>
        <li>All 12 underwriting opportunities created (qty: 1 each)</li>
        <li>Promo codes created for board/staff (if needed)</li>
        <li>Custom fields added (dietary, seating preference)</li>
      </ul>
    </div>

    <div class="step">
      <h3>Donations &amp; Tools</h3>
      <ul class="checklist">
        <li>Suggested donation amounts configured ($50 / $100 / $250 / $500 / Other)</li>
        <li>Donation frequency set to one-time only</li>
        <li>Funds created and assigned (if applicable)</li>
        <li>Phone number requirement set (recommended: ON)</li>
      </ul>
    </div>

    <div class="step">
      <h3>Sharing &amp; SEO</h3>
      <ul class="checklist">
        <li>Custom campaign URL set</li>
        <li>SEO title and description entered</li>
        <li>SEO image uploaded</li>
        <li>QR code downloaded for print materials</li>
        <li>Widget created for EdenHill website embed</li>
      </ul>
    </div>

    <div class="step">
      <h3>Communications</h3>
      <ul class="checklist">
        <li>Thank you message customized</li>
        <li>Email campaign timeline planned</li>
        <li>Save the Date email drafted</li>
        <li>Social media launch posts prepared</li>
      </ul>
    </div>

    <div class="step">
      <h3>Final Review</h3>
      <ul class="checklist">
        <li>Preview campaign page — check all copy, images, pricing</li>
        <li>Test purchase with a promo code (100% off) to verify checkout flow</li>
        <li>Verify receipt email contains correct thank you message</li>
        <li>Confirm event reminder emails will fire (24hr and 1hr before)</li>
        <li>Share preview link with EdenHill team for approval</li>
        <li>Click PUBLISH</li>
      </ul>
    </div>

    <div class="info-box tip" style="margin-top:24px;"><strong>Day-of tip:</strong> Use Givebutter's mobile app to scan tickets at the door. Download it before the event and test with a sample ticket. You can also check in guests manually from the Attendees tab on desktop.</div>
  </div>
</div>

<!-- FOOTER -->
<div style="max-width:1100px;margin:0 auto;padding:40px;border-top:1px solid var(--rule);text-align:center;">
  <div style="font-size:9px;letter-spacing:5px;text-transform:uppercase;color:var(--dim);">EdenHill Communities · Thanks &amp; Giving Speakeasy · Givebutter Implementation Guide</div>
  <div style="font-size:12px;color:var(--muted);margin-top:8px;">Prepared by MKT Agents · 2026</div>
</div>

<script>
function copyText(btn) {
  const block = btn.closest('.copy-block');
  const text = block.querySelector('.copy-text').innerText;
  navigator.clipboard.writeText(text).then(() => {
    btn.textContent = 'Copied';
    btn.classList.add('copied');
    setTimeout(() => {
      btn.textContent = 'Copy';
      btn.classList.remove('copied');
    }, 2000);
  });
}
</script>
</body>
</html>
