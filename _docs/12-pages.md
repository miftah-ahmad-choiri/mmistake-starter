---
title: "Working with Pages"
permalink: /docs/pages/
excerpt: "Suggestions and Front Matter defaults for working with pages."
last_modified_at: 2016-11-03T11:13:12-04:00
---

To better organize all of your pages you can centralize them into a single location similar to posts and collections.

**Step 1:** Start by placing pages (`.md` or `.html` files) into a `_pages` directory. Meaningfully naming files should be the goal. Avoid patterns like `/about/index.md` as it makes distinguishing between multiple `index.md` files harder.

```bash
sample-project
└── _pages/
    ├── 404.md               # custom 404 page
    ├── about.md             # about page
    └── contact.md           # contact page
```

**Step 2:** Include pages to be sure Jekyll "sees" and processes the files inside of `_pages`. Add `include: ["_pages"]` to `_config.yml`.

**Step 3:** Assign permalink overrides in the YAML Front Matter of each.

Examples:

| filename            | permalink              |
| --------            | ---------              |
| _pages/about.md     | `permalink: /about/`   |
| _pages/home.md      | `permalink: /`         |
| _pages/contact.md   | `permalink: /contact/` |

**Recommended Front Matter Defaults:**

```yaml
defaults:
  # _pages
  - scope:
      path: ""
      type: pages
    values:
      layout: single
      author_profile: true
```

<!-- Scroll to Top Button -->
<button onclick="scrollToTop()" id="scrollToTopBtn" title="Go to top">Top</button>

<style> /* Style for the button */ #scrollToTopBtn { display: none; /* Hidden by default */ position: fixed; /* Fixed/sticky position */ bottom: 20px; /* Place the button at the bottom of the page */ right: 20px; /* Place the button 20px from the right */ z-index: 99; /* Make sure it does not overlap */ border: none; /* Remove borders */ outline: none; /* Remove outline */ background-color: #555; /* Set a background color */ color: white; /* Text color */ cursor: pointer; /* Add a mouse pointer on hover */ padding: 15px; /* Some padding */ border-radius: 10px; /* Rounded corners */ font-size: 18px; /* Increase font size */ } #scrollToTopBtn:hover { background-color: #333; /* Darker background on hover */ } </style><script> // When the user scrolls down 20px from the top of the document, show the button window.onscroll = function() {scrollFunction()}; function scrollFunction() { if (document.body.scrollTop > 20 || document.documentElement.scrollTop > 20) { document.getElementById("scrollToTopBtn").style.display = "block"; } else { document.getElementById("scrollToTopBtn").style.display = "none"; } } // When the user clicks on the button, scroll to the top of the document function scrollToTop() { document.body.scrollTop = 0; // For Safari document.documentElement.scrollTop = 0; // For Chrome, Firefox, IE and Opera } </script>