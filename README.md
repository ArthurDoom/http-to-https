# http-to-https
Redirect http to https from the htaccess on Wordpress installs

## htaccess file (.htaccess)

```html
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteBase /

RewriteCond %{HTTPS} !=on
RewriteRule ^ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]

# BEGIN WordPress
RewriteRule ^index\.php$ - [L]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule . /index.php [L]
</IfModule>
```
