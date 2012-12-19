grc-mysql
====================
Config file for grc to colorize linux console mysql client output

How to use it
-------------
1. Install grc:
   - for debian: `apt-get install grc`
   - for redhat: install from tar.gz at http://kassiopeia.juls.savba.sk/%7Egarabik/software/grc/

2. Copy conf.mysql to /user/share/grc/

3. Add the following lines to your /etc/grc.conf file:
`# mysql tools`
`(^|[/\w\.]+/)mysql`
`conf.mysql`

4. Add the following lines to your /etc/my.cnf file under the `[mysql]` section (create `[mysql]` section if one does not exist)
`pager  = grcat /usr/share/conf.mysql`

5. Run mysql client `mysql -u <user> -p -h <hostname>`

6. Perform a query to view the colourised output!

How does it work
----------------
Mysql client supports using predefined pager for data output.
So we can set grcat (Generic Colouriser) for processing mysql output.
grcat reads supplied config file, parces output according to regular expression and adds colours.

The grc manual can be founded via `man grc` or here: http://kassiopeia.juls.savba.sk/~garabik/software/grc/README.txt

Sample screenshots
------------------

![Table screenshot](https://raw.github.com/nitso/colour-mysql-console/master/Screen_table.png)
![Vertical screenshot](https://raw.github.com/nitso/colour-mysql-console/master/Screen_G.png)
