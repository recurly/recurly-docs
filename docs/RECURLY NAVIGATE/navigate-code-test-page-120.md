---
title: 'Navigate Code Test Page Dunning 101: The Basics'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
html { scroll-behavior: smooth; scroll-padding-top: 80px; }

.rc-guide {
  --yellow:    #FFD706;
  --orange:    #FF8200;
  --offblack:  #0D0D0B;
  --darkgray:  #32312D;
  --gray:      #807D73;
  --lightgray: #CCC9B8;
  --brightgray:#F1EFE3;
  --offwhite:  #FFFDF2;
  --retain:    #FF9D88;
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}
.rc-guide * { box-sizing: border-box; }

.rc-top-nav { padding: 20px 40px 16px; max-width: 1200px; margin: 0 auto; }
.rc-back-link { color: var(--gray); text-decoration: none !important; font-weight: 700; font-size: .9rem; display: inline-flex; align-items: center; gap: 6px; transition: color .2s; }
.rc-back-link:hover { color: var(--orange); }
.rc-content-wrap { max-width: 1200px; margin: 0 auto; padding: 0 40px; }

/* Host-theme armor */
.rc-guide a,
.rc-guide a:link,
.rc-guide a:visited,
.rc-guide a:hover,
.rc-guide a:active { border-bottom: 0 !important; text-decoration: none !important; }

/* Announcement Bar */
.rc-announce-bar { display: none; background: var(--yellow); color: var(--offblack); align-items: center; justify-content: space-between; padding: 10px 20px; font-size: .88rem; font-weight: 600; border-radius: 10px; margin-bottom: 16px; gap: 12px; line-height: 1.4; }
.rc-announce-bar.rc-active { display: flex; }
.rc-announce-inner { display: flex; align-items: center; gap: 12px; flex: 1; flex-wrap: wrap; }
.rc-announce-link { color: var(--offblack) !important; font-weight: 800; text-decoration: none !important; white-space: nowrap; padding: 4px 12px; background: rgba(0,0,0,0.10); border-radius: 6px; transition: background 0.2s; }
.rc-announce-link:hover { background: rgba(0,0,0,0.20); }
.rc-announce-close { background: none; border: none; font-size: 1.4rem; line-height: 1; cursor: pointer; color: var(--offblack); padding: 0 2px; opacity: 0.45; transition: opacity 0.2s; flex-shrink: 0; }
.rc-announce-close:hover { opacity: 1; }

/* Hero */
.rc-hero { background: linear-gradient(rgba(13,13,11,0.82), rgba(13,13,11,0.82)), url('https://files.readme.io/7a74d62bff1d532ca5adc49ae3d1c7d39a9703386b62fa98835df5c47a5f84b1-Topo_for_Black_Background_2.png') no-repeat center center; background-color: var(--offblack); background-size: cover; color: #fff; padding: 48px 40px 44px; text-align: center; border-radius: 16px; margin-bottom: 0; }
.rc-lp-pillar-tag { display: inline-flex; align-items: center; gap: 7px; background: rgba(255,157,136,0.20); border: 1px solid rgba(255,157,136,0.45); color: #FF9D88; font-size: .75rem; font-weight: 800; letter-spacing: 1px; text-transform: uppercase; padding: 6px 14px; border-radius: 20px; margin-bottom: 20px; }
.rc-lp-pillar-tag img { width: 13px; height: 13px; object-fit: contain; }
.rc-lp-hero-title { text-align: center; margin: 0 0 14px; }
.rc-lp-hero-title h1 { font-size: 2.4rem; font-weight: 800; line-height: 1.15; color: var(--offwhite); margin: 0; }
.rc-hero > p { font-size: 1rem; opacity: .85; max-width: 640px; margin: 0 auto 32px; color: var(--lightgray); line-height: 1.6; }

/* Hero Stats */
.rc-hero-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 0; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 24px; margin-top: 4px; }
.rc-hero-stat { text-align: center; padding: 0 16px; }
.rc-hero-stat + .rc-hero-stat { border-left: 1px solid rgba(255,255,255,0.12); }
.rc-hero-stat-num { font-size: 1.9rem; font-weight: 800; color: var(--yellow); line-height: 1; margin-bottom: 6px; }
.rc-hero-stat-label { font-size: .72rem; font-weight: 600; letter-spacing: .8px; text-transform: uppercase; color: var(--lightgray); line-height: 1.3; }

/* Sticky Nav Wrap */
details.rc-sticky-nav-wrap { position: sticky; top: 0; z-index: 100; background-color: var(--retain); box-shadow: 0 4px 12px rgba(0,0,0,0.08); margin: 24px 0 48px 0; border-radius: 12px; border: 1px solid rgba(0,0,0,0.08); overflow: hidden; }
details.rc-sticky-nav-wrap > summary { list-style: none; display: flex; align-items: center; padding: 15px 24px; cursor: pointer; user-select: none; }
details.rc-sticky-nav-wrap > summary::-webkit-details-marker { display: none; }
details.rc-sticky-nav-wrap > summary::marker { display: none; }
.rc-nav-toggle-label { display: inline-flex; align-items: center; gap: 8px; font-weight: 800; font-size: .88rem; letter-spacing: 0.6px; text-transform: uppercase; color: var(--offblack); }
.rc-nav-chevron { font-size: .72rem; color: var(--offblack); opacity: 0.55; line-height: 1; transition: transform 0.25s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-chevron { transform: rotate(180deg); }
.rc-nav-drawer { display: grid; grid-template-rows: 0fr; transition: grid-template-rows 0.3s ease; }
details.rc-sticky-nav-wrap[open] .rc-nav-drawer { grid-template-rows: 1fr; }
.rc-nav-drawer-inner { overflow: hidden; border-top: 1px solid rgba(0,0,0,0.10); }
.rc-nav-links { display: flex; flex-wrap: wrap; gap: 6px 4px; padding: 12px 20px 18px; }

.rc-sticky-link { color: var(--offblack) !important; text-decoration: none !important; font-weight: 700; font-size: .83rem; letter-spacing: 0.4px; text-transform: uppercase; padding: 7px 14px; border-radius: 7px; transition: all .18s; white-space: nowrap; display: inline-flex; align-items: center; gap: 6px; }
.rc-sticky-link:hover { background: var(--offblack); color: var(--yellow) !important; }
.rc-sticky-link img { width: 15px; height: 15px; object-fit: contain; }
.rc-step-badge { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--offblack); color: var(--yellow); font-size: .65rem; font-weight: 800; flex-shrink: 0; line-height: 1; }
.rc-sticky-link:hover .rc-step-badge { background: var(--yellow); color: var(--offblack); }
.rc-sticky-link-active { background: rgba(0,0,0,0.12); font-weight: 800; }
.rc-sticky-link-active:hover { background: var(--offblack); color: var(--yellow) !important; }

/* Intro text */
.rc-lp-intro { font-size: 1.05rem; line-height: 1.6; color: var(--darkgray); margin-bottom: 32px; }

/* TOC Cards */
.rc-toc-list { display: flex; flex-direction: column; gap: 10px; margin: 0 0 40px; }
.rc-toc-card { display: grid; grid-template-columns: 44px 1fr 32px; align-items: center; gap: 16px; background: var(--offwhite); border: 1px solid var(--lightgray); border-radius: 12px; padding: 18px 22px; transition: all .2s ease; }
.rc-guide a.rc-toc-card { border-bottom: 1px solid var(--lightgray) !important; }
.rc-guide a.rc-toc-card:hover { border-color: #FF9D88; border-bottom: 1px solid #FF9D88 !important; box-shadow: 0 4px 14px rgba(255,157,136,0.12); transform: translateX(3px); }
.rc-toc-num { width: 36px; height: 36px; border-radius: 50%; background: var(--offblack); color: var(--yellow); display: flex; align-items: center; justify-content: center; font-size: .85rem; font-weight: 800; flex-shrink: 0; }
.rc-toc-body h4 { font-size: .98rem; font-weight: 800; color: var(--offblack); margin: 0 0 4px; }
.rc-toc-body p { font-size: .88rem; color: var(--gray); line-height: 1.5; margin: 0; }
.rc-toc-arrow { font-size: 1.1rem; color: var(--lightgray); text-align: right; transition: color .2s; }
.rc-guide a.rc-toc-card:hover .rc-toc-arrow { color: #FF9D88; }

/* Path Navigation */
.rc-lp-nav { display: flex; align-items: center; justify-content: space-between; gap: 16px; margin: 40px 0 16px; }
.rc-lp-nav-indicator { font-size: .8rem; font-weight: 600; color: var(--lightgray); letter-spacing: .5px; }
.rc-guide a.rc-btn-path { background: var(--yellow); color: var(--offblack) !important; text-decoration: none !important; padding: 13px 28px; border-radius: 10px; font-weight: 800; font-size: .95rem; display: inline-flex; align-items: center; gap: 8px; transition: all .2s; border: 2px solid var(--yellow); }
.rc-guide a.rc-btn-path:hover { background: transparent !important; color: var(--offblack) !important; border: 2px solid var(--yellow) !important; border-bottom: 2px solid var(--yellow) !important; }
.rc-btn-start { background: var(--brightgray); color: var(--gray); padding: 13px 24px; border-radius: 10px; font-weight: 700; font-size: .9rem; border: 2px solid var(--lightgray); cursor: default; }

/* Footer Nav */
.rc-footer-nav { border-top: 1px solid var(--lightgray); padding-top: 40px; margin-top: 48px; padding-bottom: 48px; }
.rc-footer-links { display: flex; flex-direction: column; gap: 16px; }
.rc-footer-section { display: flex; flex-wrap: wrap; align-items: center; gap: 8px 24px; }
.rc-footer-label { font-weight: 800; font-size: .75rem; text-transform: uppercase; letter-spacing: .8px; color: var(--darkgray); background: var(--brightgray); padding: 4px 10px; border-radius: 6px; margin-right: 4px; }
.rc-footer-link { color: var(--gray); text-decoration: none !important; font-weight: 600; font-size: .88rem; transition: color .2s ease; display: inline-flex; align-items: center; gap: 6px; }
.rc-footer-link:hover { color: var(--orange); }
.rc-footer-link img { width: 14px; height: 14px; object-fit: contain; opacity: 0.5; transition: opacity .2s ease; }
.rc-footer-link:hover img { opacity: 1; }
.rc-footer-utility { display: flex; flex-wrap: wrap; gap: 24px; margin-top: 16px; padding-top: 24px; border-top: 1px solid var(--brightgray); }

/* Mobile Breakpoints */
@media(max-width:768px){
  .rc-content-wrap { padding: 0 20px; }
  .rc-top-nav { padding: 16px 20px; }
  .rc-hero { padding: 36px 20px 36px; }
  .rc-lp-hero-title h1 { font-size: 1.8rem; }
  .rc-hero-stats { grid-template-columns: 1fr; gap: 16px; border-top: none; padding-top: 0; }
  .rc-hero-stat + .rc-hero-stat { border-left: none; border-top: 1px solid rgba(255,255,255,0.12); padding-top: 16px; margin-top: 0; }
  .rc-oh-cta { padding: 24px 20px; }
  .rc-lp-nav { flex-wrap: wrap; justify-content: center; }
  .rc-lp-nav-indicator { width: 100%; text-align: center; }
  .rc-card-grid, .rc-card-grid.rc-card-grid-3col { grid-template-columns: 1fr; }
  .rc-stat-strip { grid-template-columns: 1fr; }
  .rc-next-grid { grid-template-columns: 1fr; }
  .rc-toc-card { grid-template-columns: 36px 1fr 24px; padding: 14px 16px; }
}
</style>

<div class="rc-guide">
  <div class="rc-top-nav">
    <a href="/docs/navigate-retain" class="rc-back-link">← Back to Retain</a>
  </div>

  <div class="rc-content-wrap">
    
    <div class="rc-announce-bar" id="rcAnnounce">
      <div class="rc-announce-inner">
        🗓️ <strong>Upcoming:</strong> Join our CSMs for a live session.
        <a href="https://navigate.recurly.com/event-hub/" target="_blank" rel="noopener noreferrer" class="rc-announce-link">Register Now →</a>
      </div>
      <button class="rc-announce-close" onclick="this.closest('.rc-announce-bar').style.display='none'" aria-label="Dismiss">×</button>
    </div>

    <div class="rc-hero">
      <div class="rc-lp-pillar-tag">
        <img src="https://files.readme.io/4307b701706e500c878481348869b422f7b4632dc98773184d97596d2d977f87-Retain-icon-white.png" alt="Retain"> RETAIN
      </div>
      <div class="rc-lp-hero-title">
        <h1>Dunning 101: The Basics</h1>
      </div>
      <p>Recover more revenue, reduce passive churn, and build a dunning strategy that works quietly in the background.</p>
      
      <div class="rc-hero-stats">
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">3–5%</div>
          <div class="rc-hero-stat-label">Avg Recovery Uplift</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">27 Days</div>
          <div class="rc-hero-stat-label">Monthly Window</div>
        </div>
        <div class="rc-hero-stat">
          <div class="rc-hero-stat-num">Up to 40%</div>
          <div class="rc-hero-stat-label">Of Churn Is Passive</div>
        </div>
      </div>
    </div>

    <details class="rc-sticky-nav-wrap">
      <summary>
        <span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span>
      </summary>
      <div class="rc-nav-drawer">
        <div class="rc-nav-drawer-inner">
          <div class="rc-nav-links">
            <a href="/docs/navigate-home" class="rc-sticky-link">
              <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home
            </a>
            <a href="/docs/dunning-101-overview" class="rc-sticky-link rc-sticky-link-active">
              <img src="https://files.readme.io/070e914d23dead09604d5f96b8769c88b8aae704ebd4505415e5854011030110-Black_Navigate_Home_Pin_1.png" alt="Current Page"> Dunning 101: The Basics
            </a>
            <a href="/docs/dunning-101-basics" class="rc-sticky-link">Dunning Basics</a>
            <a href="/docs/dunning-101-setup" class="rc-sticky-link">Setup &amp; Configuration</a>
            <a href="/docs/dunning-101-email-strategy" class="rc-sticky-link">Email Strategy</a>
            <a href="/docs/dunning-101-subscriber-engagement" class="rc-sticky-link">Subscriber Engagement</a>
            <a href="/docs/dunning-101-advanced-configuration" class="rc-sticky-link">Advanced Configuration</a>
            <a href="/docs/dunning-101-metrics" class="rc-sticky-link">Metrics &amp; Tracking</a>
            <a href="/docs/dunning-101-strategy-and-resources" class="rc-sticky-link">Strategy &amp; Resources</a>
          </div>
        </div>
      </div>
    </details>

    <p class="rc-lp-intro">This learning path covers the essential configuration options and recovery mechanics of your dunning setup. By mastering these fundamentals, you can build a systematic approach to resolving failed payments and significantly reduce involuntary subscriber churn.</p>

    <div class="rc-toc-list">
      <a href="/docs/dunning-101-basics" class="rc-toc-card">
        <div class="rc-toc-num">1</div>
        <div class="rc-toc-body">
          <h4>Dunning Basics</h4>
          <p>What dunning is, how it works, why it matters, and where it fits in your revenue recovery toolkit.</p>
        </div>
        <div class="rc-toc-arrow">→</div>
      </a>
      
      <a href="/docs/dunning-101-setup" class="rc-toc-card">
        <div class="rc-toc-num">2</div>
        <div class="rc-toc-body">
          <h4>Setup &amp; Configuration</h4>
          <p>A step-by-step walkthrough from accessing dunning for the first time to a fully optimized campaign.</p>
        </div>
        <div class="rc-toc-arrow">→</div>
      </a>

      <a href="/docs/dunning-101-email-strategy" class="rc-toc-card">
        <div class="rc-toc-num">3</div>
        <div class="rc-toc-body">
          <h4>Email Strategy</h4>
          <p>Five tips covering everything about how your dunning emails look, feel, and communicate.</p>
        </div>
        <div class="rc-toc-arrow">→</div>
      </a>

      <a href="/docs/dunning-101-subscriber-engagement" class="rc-toc-card">
        <div class="rc-toc-num">4</div>
        <div class="rc-toc-body">
          <h4>Subscriber Engagement</h4>
          <p>Two tips that work best together — showing subscribers exactly what's at stake and when it will happen.</p>
        </div>
        <div class="rc-toc-arrow">→</div>
      </a>

      <a href="/docs/dunning-101-advanced-configuration" class="rc-toc-card">
        <div class="rc-toc-num">5</div>
        <div class="rc-toc-body">
          <h4>Advanced Configuration</h4>
          <p>Three tips for the more technical and strategic setup decisions that take dunning from good to great.</p>
        </div>
        <div class="rc-toc-arrow">→</div>
      </a>

      <a href="/docs/dunning-101-metrics" class="rc-toc-card">
        <div class="rc-toc-num">6</div>
        <div class="rc-toc-body">
          <h4>Metrics &amp; Tracking</h4>
          <p>The three core metrics to track after making changes, where to find them in Recurly, and how to interpret what you see.</p>
        </div>
        <div class="rc-toc-arrow">→</div>
      </a>

      <a href="/docs/dunning-101-strategy-and-resources" class="rc-toc-card">
        <div class="rc-toc-num">7</div>
        <div class="rc-toc-body">
          <h4>Strategy &amp; Resources</h4>
          <p>Strategic prompts to deepen your thinking, a full action checklist, and everything you need to go further.</p>
        </div>
        <div class="rc-toc-arrow">→</div>
      </a>
    </div>

    <p class="rc-lp-intro">Each Micro-Path builds on the last — work through them in order for the full picture, or jump to the topic most relevant to you right now.</p>

    <div class="rc-lp-nav">
      <span class="rc-btn-start">Start</span>
      <span class="rc-lp-nav-indicator">1 of 8</span>
      <a href="/docs/dunning-101-basics" class="rc-btn-path">Next: Dunning Basics →</a>
    </div>

    <div class="rc-footer-nav">
      <div class="rc-footer-links">
        <div class="rc-footer-section">
          <span class="rc-footer-label">Learning Path: Dunning 101:</span>
          <a href="/docs/dunning-101-basics" class="rc-footer-link">Dunning Basics</a>
          <a href="/docs/dunning-101-setup" class="rc-footer-link">Setup &amp; Configuration</a>
          <a href="/docs/dunning-101-email-strategy" class="rc-footer-link">Email Strategy</a>
          <a href="/docs/dunning-101-subscriber-engagement" class="rc-footer-link">Subscriber Engagement</a>
          <a href="/docs/dunning-101-advanced-configuration" class="rc-footer-link">Advanced Configuration</a>
          <a href="/docs/dunning-101-metrics" class="rc-footer-link">Metrics &amp; Tracking</a>
          <a href="/docs/dunning-101-strategy-and-resources" class="rc-footer-link">Strategy &amp; Resources</a>
        </div>

        <div class="rc-footer-utility">
          <a href="/docs/navigate-home" class="rc-footer-link">
            <img src="https://files.readme.io/105d407afb9e682bd60fbc60587b3da1cfb3d09be95148d71529b20fb286aadf-Home_icon_2.png" alt="Home"> Navigate Home
          </a>
          <a href="mailto:support@recurly.com" class="rc-footer-link">Contact Support</a>
        </div>
      </div>
    </div>

  </div>
</div>
`}</HTMLBlock>

<br />