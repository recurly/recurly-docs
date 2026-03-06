---
title: Commerce Experiment 2
deprecated: false
hidden: false
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
.tab-container {
  font-family: system-ui, sans-serif;
}

/* Hide all tab panels by default */
.tab-panel {
  display: none;
  padding: 24px;
  border: 1px solid #ddd;
  border-top: none;
}

/* Show tab when targeted */
.tab-panel:target {
  display: block;
}

/* Default visible tab */
.tab-panel:first-of-type {
  display: block;
}

/* Tab buttons */
.tab-nav {
  display: flex;
  gap: 8px;
  border-bottom: 1px solid #ddd;
}

.tab-nav a {
  padding: 10px 16px;
  text-decoration: none;
  border: 1px solid #ddd;
  border-bottom: none;
  background: #f7f7f7;
  border-radius: 6px 6px 0 0;
  font-weight: 600;
  color: #333;
}

.tab-nav a:hover {
  background: #fff;
}
</style>


<div class="tab-container">

<div class="tab-nav">
<a href="#tab1">First Tab</a>
<a href="#tab2">Second Tab</a>
<a href="#tab3">Third Tab</a>
</div>


<div id="tab1" class="tab-panel">
<h3>First Tab</h3>

<p>Welcome to the content that you can only see inside the first Tab.</p>

<a href="#tab2">Next: Second Tab →</a>
</div>


<div id="tab2" class="tab-panel">
<h3>Second Tab</h3>

<p>Here's content that's only inside the second Tab.</p>

<a href="#tab1">← Back</a>
<a href="#tab3">Next: Third Tab →</a>
</div>


<div id="tab3" class="tab-panel">
<h3>Third Tab</h3>

<p>Here's content that's only inside the third Tab.</p>

<a href="#tab2">← Back</a>
</div>


</div>
`}</HTMLBlock>

<br />
