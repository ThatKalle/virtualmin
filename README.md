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
#### action.d/apache-xmlrpc.conf
#### jail.conf
#### disable-xmlrpc-php
Add to bottom of .htaccess
