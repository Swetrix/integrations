# Swetrix to Ghost integration
After you sign up on Swetrix and create a new project, the only thing left is to add it to your website.
If you're curious what data the tracking script collects, open our [documentation](https://swetrix.com/docs#docs-tv) and read the `API -> trackViews` section.

## Installation
1. Log in to your Ghost admin account.
2. Open `Settings`, go to the `Code Injection` section.

3. To the `Site Header` section you need to add the following:
```html
<script src="https://swetrix.org/swetrix.js" defer></script>
```

5. In the `Site Footer` section you need to add the following:
```html
<script>
  document.addEventListener('DOMContentLoaded', function () {
    swetrix.init('YOUR_PROJECT_ID')
    swetrix.trackViews()
})
</script>

<noscript>
  <img src="https://api.swetrix.com/log/noscript?pid=YOUR_PROJECT_ID" alt="" referrerpolicy="no-referrer-when-downgrade" />
</noscript>
```

**Do not forget to change YOUR_PROJECT_ID to your actual project id!**

## Check your installation
After installing Swetrix tracking script, go to your website and visit some pages.\
Within a minute you should be able to see new pageviews being added to your project's dahsboard.
