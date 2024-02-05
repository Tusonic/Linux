a2enmod rewrite



<VirtualHost *:80>
	
		ServerAdmin admin@serwer.tusonic.pl
		ServerName serwer.tusonic.pl
		ServerAlias www.serwer.tusonic.pl
		DocumentRoot /var/www/html/serwer.tusonic.pl
	
		ErrorLog ${APACHE_LOG_DIR}/serwer.tusonic.pl/error.log
		CustomLog ${APACHE_LOG_DIR}/serwer.tusonic.pl/access.log combined

RewriteEngine on
RewriteCond %{SERVER_NAME} =www.serwer.tusonic.pl [OR]
RewriteCond %{SERVER_NAME} =serwer.tusonic.pl
RewriteRule ^ https://%{SERVER_NAME}%{REQUEST_URI} [END,NE,R=permanent]
	</VirtualHost>

 <IfModule mod_ssl.c>
	<VirtualHost *:443>

                ServerAdmin admin@serwer.tusonic.pl
                ServerName serwer.tusonic.pl
                ServerAlias www.serwer.tusonic.pl
                DocumentRoot /var/www/html/serwer.tusonic.pl
		# SSLEngine on
		 ErrorLog ${APACHE_LOG_DIR}/serwer.tusonic.pl.ssl/error.log
		 CustomLog ${APACHE_LOG_DIR}/serwer.tusonic.pl.ssl/access.log combined

		SSLCertificateFile /etc/letsencrypt/live/serwer.tusonic.pl/fullchain.pem
               SSLCertificateKeyFile /etc/letsencrypt/live/serwer.tusonic.pl/privkey.pem
        #       Include /etc/letsencrypt/options-ssl-apache.conf
        </VirtualHost>
 </IfModule>


