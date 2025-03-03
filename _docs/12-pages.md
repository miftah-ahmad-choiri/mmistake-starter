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

Test2 

<!-- Scroll to Top Button -->
<button onclick="scrollToTop()" id="scrollToTopBtn" title="Go to top">
  &#8679;
</button>

<style>
  /* Style for the button */
  #scrollToTopBtn {
    display: none; /* Hidden by default */
    position: fixed; /* Fixed/sticky position */
    bottom: 20px; /* Place the button at the bottom of the page */
    right: 20px; /* Place the button 20px from the right */
    z-index: 99; /* Make sure it does not overlap */
    border: none; /* Remove borders */
    outline: none; /* Remove outline */
    background-color: #555; /* Set a background color */
    color: white; /* Text color */
    cursor: pointer; /* Add a mouse pointer on hover */
    width: 50px; /* Set width */
    height: 50px; /* Set height */
    border-radius: 50%; /* Make it circular */
    font-size: 24px; /* Increase font size */
    display: flex;
    justify-content: center;
    align-items: center;
  }
  #scrollToTopBtn:hover {
    background-color: #333; /* Darker background on hover */
  }
</style>

<script defer>
  // Show the button when scrolling down
  window.onscroll = function() {
    let btn = document.getElementById("scrollToTopBtn");
    if (document.body.scrollTop > 20 || document.documentElement.scrollTop > 20) {
      btn.style.display = "flex";
    } else {
      btn.style.display = "none";
    }
  };

  // Scroll to top function
  function scrollToTop() {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }
</script>
