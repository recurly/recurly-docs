---
title: 'Welcome to Navigate: Getting started'
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
/* BOTTOM CONTEXT (Flywheel & Info) */
.rc-context-wrap{display:grid;grid-template-columns:1fr 1fr;gap:40px;align-items:center;background:var(--offwhite);border:1px solid var(--lightgray);padding:40px;border-radius:16px;margin-bottom:24px;}
.rc-context-info h3{font-size:1.5rem;font-weight:800;margin:0 0 16px;color:var(--offblack);}
.rc-context-info p{font-size:1rem;color:var(--darkgray);line-height:1.7;margin:0 0 16px;}
.rc-flywheel-img{background:var(--offblack);border-radius:16px;padding:24px;display:flex;justify-content:center;}
.rc-flywheel-img img{max-width:100%;height:auto;max-height:300px;}

/* Don't forget these responsive breakpoints for it! */
@media(max-width:900px){
  .rc-context-wrap{grid-template-columns:1fr;}
}
@media(max-width:640px){
  .rc-context-wrap{padding:24px;}
}
`}</HTMLBlock>

<HTMLBlock>{`
<div class="rc-context-wrap">
    <div class="rc-context-info">
      <h3>The Recurly Flywheel</h3>
      <p>Navigate was built to act as your digital Customer Success Manager. Every resource is structured around the four pillars of a healthy subscription business.</p>
      <p>Whether you're exploring Account Updater to fix retention issues or setting up Dunning windows for the first time, Navigate meets you where you are and helps you get to the next level.</p>
    </div>
    <div class="rc-flywheel-img">
      <img src="https://files.readme.io/85e931cea7e5f65844bb1928786a705578636d4a0e6a258be4f0f4a8cb871cac-Recurly-Flywheel.png" alt="Recurly Flywheel — Launch, Acquire, Retain, Scale" />
    </div>
  </div>
`}</HTMLBlock>

<br />
