Currently just hosting my personal website. Would be relatively easy to spin up other websites.

PHP needed to be installed, as well as php's curl support for letterboxd project and sqlite for stocks website.

.htaccess contains environment variables for api keys and phpliteadmin password.

Also blocks db file from being downloaded. Had to add rule to base 000-default.conf
to get apache to read .htaccess files as it was overwritten by a higher up rule:

```
        <Directory /var/www/personal-website>
                Options Indexes FollowSymLinks
                AllowOverride All
                Require all granted
        </Directory>
```

## Todo
- Setup Cloudflare tunneling to route to web server without opening ports on router