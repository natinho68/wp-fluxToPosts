# JSON Feed wp-posts importer

A posts importer based on a JSON stream. <br>
Posts generation by form and handle an automation system. <br><br>
Thanks to this tutorial [Creating Custom WordPress Administration Pages](https://code.tutsplus.com/tutorials/creating-custom-admin-pages-in-wordpress-1--cms-26829) and to [Easy WordPress Admin Notifications](https://github.com/JolekPress/Easy-WordPress-Admin-Notifications), which helped me a lot for the creation of this plugin

## Getting Started

* Local server environment or live server

### Prerequisites

* Tested on WP 4.9.7

* Your Feed must be a JSON, and formatted like this below 
```json
{
   "items": [
      {
         "pubdate": "Thu, 21 Dec 2000 16:01:07 +0000",
         "description": "Your content (html is ok)1",
         "title": "Title1"
      },
      {
         "pubdate": "Thu, 21 Dec 2000 16:01:07 +0000",
         "description": "Your content (html is ok)2",
         "title": "Title2"
      }
   ]
}
```

I do not know if it will work on previous or higher versions

### Installing



* Clone or download the repository, and put files into **/wp-content/plugins/**

```html
https://github.com/natinho68/wp-FeedToPosts.git
```

* Activate the plugin
* Go to the Feed to posts page in the admin menu
* Put a feed and click on "Generate Posts"
* Your posts have been imported

### Automation

**Please note that for automation, you must first inject posts via the form in the settings of the plugin. Once done, you are free to do automation as explained below.**

If you want to check that new posts are available in your feed, add a cron job like this (here every 5 minutes) :
```
*/5 * * * * wget http://YOURDOMAIN.DOMAIN/?rest_route=/FeedToPosts/v1/feedtoposts
```
If you want simple authentication, add a *.htaccess* require_auth and *.htpasswd* pair, for this url. Just add ```--user user --password pass``` to your cron job.

## Author

[**Nathan MEYER**](https://github.com/natinho68)
