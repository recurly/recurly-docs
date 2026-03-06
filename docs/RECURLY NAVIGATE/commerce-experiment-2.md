---
title: Commerce Experiment 2
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
:root {
  --yellow:#FFD706;
  --offblack:#0D0D0B;
  --darkgray:#32312D;
  --lightgray:#CCC9B8;
}

/* Reset */
*{box-sizing:border-box;margin:0;padding:0;}
body{font-family:'Segoe UI',system-ui,sans-serif;}

/* NAV */
.rc-nav{
display:flex;
flex-wrap:wrap;
gap:10px;
margin:24px 0 28px;
}

.rc-nav a{
display:inline-flex;
align-items:center;
gap:8px;
padding:10px 14px;
border-radius:12px;
border:1px solid var(--lightgray);
background:white;
color:var(--darkgray);
text-decoration:none;
font-size:0.88rem;
font-weight:700;
transition:border-color .2s,box-shadow .2s;
}

.rc-nav a:hover{
border-color:var(--yellow);
box-shadow:0 2px 8px rgba(255,215,6,0.2);
color:var(--offblack);
}

.rc-snum{
display:inline-flex;
align-items:center;
justify-content:center;
width:24px;
height:24px;
border-radius:50%;
background:var(--offblack);
color:var(--yellow);
font-size:12px;
font-weight:700;
flex-shrink:0;
}

/* TAB PANELS */

.rc-panel{
display:none;
padding:28px;
border:1px solid var(--lightgray);
border-radius:14px;
}

/* show targeted tab */

.rc-panel:target{
display:block;
}

/* default tab */

.rc-panel:first-of-type{
display:block;
}

/* buttons */

.rc-btn{
display:inline-block;
margin-top:20px;
padding:10px 16px;
border-radius:10px;
background:var(--yellow);
color:var(--offblack);
font-weight:700;
text-decoration:none;
}

/* mobile */

@media(max-width:640px){
.rc-nav{flex-direction:column;}
}
</style>


<nav class="rc-nav">

<a href="#rcSec0"><span class="rc-snum">1</span>Intro</a>
<a href="#rcSec1"><span class="rc-snum">2</span>Plans</a>
<a href="#rcSec2"><span class="rc-snum">3</span>Storefront</a>
<a href="#rcSec3"><span class="rc-snum">4</span>Portal</a>
<a href="#rcSec4"><span class="rc-snum">5</span>Notifications</a>
<a href="#rcSec5"><span class="rc-snum">6</span>Integrations</a>
<a href="#rcSec6"><span class="rc-snum">✓</span>Launch!</a>

</nav>



<div id="rcSec0" class="rc-panel">

<h2>Intro</h2>

<p>Welcome to Recurly Commerce onboarding.</p>

<a class="rc-btn" href="#rcSec1">Next: Subscription Plans →</a>

</div>



<div id="rcSec1" class="rc-panel">

<h2>Subscription Plans</h2>

<p>Create your subscription plans.</p>

<a class="rc-btn" href="#rcSec0">← Intro</a>
<a class="rc-btn" href="#rcSec2">Next: Storefront →</a>

</div>



<div id="rcSec2" class="rc-panel">

<h2>Storefront Setup</h2>

<p>Configure the storefront widget.</p>

<a class="rc-btn" href="#rcSec1">← Plans</a>
<a class="rc-btn" href="#rcSec3">Next: Portal →</a>

</div>



<div id="rcSec3" class="rc-panel">

<h2>Customer Portal</h2>

<p>Configure subscriber self-service.</p>

<a class="rc-btn" href="#rcSec2">← Storefront</a>
<a class="rc-btn" href="#rcSec4">Next: Notifications →</a>

</div>



<div id="rcSec4" class="rc-panel">

<h2>Notifications</h2>

<p>Configure subscriber notifications.</p>

<a class="rc-btn" href="#rcSec3">← Portal</a>
<a class="rc-btn" href="#rcSec5">Next: Integrations →</a>

</div>



<div id="rcSec5" class="rc-panel">

<h2>Integrations</h2>

<p>Connect marketing and support tools.</p>

<a class="rc-btn" href="#rcSec4">← Notifications</a>
<a class="rc-btn" href="#rcSec6">Next: Launch →</a>

</div>



<div id="rcSec6" class="rc-panel">

<h2>Launch!</h2>

<p>You are ready to launch.</p>

<a class="rc-btn" href="#rcSec5">← Integrations</a>

</div>
`}</HTMLBlock>

<br />