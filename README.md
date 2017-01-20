# Maintenance Mode

Use this repo to facilitate creation of a custom page that serves as a maintenance page for you site in Apache. It uses .htaccess to let Apache know to return a 503 error and load a custom html page inside the same directory.

### File placement

Add the files in this repo to the root of you site via FTP. Add a custom logo.png and full viewport image so you replace the default unplash.com and placehold.it images.

### Custom HTML

The custom index.html should be changed to 503.html, maintenance.html or even 503.php to avoid conflicts with actual index.html page for the site. This repo uses index.html to add site to GitHub pages.

### Exclude IP Addresses

To allow IP addresses to access site even in maintenance mode uncomment the code below:

```shell
RewriteCond %{REMOTE_ADDR} !^xxx.xxx.xxx.xxx$
```

You can find your own IP address by typing "My IP address" in Google. 

### Skip Crawling

To tell search engine to skip crawling your site while in maintenance mode uncomment the code below:

```shell
Header always set Retry-After "3600"
```

You can replace the numbers with any multiple of 60 but keep in mind that it is in seconds. For example 1 week is 604800 and so on.

### Additional Code

Check my [maintenance mode gist](https://gist.github.com/ar-to/55d4a639dc9ab60b9b5a150515720267) for more options in setting up this page. 