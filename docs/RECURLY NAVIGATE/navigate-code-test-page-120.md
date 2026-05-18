---
title: Navigate Code Test Page 120
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
.rc-guide {
  --yellow: #FFD706;
  --orange: #FF8200;
  --offblack: #0D0D0B;
  --darkgray: #32312D;
  --gray: #807D73;
  --lightgray: #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite: #FFFDF2;
  --retain: #00D28E; 
  font-family: 'Segoe UI', system-ui, sans-serif;
  color: var(--darkgray);
}

.rc-guide * { 
  box-sizing: border-box; 
}

.rc-guide a { 
  text-decoration: none; 
}

/* Back Link */
.rc-back-link {
  display: inline-flex;
  align-items: center;
  font-size: 0.85rem;
  font-weight: 600;
  color: var(--gray);
  margin-bottom: 24px;
  transition: color 0.2s;
}

.rc-back-link:hover {
  color: var(--offblack);
}

/* Hero Section */
.rc-hero {
  background: var(--offblack);
  color: #fff;
  padding: 56px 40px 48px;
  text-align: center;
  border-radius: 16px;
  margin-bottom: 32px;
}

.rc-badge {
  display: inline-block;
  background: var(--yellow);
  color: var(--offblack);
  border-radius: 20px;
  padding: 6px 18px;
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 1px;
  text-transform: uppercase;
  margin-bottom: 20px;
}

.rc-hero h1 {
  font-size: 2.2rem;
  font-weight: 800;
  line-height: 1.15;
  margin: 0 0 14px;
  color: var(--offwhite);
}

.rc-hero p {
  font-size: 1.05rem;
  opacity: 0.8;
  max-width: 680px;
  margin: 0 auto 32px;
  color: var(--lightgray);
  line-height: 1.6;
}

/* Hero Stats - Path Level */
.rc-hero-stats {
  display: flex;
  justify-content: center;
  gap: 40px;
  flex-wrap: wrap;
}

.rc-num {
  font-size: 1.8rem;
  font-weight: 800;
  color: var(--yellow); 
  margin-bottom: 4px;
}

.rc-lbl {
  font-size: 0.8rem;
  color: var(--lightgray);
  text-transform: uppercase;
  letter-spacing: 0.5px;
  font-weight: 600;
}

/* Sticky Nav Wrap */
.rc-sticky-nav-wrap {
  position: sticky;
  top: 0;
  z-index: 100;
  background: #fff;
  border-bottom: 1px solid var(--lightgray);
  margin: 0 -20px 32px;
  padding: 16px 20px;
}

.rc-sticky-nav-wrap summary {
  list-style: none;
  cursor: pointer;
  font-weight: 700;
  font-size: 0.95rem;
  color: var(--offblack);
}

.rc-nav-toggle-label {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
}

.rc-sticky-nav-wrap summary::-webkit-details-marker {
  display: none;
}

.rc-nav-chevron {
  font-size: 0.8rem;
  color: var(--gray);
}

.rc-nav {
  display: flex;
  flex-direction: column;
  gap: 8px;
  margin-top: 16px;
}

.rc-sticky-link {
  display: flex;
  align-items: center;
  padding: 10px 14px;
  border-radius: 8px;
  color: var(--darkgray);
  font-size: 0.9rem;
  font-weight: 600;
  transition: background 0.2s, color 0.2s;
}

.rc-sticky-link:hover {
  background: var(--brightgray);
  color: var(--offblack);
}

/* LP Content Intro */
.rc-intro-text {
  font-size: 1.05rem;
  color: var(--darkgray);
  line-height: 1.6;
  margin-bottom: 32px;
}

/* TOC Cards */
.rc-toc-list {
  display: flex;
  flex-direction: column;
  gap: 16px;
  margin-bottom: 40px;
}

.rc-toc-card {
  background: var(--offwhite);
  border: 1px solid var(--lightgray);
  border-radius: 12px;
  padding: 24px;
  display: flex;
  flex-direction: column;
  gap: 8px;
  transition: border-color 0.2s, box-shadow 0.2s;
}

.rc-toc-card:hover {
  border-color: var(--yellow);
  box-shadow: 0 4px 12px rgba(255, 215, 6, 0.1);
}

.rc-toc-card h3 {
  font-size: 1.1rem;
  font-weight: 700;
  margin: 0;
  color: var(--offblack);
}

.rc-toc-card p {
  font-size: 0.92rem;
  color: var(--gray);
  margin: 0 0 12px;
  line-height: 1.6;
}

.rc-toc-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 16px;
  background: #fff;
  border: 1px solid var(--lightgray);
  border-radius: 8px;
  font-size: 0.85rem;
  font-weight: 700;
  color: var(--darkgray);
  width: fit-content;
  transition: all 0.2s;
}

.rc-toc-card:hover .rc-toc-btn {
  background: var(--yellow);
  border-color: var(--yellow);
  color: var(--offblack);
}

/* Path Navigation Buttons */
.rc-sec-nav {
  display: flex;
  justify-content: flex-end;
  margin-top: 32px;
}

.rc-btn-next {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 12px 24px;
  border-radius: 10px;
  font-weight: 700;
  font-size: 0.95rem;
  background: var(--yellow);
  color: var(--offblack);
  border: 1px solid var(--yellow);
  transition: opacity 0.2s;
}

.rc-btn-next:hover {
  opacity: 0.9;
}

/* Footer Group */
.rc-footer-section {
  margin-top: 64px;
}

.rc-footer-utility {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-top: 1px solid var(--lightgray);
  padding-top: 24px;
  font-size: 0.85rem;
}

.rc-footer-utility a {
  color: var(--gray);
  font-weight: 600;
  transition: color 0.2s;
}

.rc-footer-utility a:hover {
  color: var(--offblack);
}
</style>

<div class="rc-guide">

  <a href="/docs/retain" class="rc-back-link">← Back to Retain</a>

  <div class="rc-hero">
    <div class="rc-badge">Learning Path</div>
    <h1>Dunning 101: The Basics</h1>
    <p>Recover more revenue, reduce passive churn, and build a dunning strategy that works quietly in the background.</p>
    
    <div class="rc-hero-stats">
      <div>
        <div class="rc-num">3–5%</div>
        <div class="rc-lbl">Avg Recovery Uplift</div>
      </div>
      <div>
        <div class="rc-num">27 Days</div>
        <div class="rc-lbl">Monthly Window</div>
      </div>
      <div>
        <div class="rc-num">Up to 40%</div>
        <div class="rc-lbl">Of Churn Is Passive</div>
      </div>
    </div>
  </div>

  <details class="rc-sticky-nav-wrap">
    <summary><span class="rc-nav-toggle-label">Navigation Menu <span class="rc-nav-chevron">▲</span></span></summary>
    <nav class="rc-nav">
      <a href="#basics" class="rc-sticky-link">Dunning Basics</a>
      <a href="#setup" class="rc-sticky-link">Setup &amp; Configuration</a>
      <a href="#email" class="rc-sticky-link">Email Strategy</a>
      <a href="#engagement" class="rc-sticky-link">Subscriber Engagement</a>
      <a href="#advanced" class="rc-sticky-link">Advanced Configuration</a>
      <a href="#metrics" class="rc-sticky-link">Metrics &amp; Tracking</a>
      <a href="#strategy" class="rc-sticky-link">Strategy &amp; Resources</a>
    </nav>
  </details>

  <p class="rc-intro-text">This learning path provides the essential knowledge and tools to master your Recurly Dunning strategy. You will walk step-by-step from accessing dunning for the first time to launching a fully optimized campaign. Learn to configure your setup using proven best practices, significantly reducing involuntary churn for sustained subscription growth.</p>

  <div class="rc-toc-list">
    <div class="rc-toc-card">
      <h3>Dunning Basics</h3>
      <p>What dunning is, how it works, why it matters, and where it fits in your revenue recovery toolkit.</p>
      <a href="/docs/dunning-101-basics" class="rc-toc-btn">Start Micro-Path</a>
    </div>
    
    <div class="rc-toc-card">
      <h3>Setup &amp; Configuration</h3>
      <p>A step-by-step walkthrough from accessing dunning for the first time to a fully optimized campaign.</p>
      <a href="/docs/dunning-101-setup" class="rc-toc-btn">Start Micro-Path</a>
    </div>

    <div class="rc-toc-card">
      <h3>Email Strategy</h3>
      <p>Five tips covering everything about how your dunning emails look, feel, and communicate.</p>
      <a href="/docs/dunning-101-email-strategy" class="rc-toc-btn">Start Micro-Path</a>
    </div>

    <div class="rc-toc-card">
      <h3>Subscriber Engagement</h3>
      <p>Two tips that work best together — showing subscribers exactly what's at stake and when it will happen.</p>
      <a href="/docs/dunning-101-subscriber-engagement" class="rc-toc-btn">Start Micro-Path</a>
    </div>

    <div class="rc-toc-card">
      <h3>Advanced Configuration</h3>
      <p>Three tips for the more technical and strategic setup decisions that take dunning from good to great.</p>
      <a href="/docs/dunning-101-advanced-configuration" class="rc-toc-btn">Start Micro-Path</a>
    </div>

    <div class="rc-toc-card">
      <h3>Metrics &amp; Tracking</h3>
      <p>The three core metrics to track after making changes, where to find them in Recurly, and how to interpret what you see.</p>
      <a href="/docs/dunning-101-metrics" class="rc-toc-btn">Start Micro-Path</a>
    </div>

    <div class="rc-toc-card">
      <h3>Strategy &amp; Resources</h3>
      <p>Strategic prompts to deepen your thinking, a full action checklist, and everything you need to go further.</p>
      <a href="/docs/dunning-101-strategy-and-resources" class="rc-toc-btn">Start Micro-Path</a>
    </div>
  </div>

  <div class="rc-sec-nav">
    <a href="/docs/dunning-101-basics" class="rc-btn-next">Start Learning Path →</a>
  </div>

  <div class="rc-footer-section">
    <div class="rc-footer-utility">
      <a href="/docs/navigate-home" target="_self">Navigate Home</a>
      <a href="mailto:support@recurly.com" target="_blank" rel="noopener noreferrer">Contact Support</a>
    </div>
  </div>

</div>
`}</HTMLBlock>

<br />
