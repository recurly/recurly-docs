---
title: Recurly Subscriptions Changelog
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
  #hub-sidebar, #reference-sidebar, .rm-Sidebar {
    font-family: var(--recurly-font) !important;
    background: #fff !important;
    display: none;
}
.rm-Guides #content-head {
    display: none;
    border-bottom: 0;
    padding-bottom: 0;
    margin: 0 auto;
    width: 120%;
}
  #recurly-changelog-header {
    background: #080807;
    border-radius: 22px;
    padding: 66px 72px 58px !important;
    margin: 42px 0 34px;
    color: #d6d1c6;
    box-sizing: border-box;
  }

  #recurly-changelog-header h1 {
    color: #ffd400;
    font-size: 48px;
    line-height: 1.15;
    font-weight: 800;
    margin: 0 0 28px;
    letter-spacing: -0.02em;
  }

  #recurly-changelog-header > p:not(.rss-line) {
    color: #d6d1c6;
    font-size: 30px;
    line-height: 1.55;
    font-weight: 400;
    margin: 0;
    max-width: 1720px;
  }

  #recurly-changelog-header .rss-line {
    border-top: 1px solid #32312d;
    margin: 32px 0 0;
    padding-top: 32px;
    color: #d6d1c6;
    font-size: 27px;
    line-height: 1.45;
    font-weight: 400;
    display: flex;
    align-items: center;
    gap: 18px;
  }

  #recurly-changelog-header .rss-icon {
    color: #ffd400;
    font-size: 27px;
    line-height: 1;
    flex: 0 0 auto;
  }

  #recurly-changelog-header .rss-copy {
    appearance: none;
    background: transparent;
    border: 0;
    padding: 0;
    margin: 0 8px;
    color: #ffd400;
    font: inherit;
    font-weight: 800;
    line-height: inherit;
    text-decoration: underline;
    text-underline-offset: 6px;
    text-decoration-thickness: 2px;
    cursor: pointer;
  }

  #recurly-changelog-header .rss-copy:hover,
  #recurly-changelog-header .rss-copy:focus {
    color: #ffe45c;
  }

  @media (max-width: 768px) {
    #recurly-changelog-header {
      border-radius: 18px;
      padding: 36px 28px 32px !important;
      margin: 28px 0;
    }

    #recurly-changelog-header h1 {
      font-size: 34px;
      margin-bottom: 20px;
    }

    #recurly-changelog-header > p:not(.rss-line),
    #recurly-changelog-header .rss-line {
      font-size: 20px;
    }

    #recurly-changelog-header .rss-line {
      align-items: flex-start;
      gap: 12px;
    }

    #recurly-changelog-header .rss-icon {
      font-size: 22px;
      margin-top: 4px;
    }
  }
</style>

<div id="recurly-changelog-header" class="rm-Markdown markdown-body">
  <h1>Recurly RevRec Changelog</h1>

  <p>
    Discover what's new in Recurly Subscriptions Management. Browse posts by year to see recent launches,
    enhancements, and behind-the-scenes improvements that keep your platform sharp.
  </p>

  <p class="rss-line">
    <i class="fa fa-rss rss-icon" aria-hidden="true"></i>
    <span>
      Stay in the loop — copy our
      <button
        type="button"
        class="rss-copy"
        data-url="https://docs.recurly.com/recurly-revrec/changelog.rss"
      >RSS feed URL</button>
      and paste it into your favorite RSS reader to get every update the moment it ships.
    </span>
  </p>
</div>
`}</HTMLBlock>

<RecurlyChangelogMount
  rssUrl="https://docs.recurly.com/recurly-subscriptions/changelog.rss"
  product="Subscriptions"
  itemsPerPage={25}
  cacheMinutes={0}
  showSearch={true}
  showFeatureFilter={true}
  showImpactFilter={true}
  showDateFilter={true}
  showItemsPerPageDropdown={true}
/>

<HTMLBlock>{`
<style>
.content-toc {
    display: none;
  }
:where(.ThemeContext_spacing_legacy) .rm-Guides .content-body {
    max-width: 100%;
    width: 100%;
}
</style> 
`}</HTMLBlock>

<br />
