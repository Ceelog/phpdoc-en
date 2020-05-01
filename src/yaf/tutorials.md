Examples
========

**Example \#1 A classic Application directory layout**

    - index.php 
    - .htaccess 
    + conf
      |- application.ini //application config
    - application/
      - Bootstrap.php   
      + controllers
         - Index.php //default controller
      + views    
         |+ index   
            - index.phtml //view template for default action
      + modules 
      - library
      - models  
      - plugins 

**Example \#2 Entry**

index.php in the top directory is the only way in of the application,
you should rewrite all request to it. (You can use .htaccess in Apache +
php\_mod)

``` php
<?php
define("APPLICATION_PATH",  dirname(__FILE__));

$app  = new Yaf_Application(APPLICATION_PATH . "/conf/application.ini");
$app->bootstrap() //call bootstrap methods defined in Bootstrap.php
 ->run();
?>
```

**Example \#3 Rewrite rule**

    #for apache (.htaccess)
    RewriteEngine On
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule .* index.php

    #for nginx
    server {
      listen ****;
      server_name  domain.com;
      root   document_root;
      index  index.php index.html index.htm;

      if (!-e $request_filename) {
        rewrite ^/(.*)  /index.php/$1 last;
      }
    }

    #for lighttpd
    $HTTP["host"] =~ "(www.)?domain.com$" {
      url.rewrite = (
         "^/(.+)/?$"  => "/index.php/$1",
      )
    }

**Example \#4 Application config**

``` ini
[yaf]
;APPLICATION_PATH is the constant defined in index.php
application.directory=APPLICATION_PATH "/application/" 

;product section inherit from yaf section
[product:yaf]
foo=bar
```

**Example \#5 Default controller**

``` php
<?php
class IndexController extends Yaf_Controller_Abstract {
   /* default action */
   public function indexAction() {
       $this->_view->word = "hello world";
       //or
       // $this->getView()->word = "hello world";
   }
}
?>
```

**Example \#6 Default view template**

``` php
<html>
 <head>
   <title>Hello World</title>
 </head>
 <body>
   <?php echo $word;?>
 </body>
</html>
```

**Example \#7 Run the Application**

The above example will output something similar to:

    <html>
     <head>
       <title>Hello World</title>
     </head>
     <body>
       hello world
     </body>
    </html>

> **Note**:
>
> you can also generate above example by use Yaf codes generator, which
> could be found here yaf@github.
