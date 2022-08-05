# Swetrix to Wordpress integration
After you sign up on Swetrix and create a new project, the only thing left is to add it to your website.
If you're curious what data the tracking script collects, open our [documentation](https://swetrix.com/docs#docs-tv) and read the `API -> trackViews` section.

## Installation
1. Log in to your Wordpress account.
2. Install a plugin for adding the code to your HTML, for instance the [Insert Headers and Footers plugin](https://wordpress.org/plugins/insert-headers-and-footers/?ref=swetrix.com).
3. Open up your project, go to the `Project Settings > Custom Code` section:

4. To the `Scripts in Header` section you need to add the following:
```html
<script src="https://swetrix.org/swetrix.js" defer></script>
```

5. In the `Scripts in Footer` section you need to add the following:
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

**Do not forget to update YOUR_PROJECT_ID to your actual project id!**

## Check your installation
After installing Swetrix tracking script, go to your website and visit some pages.\
Within a minute you should be able to see new pageviews being added to your project's dahsboard.
