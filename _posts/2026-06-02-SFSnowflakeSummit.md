---
layout: conference
title: ''
date: 2026-03-17
tags:
  - Blog
  - Post
  - Tag
---


<iframe id="snowframe-srcdoc" style="width:100%;height:900px;border:0;" title="Snowflake Summit 2026"></iframe>

<script>
  fetch('{{ "/assets/images/etc/Snowflake Summit 2026 Webpage.html" | relative_url }}')
    .then(r => r.text())
    .then(html => {
      // Insert remote HTML into the iframe using srcdoc
      document.getElementById('snowframe-srcdoc').srcdoc = html;
    })
    .catch(err => {
      console.error('Could not load Snowflake page:', err);
      // fallback link
      document.getElementById('snowframe-srcdoc').outerHTML =
        '<p>Unable to embed page. <a href="{{ \'/assets/images/etc/Snowflake Summit 2026 Webpage.html\' | relative_url }}">Open in new tab</a></p>';
    });
</script>

## Section 1
