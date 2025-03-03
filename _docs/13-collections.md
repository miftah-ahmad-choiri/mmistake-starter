---
title: "Working with Collections"
permalink: /docs/collections/
excerpt: "Suggestions and Front Matter defaults for working with collections."
last_modified_at: 2018-03-20T16:00:02-04:00
---

Collections like posts and pages work as you'd expect. If you're new to them be sure to read [Jekyll's documentation](https://jekyllrb.com/docs/collections/).

The theme has been built with collections in mind and you will find [several examples]({{ "/collection-archive/" | relative_url }}) on the demo site ([portfolio]({{ "/portfolio/" | relative_url }}), [recipes]({{ "/recipes/" | relative_url }}), [pets]({{ "/pets/" | relative_url }})). 

**Collections in the Wild:** This set of documentation is also [built as a collection](https://github.com/{{ site.repository }}/blob/master/docs/_docs/) if you're looking for a fully fleshed out example to inspect.
{: .notice--info}

---

A popular use case for collections is to build a portfolio section as part of one's personal site. Let's quickly walk through the steps to do that.

**Step 1:** Configure the portfolio collection by adding the following to `_config.yml`.

```yaml
collections:
  portfolio:
    output: true
    permalink: /:collection/:path/
```

These settings essentially say output `index.html` files for each portfolio document in `_portfolio` at `_site/portfolio/<document-filename>/`.

Just like posts and pages you'll probably want to set some defaults for the Front Matter:

```yaml
defaults:
  # _portfolio
  - scope:
      path: ""
      type: portfolio
    values:
      layout: single
      author_profile: false
      share: true
```

Now make a portfolio.md file in the '_pages' folder.

```yaml
---
title: Portfolio
layout: collection
permalink: /portfolio/
collection: portfolio
entries_layout: grid
classes: wide
---
```

And then create portfolio content like [`_portfolio/foo-bar-website.md`](https://github.com/{{ site.repository }}/blob/master/docs/_portfolio/foo-bar-website.md), to end up with something like this.

![portfolio collection example]({{ "/assets/images/mm-portfolio-collection-example.jpg" | relative_url }})


<!-- Scroll to Top Button -->
<button onclick="scrollToTop()" id="scrollToTopBtn" title="Go to top">![Go to Top](image.png)</button>

<style>
  /* Style for the button */
  #scrollToTopBtn {
    display: none; /* Hidden by default */
    position: fixed; /* Fixed/sticky position */
    bottom: 20px; /* Place the button at the bottom of the page */
    right: 60px; /* Place the button 20px from the right */
    z-index: 99; /* Make sure it does not overlap */
    border: none; /* Remove borders */
    outline: none; /* Remove outline */
    background-color: #555; /* Set a background color */
    color: white; /* Text color */
    cursor: pointer; /* Add a mouse pointer on hover */
    padding: 15px; /* Some padding */
    border-radius: 10px; /* Rounded corners */
    font-size: 15px; /* Increase font size */
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
      btn.style.display = "block";
    } else {
      btn.style.display = "none";
    }
  };

  // Scroll to top function
  function scrollToTop() {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }
</script>