# virtualmin

#### wordpress.pl
Virtualmin install script for installing WordPress.
* Please read the [related post](https://kallelilja.com/2017/07/how-to-install-wordpress-on-virtualmin/) for more information.

## Fail2Ban
* Please read the [related post](https://kallelilja.com/2017/07/protect-wordpress-site-xmlrpc-php-attacks/) for more information.
```
tail -f /var/log/fail2ban.log
```
```
fail2ban-client status | grep "Jail list:" | sed "s/ //g" | awk '{split($2,a,",");for(i in a) system("fail2ban-client status " a[i])}' | grep "Status\|IP list"
```
#### filter.d/apache-xmlrpc.conf
Filter to detect /xmlrps.php attacks.
#### filter.d/wp-login.conf
Filter to detect /wp-login.php attacks.
#### action.d/apache-xmlrpc.conf
Action to protect against /xmlrps.php attacks.
#### action.d/wp-login.conf
Action to protect against /wp-login.php attacks.
#### jail.conf
Fail2Ban Jail configuration.
#### disable-xmlrpc-php
Add to bottom of .htaccess.
