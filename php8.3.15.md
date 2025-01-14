## PHP 8.3.15
   VS16 x86 Non Thread Safe (2024-Dec-17 19:25:00)

1. install php
   https://windows.php.net/downloads/releases/php-8.3.15-nts-Win32-vs16-x86.zip
2. install xdebug
   https://xdebug.org/files/php_xdebug-3.4.1-8.3-nts-vs16-x86_64.dll

## Config php.ini
1. open extension
   ```
   extension_dir = "ext"

   extension=curl
   extension=fileinfo
   extension=gd
   extension=mbstring
   extension=mysqli
   extension=openssl
   extension=pdo_mysql

   extension=php_sqlsrv_83_nts_x64.dll
   extension=php_pdo_sqlsrv_83_nts_x64.dll

   [curl]
   ; A default value for the CURLOPT_CAINFO option. This is required to be an
   ; absolute path.
   ;curl.cainfo =
   curl.cainfo = "D:\xampp\php-8.3.15\extras\ssl\cacert.pem"
   ``` 
2. config xdebug
   ```
   [Xdebug]
   #https://www.youtube.com/watch?v=3nCfRxuGtv4
   zend_extension="D:\xampp\php-8.3.15\ext\php_xdebug-3.4.1-8.3-nts-vs16-x86_64.dll"
   xdebug.mode=debug
   xdebug.start_with_request=yes
   xdebug.client_port=9001
   #xdebug.remote_port=9001
   xdebug.log="D:\xampp\php-8.3.15\logs\x-debug.log"
   xdebug.log_level=7
   xdebug.idekey=VSCODE
   xdebug.client_host="127.0.0.1"
   ```

