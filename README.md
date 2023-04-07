phpssdbadmin
============

### PHP module dependencies

- php-gd
- php-mcrypt
- php-openssl

## Install

Edit `app/config/config.php`:

    'servers' => array(
    	array(
    		'host' => '127.0.0.1',
    		'port' => '8888',
    	),
    ),

modify `host` and `port` to the correct value.

Then edit your Nginx configuration file, Add a URL rewriting rule:

    location /phpssdbadmin {
    	try_files $uri $uri/ /phpssdbadmin/index.php?$args;
    }

**Note: If you haven't configured php yet, please configure php first! Here is an example , but it is not guaranteed that you can fully understand. If you can’t understand, please learn how to configure nginx+php on the search engine, thank you!**

    index index.php;
    root /somewhere/htdocs
    location ~ \.php$ {
    	include fastcgi_params;
    	fastcgi_pass 127.0.0.1:9000;
    	fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
    }

If you are using Apache, you can try this URL rewriting rule.

    RewriteEngine On
    RewriteBase /phpssdbadmin/
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule . /phpssdbadmin/index.php [L]

# phpssdbadmin

SSDB Admin Tool Built with PHP.

### PHP module dependency

- php-gd
- php-mcrypt
- php-openssl

## Install

Edit `app/config/config.conf`:

    'servers' => array(
    	array(
    		'host' => '127.0.0.1',
    		'port' => '8888',
    	),
    ),

Change `host` and `port` to the right values.

Then edit your Nginx configuration, add one URL rewrite rule as:

    location /phpssdbadmin {
    	try_files $uri $uri/ /phpssdbadmin/index.php?$args;
    }

**Your have to set up nginx+php first!**

    index index.php;
    root /somewhere/htdocs
    location ~ \.php$ {
    	include        fastcgi_params;
    	fastcgi_pass   127.0.0.1:9000;
    	fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
    }

If you are using Apache, try this URL rewrite rule:

    RewriteEngine On
    RewriteBase /phpssdbadmin/
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule . /phpssdbadmin/index.php [L]

## Screenshots

![](./imgs/phpssdbadmin-index.png)

![](./imgs/phpssdbadmin-hash.png)
