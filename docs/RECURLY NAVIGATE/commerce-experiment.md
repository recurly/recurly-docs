---
title: Commerce Experiment
deprecated: false
hidden: true
metadata:
  robots: index
---
<br />

<Tabs>
  <Tab title="First Tab">
<HTMLBlock>{`
<style>
  /* ── RECURLY BRAND TOKENS ── */
.rc-guide {
  --yellow:     #FFD706;
  --orange:     #FF8200;
  --vermillion: #FF5810;
  --salmon:     #FF9D88;
  --offblack:   #0D0D0B;
  --darkgray:   #32312D;
  --gray:       #807D73;
  --lightgray:  #CCC9B8;
  --brightgray: #F1EFE3;
  --offwhite:   #FFFDF2;
  font-family: 'Segoe UI', system-ui, sans-serif;
}

/* HERO */
.rc-hero {
  background: var(--offblack);
  color: white;
  padding: 56px 40px 48px;
  text-align: center;
  border-radius: 16px;
  margin-bottom: 0;
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
  font-size: 2.4rem;
  font-weight: 800;
  line-height: 1.15;
  margin-bottom: 14px;
  color: var(--offwhite);
}
.rc-hero > p {
  font-size: 1.05rem;
  opacity: 0.8;
  max-width: 600px;
  margin: 0 auto 32px;
  color: var(--lightgray);
}
.rc-hero-stats {
  display: flex;
  justify-content: center;
  gap: 40px;
  flex-wrap: wrap;
}
.rc-num { font-size: 1.8rem; font-weight: 800; color: var(--yellow); }
.rc-lbl { font-size: 0.8rem; color: var(--lightgray); text-transform: uppercase; letter-spacing: 0.5px; }

/* TABLE OF CONTENTS */
.rc-toc {
  background: var(--offwhite);
  border: 1px solid var(--lightgray);
  border-radius: 14px;
  padding: 24px 28px;
  margin: 28px 0;
}
.rc-toc-title {
  font-size: 0.82rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  color: var(--gray);
  margin-bottom: 16px;
}
.rc-toc-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
  gap: 10px;
}
.rc-toc-item {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 10px 14px;
  border-radius: 10px;
  border: 1px solid var(--lightgray);
  background: white;
  text-decoration: none;
  color: var(--darkgray);
  font-size: 0.88rem;
  font-weight: 600;
  transition: border-color 0.2s, box-shadow 0.2s;
}
.rc-toc-item:hover {
  border-color: var(--yellow);
  box-shadow: 0 2px 8px rgba(255,215,6,0.2);
  text-decoration: none;
  color: var(--offblack);
}
.rc-toc-num {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 26px;
  height: 26px;
  border-radius: 50%;
  background: var(--offblack);
  color: var(--yellow);
  font-size: 12px;
  font-weight: 700;
  flex-shrink: 0;
}
.rc-toc-launch .rc-toc-num { background: var(--orange); color: white; }

/* SECTION DIVIDER */
.rc-divider {
  border: none;
  border-top: 2px solid var(--brightgray);
  margin: 48px 0;
  position: relative;
}
.rc-divider::after {
  content: '↓';
  position: absolute;
  top: -14px;
  left: 50%;
  transform: translateX(-50%);
  background: var(--brightgray);
  color: var(--lightgray);
  width: 28px;
  height: 28px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 14px;
}

/* CONTAINER */
.rc-container { padding: 0 0 80px; }

/* SECTIONS — always visible, no toggling needed */
.rc-sec { display: block; margin-bottom: 0; }

/* SECTION HEADER */
.rc-sec-header {
  display: flex;
  align-items: flex-start;
  gap: 20px;
  margin-bottom: 32px;
}
.rc-sec-icon {
  width: 56px;
  height: 56px;
  border-radius: 16px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 26px;
  flex-shrink: 0;
  background: var(--yellow);
}
.rc-sec-header h2 { font-size: 1.7rem; font-weight: 800; margin-bottom: 6px; color: var(--offblack); }
.rc-sec-header > div > p { color: var(--gray); font-size: 0.95rem; line-height: 1.5; }

/* VIDEO CARD */
.rc-video-card {
  display: flex;
  align-items: center;
  gap: 24px;
  background: var(--darkgray);
  border-radius: 16px;
  padding: 32px;
  margin-bottom: 24px;
  text-decoration: none;
  transition: opacity 0.2s;
}
.rc-video-card:hover { opacity: 0.88; }
.rc-video-alt { background: #32312D; margin-top: -8px; }
.rc-play {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background: var(--yellow);
  color: var(--offblack);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  flex-shrink: 0;
}
.rc-play-orange { background: var(--orange); color: white; }
.rc-vmeta { color: white; }
.rc-vtag { font-size: 11px; text-transform: uppercase; letter-spacing: 1px; color: var(--lightgray); margin-bottom: 6px; }
.rc-vmeta h3 { font-size: 1.05rem; font-weight: 700; margin-bottom: 4px; color: var(--offwhite); }
.rc-vmeta p  { font-size: 0.85rem; color: var(--lightgray); margin: 0; }

/* STEP CARDS */
.rc-steps { display: flex; flex-direction: column; gap: 16px; margin-bottom: 28px; }
.rc-step {
  background: var(--offwhite);
  border-radius: 14px;
  padding: 22px 26px;
  border: 1px solid var(--lightgray);
  display: flex;
  gap: 18px;
  align-items: flex-start;
  transition: box-shadow 0.2s;
}
.rc-step:hover { box-shadow: 0 4px 16px rgba(13,13,11,0.08); }
.rc-sbadge {
  width: 38px;
  height: 38px;
  border-radius: 10px;
  background: var(--offblack);
  color: var(--yellow);
  font-weight: 800;
  font-size: 15px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}
.rc-sbadge-orange { background: var(--orange); color: white; }
.rc-sbadge-verm   { background: var(--vermillion); color: white; }
.rc-sbadge-dark   { background: var(--darkgray); color: var(--yellow); }
.rc-step h3 { font-size: 0.98rem; font-weight: 700; margin-bottom: 5px; color: var(--offblack); }
.rc-step p  { font-size: 0.87rem; color: var(--gray); line-height: 1.6; margin: 0; }

/* PRO TIP */
.rc-tip {
  background: var(--offwhite);
  border: 2px solid var(--yellow);
  border-radius: 14px;
  padding: 20px 24px;
  margin-bottom: 24px;
  display: flex;
  gap: 16px;
  align-items: flex-start;
}
.rc-tipicon { font-size: 24px; flex-shrink: 0; }
.rc-tip h4  { font-size: 0.82rem; font-weight: 700; color: var(--offblack); text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 4px; }
.rc-tip p   { font-size: 0.87rem; color: var(--darkgray); line-height: 1.55; margin: 0; }

/* WARNING */
.rc-warning {
  background: #FFF8E6;
  border: 1px solid var(--orange);
  border-radius: 14px;
  padding: 16px 20px;
  margin-bottom: 24px;
  display: flex;
  gap: 14px;
  align-items: flex-start;
}
.rc-wicon { font-size: 20px; flex-shrink: 0; }
.rc-warning p { font-size: 0.87rem; color: var(--darkgray); line-height: 1.55; margin: 0; }

/* CHECKLIST */
.rc-checklist {
  background: var(--offwhite);
  border-radius: 16px;
  border: 1px solid var(--lightgray);
  overflow: hidden;
  margin-bottom: 28px;
}
.rc-cl-header {
  padding: 16px 22px;
  border-bottom: 1px solid var(--brightgray);
  display: flex;
  align-items: center;
  gap: 10px;
  background: var(--offblack);
}
.rc-cl-header h3 { font-size: 0.88rem; font-weight: 700; text-transform: uppercase; letter-spacing: 0.5px; color: var(--yellow); margin: 0; }
.rc-cli {
  padding: 13px 22px;
  border-bottom: 1px solid var(--brightgray);
  display: flex;
  align-items: flex-start;
  gap: 14px;
}
.rc-cli:last-child { border-bottom: none; }
.rc-cb {
  width: 22px;
  height: 22px;
  border-radius: 6px;
  border: 2px solid var(--lightgray);
  flex-shrink: 0;
  margin-top: 1px;
  background: white;
}
.rc-clab { font-size: 0.88rem; color: var(--darkgray); line-height: 1.4; }
.rc-clab span { display: block; font-size: 0.78rem; color: var(--gray); margin-top: 2px; }

/* 2-COL OPTIONS GRID */
.rc-2col { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; margin-bottom: 26px; }
.rc-opt {
  background: var(--offwhite);
  border: 1px solid var(--lightgray);
  border-radius: 14px;
  padding: 18px;
  transition: border-color 0.2s, box-shadow 0.2s;
}
.rc-opt:hover { border-color: var(--yellow); box-shadow: 0 2px 12px rgba(255,215,6,0.2); }
.rc-oicon { font-size: 22px; margin-bottom: 8px; }
.rc-opt h4 { font-size: 0.92rem; font-weight: 700; margin-bottom: 5px; color: var(--offblack); }
.rc-opt p  { font-size: 0.82rem; color: var(--gray); line-height: 1.5; margin: 0; }
.rc-tag {
  display: inline-block;
  margin-top: 10px;
  padding: 3px 10px;
  border-radius: 20px;
  font-size: 11px;
  font-weight: 700;
  background: var(--offblack);
  color: var(--yellow);
}

/* 3-COL WHAT-IS GRID */
.rc-3col { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 14px; margin-bottom: 24px; }
.rc-wi {
  background: var(--offwhite);
  border-radius: 14px;
  padding: 20px;
  border: 1px solid var(--lightgray);
  text-align: center;
}
.rc-wi-icon { font-size: 30px; margin-bottom: 10px; }
.rc-wi h4 { font-size: 0.88rem; font-weight: 700; margin-bottom: 5px; color: var(--offblack); }
.rc-wi p  { font-size: 0.80rem; color: var(--gray); line-height: 1.5; margin: 0; }

/* JOURNEY */
.rc-journey { display: flex; overflow-x: auto; padding-bottom: 8px; margin-bottom: 0; }
.rc-jstep  { flex: 1; min-width: 100px; text-align: center; position: relative; }
.rc-jstep::after { content: '→'; position: absolute; right: -12px; top: 10px; font-size: 18px; color: var(--lightgray); }
.rc-jstep:last-child::after { display: none; }
.rc-jdot {
  width: 38px; height: 38px; border-radius: 50%;
  background: var(--offblack); color: var(--yellow);
  font-size: 14px; display: flex; align-items: center; justify-content: center;
  margin: 0 auto 6px;
}
.rc-jlbl { font-size: 0.72rem; font-weight: 700; color: var(--darkgray); }

/* GENERIC CARD */
.rc-card {
  background: var(--offwhite);
  border-radius: 16px;
  padding: 28px;
  border: 1px solid var(--lightgray);
  margin-bottom: 24px;
}

/* COMPLETE BANNER */
.rc-complete {
  background: var(--offblack);
  border-radius: 16px;
  padding: 40px;
  text-align: center;
  margin-bottom: 28px;
  color: white;
}
.rc-complete h2 { font-size: 1.8rem; font-weight: 800; margin: 12px 0 10px; color: var(--yellow); }
.rc-complete p  { color: var(--lightgray); font-size: 0.95rem; margin: 0; }

/* SUBHEADING */
.rc-subhead { font-size: 1rem; font-weight: 700; margin-bottom: 16px; color: var(--offblack); }

/* LINK BUTTONS */
.rc-link-btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: var(--yellow);
  color: var(--offblack);
  text-decoration: none;
  padding: 11px 22px;
  border-radius: 10px;
  font-weight: 700;
  font-size: 0.88rem;
  transition: opacity 0.2s;
  margin-bottom: 8px;
  margin-right: 8px;
}
.rc-link-btn:hover { opacity: 0.85; text-decoration: none; }
.rc-link-sec {
  background: var(--offwhite);
  color: var(--darkgray);
  border: 1px solid var(--lightgray);
}
.rc-link-sec:hover { background: var(--brightgray); }

/* RESPONSIVE */
@media (max-width: 640px) {
  .rc-hero h1 { font-size: 1.7rem; }
  .rc-2col, .rc-3col { grid-template-columns: 1fr; }
  .rc-hero-stats { gap: 20px; }
  .rc-sec-header { flex-direction: column; gap: 12px; }
  .rc-hero { padding: 36px 20px 32px; }
  .rc-toc-grid { grid-template-columns: 1fr 1fr; }
  .rc-video-card { flex-direction: column; padding: 24px; }
}
</style>
`}</HTMLBlock>


  </Tab>

  <Tab title="Second Tab">
    Here's content that's only inside the second Tab.
  </Tab>

  <Tab title="Third Tab">
    Here's content that's only inside the third Tab.
  </Tab>
</Tabs>
