---
title: Navigate Code Testing Page
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Launch — Recurly Navigate</title>
<style>
html { scroll-behavior: smooth; scroll-padding-top: 80px; }

.rc-guide {
  --yellow: #FFD706;
  --orange: #FF8200;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}
.rc-guide * { box-sizing: border-box; }
body { margin: 0; background: #fff; }

/* ── ANNOUNCEMENT BAR ── */
.rc-announce-bar {
  background: var(--yellow);
  color: var(--offblack);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 10px 20px;
  font-size: .88rem;
  font-weight: 600;
  border-radius: 10px;
  margin-bottom: 16px;
  gap: 12px;
  line-height: 1.4;
}
.rc-announce-inner {
  display: flex;
  align-items: center;
  gap: 12px;
  flex: 1;
  flex-wrap: wrap;
}
.rc-announce-link {
  color: var(--offblack) !important;
  font-weight: 800;
  text-decoration: none !important;
  white-space: nowrap;
  padding: 4px 12px;
  background: rgba(0,0,0,0.10);
  border-radius: 6px;
  transition: background 0.2s;
}
.rc-announce-link:hover { background: rgba(0,0,0,0.20); text-decoration: none !important; }
.rc-announce-close {
  background: none;
  border: none;
  font-size: 1.4rem;
  line-height: 1;
  cursor: pointer;
  color: var(--offblack);
  padding: 0 2px;
  opacity: 0.45;
  transition: opacity 0.2s;
  flex-shrink: 0;
}
.rc-announce-close:hover { opacity: 1; }

/* ── TOP BACK LINK ── */
.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }

/* ── CONTENT WRAPPER ── */
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* ── PILLAR HERO ── */
.rc-hero {
  background: linear-gradient(rgba(13,13,11,0.8), rgba(13,13,11,0.8)),
              url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center;
  background-color: var(--offblack);
  background-size: cover;
  color: #fff;
  padding: 48px 40px 56px;
  text-align: center;
  border-radius: 16px;
  margin-bottom: 0;
}
.rc-brand-header { display: flex; align-items: center; justify-content: center; gap: 16px; margin-bottom: 30px; }
.rc-logo-image { height: 40px; width: auto; }
.rc-pillar-hero-icon { width: 72px; height: 72px; display: flex; align-items: center; justify-content: center; margin: 0 auto 24px; }
.rc-pillar-hero-icon img { width: 48px; height: 48px; object-fit: contain; }
.rc-hero h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; margin: 0 0 16px; color: var(--offwhite); }
.rc-hero > p { font-size: 1.1rem; opacity: .9; max-width: 700px; margin: 0 auto; color: var(--lightgray); line-height: 1.6; }

/* ── EXPANDING NAV ── */
.rc-sticky-nav-wrap {
  position: sticky;
  top: 0;
  z-index: 100;
  background-color: var(--lightgray);
  box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  margin: 24px 0 48px 0;
  border-radius: 12px;
  overflow: hidden;
}
.rc-nav-toggle {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 15px 24px;
  cursor: pointer;
  background: none;
  border: none;
  width: 100%;
  text-align: left;
}
.rc-nav-toggle-label {
  display: flex;
  align-items: center;
  gap: 8px;
  font-weight: 800;
  font-size: .88rem;
  letter-spacing: 0.6px;
  text-transform: uppercase;
  color: var(--offblack);
}
.rc-nav-toggle-label img { width: 15px; height: 15px; object-fit: contain; }
.rc-nav-hint {
  font-size: .78rem;
  font-weight: 600;
  color: var(--darkgray);
  text-transform: none;
  letter-spacing: 0;
  margin-left: 4px;
  opacity: 0.7;
}
.rc-nav-chevron {
  font-size: .72rem;
  color: var(--darkgray);
  transition: transform 0.25s ease;
  line-height: 1;
  opacity: 0.7;
}
.rc-nav-chevron.rc-open { transform: rotate(180deg); }

.rc-nav-drawer {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.35s ease;
}
.rc-nav-drawer.rc-open { max-height: 300px; }

/* Two-group layout inside the drawer */
.rc-nav-drawer-inner {
  border-top: 1px solid rgba(0,0,0,0.10);
  padding: 16px 20px 20px;
  display: flex;
  flex-direction: column;
  gap: 14px;
}
.rc-nav-group-label {
  font-size: .72rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.8px;
  color: var(--darkgray);
  opacity: 0.6;
  margin-bottom: 4px;
}
.rc-nav-links {
  display: flex;
  flex-wrap: wrap;
  gap: 5px 4px;
}
.rc-sticky-link {
  color: var(--offblack) !important;
  text-decoration: none !important;
  font-weight: 700;
  font-size: .83rem;
  letter-spacing: 0.4px;
  text-transform: uppercase;
  padding: 7px 14px;
  border-radius: 7px;
  transition: all .18s;
  white-space: nowrap;
}
.rc-sticky-link:hover {
  background: var(--offblack);
  color: var(--yellow) !important;
  text-decoration: none !important;
}
/* Anchor links (on this page) get a slightly different pill */
.rc-sticky-link-anchor {
  background: rgba(0,0,0,0.07);
}
.rc-sticky-link-anchor:hover {
  background: var(--offblack);
  color: var(--yellow) !important;
}

/* ── CATEGORY SECTIONS ── */
.rc-category { margin-bottom: 56px; }
.rc-category h2 {
  font-size: 1.6rem;
  font-weight: 800;
  margin: 0 0 24px;
  color: var(--offblack);
  display: flex;
  align-items: center;
  gap: 12px;
}
.rc-category h2::after {
  content: "";
  flex-grow: 1;
  height: 1px;
  background: var(--lightgray);
}

/* ── LEARNING PATH CARDS ── */
.rc-path-list { display: flex; flex-direction: column; gap: 16px; }
.rc-path-card {
  background: var(--offwhite);
  border: 1px solid var(--lightgray);
  border-radius: 12px;
  padding: 20px 24px;
  text-decoration: none !important;
  color: inherit;
  transition: all .2s ease;
  display: grid;
  grid-template-columns: auto 1fr auto;
  gap: 24px;
  align-items: center;
}
.rc-path-card:hover {
  border-color: var(--yellow);
  box-shadow: 0 4px 16px rgba(255,215,6,.12);
  transform: translateY(-2px);
  text-decoration: none !important;
}
.rc-path-icon {
  width: 48px;
  height: 48px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--brightgray);
  border: 1px solid rgba(0,0,0,0.05);
  flex-shrink: 0;
}
.rc-path-icon img { width: 24px; height: 24px; object-fit: contain; }
.rc-path-content { min-width: 0; }
.rc-path-content h3 { font-size: 1.1rem; font-weight: 800; margin: 0 0 6px; color: var(--offblack); text-decoration: none !important; }
.rc-path-content p { font-size: .92rem; color: var(--gray); line-height: 1.5; margin: 0; text-decoration: none !important; }
.rc-path-arrow { color: var(--orange); font-weight: 700; font-size: .9rem; text-decoration: none !important; white-space: nowrap; }

/* ── GETTING STARTED CTA ── */
.rc-starter-cta { background: var(--brightgray); border: 1px solid var(--lightgray); border-radius: 16px; padding: 24px 32px; display: flex; align-items: center; justify-content: space-between; gap: 24px; margin-bottom: 56px; }
.rc-starter-text h3 { margin: 0 0 6px; font-size: 1.2rem; font-weight: 800; color: var(--offblack); }
.rc-starter-text p { margin: 0; font-size: .95rem; color: var(--darkgray); line-height: 1.5; }
.rc-btn-secondary { background: transparent; color: var(--offblack); text-decoration: none !important; padding: 10px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--offblack); white-space: nowrap; transition: all .2s; }
.rc-btn-secondary:hover { background: var(--offblack); color: var(--yellow) !important; }

/* ── FOOTER SUMMARY ── */
.rc-footer-summary { margin-top: 40px; padding-top: 32px; border-top: 1px solid var(--lightgray); text-align: center; color: var(--gray); font-size: .95rem; line-height: 1.6; max-width: 800px; margin-left: auto; margin-right: auto; margin-bottom: 24px; }
.rc-footer-summary strong { color: var(--darkgray); }
.rc-footer-summary a { color: var(--orange); text-decoration: none !important; font-weight: 700; }
.rc-footer-summary a:hover { text-decoration: underline !important; }

/* ── FOOTER NAV ── */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 32px; margin-top: 20px; text-align: center; }
.rc-footer-title { font-size: .85rem; font-weight: 700; text-transform: uppercase; letter-spacing: 1px; color: var(--gray); margin-bottom: 16px; }
.rc-footer-links { display: flex; flex-wrap: wrap; gap: 12px; justify-content: center; }
.rc-footer-link { color: var(--darkgray); text-decoration: none !important; font-weight: 700; font-size: .9rem; padding: 8px 20px; background: var(--brightgray); border-radius: 8px; transition: all .2s; }
.rc-footer-link:hover { background: var(--offblack); color: var(--yellow) !important; }

/* ── RESPONSIVE ── */
@media(max-width:768px){
  .rc-path-card { grid-template-columns: 1fr; gap: 16px; }
  .rc-path-arrow { margin-top: 4px; }
  .rc-hero { padding: 36px 20px 40px; }
  .rc-content-wrap { padding: 0 20px; }
  .rc-starter-cta { flex-direction: column; align-items: flex-start; }
  .rc-announce-bar { flex-direction: column; align-items: flex-start; gap: 8px; }
  .rc-top-nav { padding: 16px 20px; }
}
</style>
</head>
<body>
<div class="rc-guide">

  <div class="rc-top-nav">
    <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-back-link">← Back to Navigate Hub</a>
  </div>

  <div class="rc-content-wrap">

    <!-- ── ANNOUNCEMENT BAR ── -->
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>This Thursday:</strong> Global Office Hours — Dunning windows &amp; payment recovery with our lead CSMs.
        <a href="https://navigate.recurly.com/global-office-hours/" target="_blank" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="document.getElementById('rcAnnounce').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <!-- ── HERO ── -->
    <div class="rc-hero">
      <div class="rc-brand-header">
        <img src="https://files.readme.io/3a81c518f47c7b9564898238f77cc4fcab026e99e7a7f09817e9815d89e0b297-Logo_for_Black_BG_V1.svg" alt="Recurly" class="rc-logo-image">
      </div>
      <div class="rc-pillar-hero-icon">
        <img src="https://files.readme.io/b6c93b0c856b23bcb18d1c1f5106eb9c83d23d9b505dc37e5ce9ea0d8dcfe89b-Launch-icon-white.png" alt="Launch" />
      </div>
      <h1>Launch</h1>
      <p>Get configured and live fast. Build a solid subscription foundation from day one by mastering the core elements of the Recurly platform.</p>
    </div>

    <!-- ── EXPANDING NAV ── -->
    <div class="rc-sticky-nav-wrap">
      <button class="rc-nav-toggle" id="rcNavToggle" onclick="rcToggleNav()" aria-expanded="false" aria-controls="rcNavDrawer">
        <span class="rc-nav-toggle-label">
          <img src="https://files.readme.io/532693d4eb61149090deae2d52890bb6fc25bd87004b2c7e0d09cca1b116df0e-Yellow_Navigate_Pin.png" alt="">
          Launch — Navigate
          <span class="rc-nav-hint">— tap to explore</span>
        </span>
        <span class="rc-nav-chevron" id="rcNavChevron">▼</span>
      </button>
      <div class="rc-nav-drawer" id="rcNavDrawer" role="navigation">
        <div class="rc-nav-drawer-inner">

          <div>
            <div class="rc-nav-group-label">Navigate</div>
            <div class="rc-nav-links">
              <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-home" class="rc-sticky-link">🏠 Home</a>
              <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-sticky-link">Launch</a>
              <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-acquire" class="rc-sticky-link">Acquire</a>
              <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-sticky-link">Retain</a>
              <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-scale" class="rc-sticky-link">Scale</a>
              <a href="https://navigate.recurly.com/event-hub/" class="rc-sticky-link" target="_blank">Events ↗</a>
              <a href="https://navigate.recurly.com/global-office-hours/" class="rc-sticky-link" target="_blank">Office Hours ↗</a>
            </div>
          </div>

          <div>
            <div class="rc-nav-group-label">On This Page</div>
            <div class="rc-nav-links">
              <a href="#launchpad" class="rc-sticky-link rc-sticky-link-anchor">Launchpad</a>
              <a href="#technical" class="rc-sticky-link rc-sticky-link-anchor">Technical Setup</a>
              <a href="#onboarding" class="rc-sticky-link rc-sticky-link-anchor">Onboarding</a>
            </div>
          </div>

        </div>
      </div>
    </div>

    <!-- ── LAUNCHPAD ── -->
    <div id="launchpad" class="rc-category">
      <h2>Launchpad</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Launchpad Phase One: Optimize</h3>
            <p>Ensure your Recurly instance is configured for maximum impact. Learn best practices for site settings, payment gateways, and baseline security.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Launchpad Phase Two: Mastering Metrics</h3>
            <p>Dive deep into Recurly Analytics. Understand your core subscription KPIs, how to read your dashboards, and track success from day one.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
      </div>
    </div>

    <!-- ── TECHNICAL SETUP ── -->
    <div id="technical" class="rc-category">
      <h2>Technical Setup</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>API &amp; Webhook Fundamentals</h3>
            <p>Learn how to authenticate, connect your backend architecture, and listen to real-time Recurly events seamlessly.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Data Migration Guide</h3>
            <p>Step-by-step instructions for importing your existing customer data, billing information, and active subscriptions securely into Recurly.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
      </div>
    </div>

    <!-- ── ONBOARDING ── -->
    <div id="onboarding" class="rc-category">
      <h2>Onboarding</h2>
      <div class="rc-path-list">
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>The First 30 Days Playbook</h3>
            <p>A structured checklist and strategic guide for your entire team to ensure a flawless, stress-free go-live experience.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
        <a href="#" class="rc-path-card">
          <div class="rc-path-icon">
            <img src="https://files.readme.io/41c9ced85b9940e8600982eafb33c6d68fc11d01dd9f2fc7611155c43ce3d3fe-Launch-icon-black.png" alt="Icon" style="opacity:.6;" />
          </div>
          <div class="rc-path-content">
            <h3>Team Training &amp; Permissions</h3>
            <p>Learn how to invite new users, set up role-based access control, and train your staff on navigating the admin console.</p>
          </div>
          <div class="rc-path-arrow">Start Path →</div>
        </a>
      </div>
    </div>

    <!-- ── CTA ── -->
    <div class="rc-starter-cta">
      <div class="rc-starter-text">
        <h3>👋 Need live guidance on your Launch?</h3>
        <p>Bring your configuration questions directly to our experts during our weekly open-forum sessions.</p>
      </div>
      <a href="https://navigate.recurly.com/global-office-hours/" class="rc-btn-secondary" target="_blank">Register for Office Hours</a>
    </div>

    <!-- ── FOOTER SUMMARY ── -->
    <div class="rc-footer-summary">
      <strong>Maximizing your subscription potential.</strong>
      <p>Navigate is designed to put Recurly's strategic insights directly in your hands, ensuring you have the resources needed to drive revenue and scale efficiently. Have questions about the program? Reach out to <a href="mailto:support@recurly.com">support@recurly.com</a>.</p>
    </div>

    <!-- ── FOOTER NAV ── -->
    <div class="rc-footer-nav">
      <div class="rc-footer-title">Jump to a section</div>
      <div class="rc-footer-links">
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-launch" class="rc-footer-link">Launch</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-acquire" class="rc-footer-link">Acquire</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/navigate-retain" class="rc-footer-link">Retain</a>
        <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-navigate-scale" class="rc-footer-link">Scale</a>
        <a href="https://navigate.recurly.com/event-hub/" class="rc-footer-link" target="_blank">Events ↗</a>
        <a href="https://navigate.recurly.com/global-office-hours/" class="rc-footer-link" target="_blank">Office Hours ↗</a>
      </div>
    </div>

  </div>
</div>

<script>
function rcToggleNav() {
  var drawer  = document.getElementById('rcNavDrawer');
  var chevron = document.getElementById('rcNavChevron');
  var toggle  = document.getElementById('rcNavToggle');
  var isOpen  = drawer.classList.toggle('rc-open');
  chevron.classList.toggle('rc-open');
  toggle.setAttribute('aria-expanded', isOpen ? 'true' : 'false');
}
</script>
</body>
</html>
`}</HTMLBlock>

<br />
