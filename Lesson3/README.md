# Системы управления конфигурациями - Урок 3

## Задание

Установить и настроить Ansible. Результатом работы должен быть вывод Ansible -m setup.

## Результат

- Дополнил ролью common;
- Дополнил открытием http траффика;
- Заменил настройки с порта 443 на 80;
- В роль geerlingguy.php добавил поддержку unix-socket;
- Понизил версию WordPress для поддержки php-5.4 (честно говоря, не хватило свободного времени, чтобы переделывать на запуск php более свежей версии);
- Все приложения установились;
- Лог запуска:
<pre>
$/.../Lesson3$ ansible-playbook wordpress.yml 

PLAY [prod_gb] ****************************************************************************************************************************************************

TASK [Gathering Facts] ********************************************************************************************************************************************
ok: [cos7-server1]

TASK [common : Install packages] **********************************************************************************************************************************
changed: [cos7-server1] => (item=epel-release)

TASK [geerlingguy.nginx : Include OS-specific variables.] *********************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.nginx : Define nginx_user.] *********************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.nginx : include_tasks] **************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.nginx/tasks/setup-RedHat.yml for cos7-server1

TASK [geerlingguy.nginx : Enable nginx repo.] *********************************************************************************************************************
changed: [cos7-server1]

TASK [geerlingguy.nginx : Ensure nginx is installed.] *************************************************************************************************************
changed: [cos7-server1]

TASK [geerlingguy.nginx : include_tasks] **************************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.nginx : include_tasks] **************************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.nginx : include_tasks] **************************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.nginx : include_tasks] **************************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.nginx : include_tasks] **************************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.nginx : Remove default nginx vhost config file (if configured).] ********************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.nginx : Ensure nginx_vhost_path exists.] ********************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.nginx : Add managed vhost config files.] ********************************************************************************************************
changed: [cos7-server1] => (item={'listen': '80', 'server_name': '192.168.0.26', 'root': '/var/www/192.168.0.26/wordpress', 'index': 'index.php index.html index.htm', 'error_page': '500 502 503 504  /50x.html', 'access_log': '/var/log/nginx/192.168.0.26.access.log  main', 'state': 'present', 'template': 'vhost.j2', 'filename': '192.168.0.26.conf', 'extra_parameters': 'location = /50x.html {\n    root   /usr/share/nginx/html;\n}\nlocation ~ \\.php$ {\n    fastcgi_split_path_info ^(.+\\.php)(/.+)$;\n    fastcgi_pass unix:/var/run/php-fpm/php-fpm.sock;\n    fastcgi_index index.php;\n    fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;\n    include fastcgi_params;\n}\n'})

TASK [geerlingguy.nginx : Remove managed vhost config files.] *****************************************************************************************************
skipping: [cos7-server1] => (item={'listen': '80', 'server_name': '192.168.0.26', 'root': '/var/www/192.168.0.26/wordpress', 'index': 'index.php index.html index.htm', 'error_page': '500 502 503 504  /50x.html', 'access_log': '/var/log/nginx/192.168.0.26.access.log  main', 'state': 'present', 'template': 'vhost.j2', 'filename': '192.168.0.26.conf', 'extra_parameters': 'location = /50x.html {\n    root   /usr/share/nginx/html;\n}\nlocation ~ \\.php$ {\n    fastcgi_split_path_info ^(.+\\.php)(/.+)$;\n    fastcgi_pass unix:/var/run/php-fpm/php-fpm.sock;\n    fastcgi_index index.php;\n    fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;\n    include fastcgi_params;\n}\n'}) 

TASK [geerlingguy.nginx : Remove legacy vhosts.conf file.] ********************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.nginx : Copy nginx configuration in place.] *****************************************************************************************************
changed: [cos7-server1]

TASK [geerlingguy.nginx : Ensure nginx service is running as configured.] *****************************************************************************************
changed: [cos7-server1]

TASK [geerlingguy.php : Include distribution and version-specific vars.] ******************************************************************************************

TASK [geerlingguy.php : Set the default PHP version for Debian-based OSes.] ***************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.php : Include OS-specific variables.] ***********************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.php : Define php_packages.] *********************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.php : Define php_webserver_daemon.] *************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.php : Define php_conf_paths.] *******************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.php : Define php_extension_conf_paths.] *********************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.php : Define php_apc_conf_filename.] ************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.php : Define php_opcache_conf_filename (Ubuntu 16.04).] *****************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.php : Define php_opcache_conf_filename.] ********************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.php : Define php_fpm_conf_path.] ****************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.php : include_tasks] ****************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.php/tasks/setup-RedHat.yml for cos7-server1

TASK [geerlingguy.php : Ensure PHP packages are installed.] *******************************************************************************************************
changed: [cos7-server1]

TASK [geerlingguy.php : include_tasks] ****************************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.php : include_tasks] ****************************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.php : include_tasks] ****************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.php/tasks/configure.yml for cos7-server1

TASK [geerlingguy.php : Ensure configuration directories exist.] **************************************************************************************************
ok: [cos7-server1] => (item=/etc)
ok: [cos7-server1] => (item=/etc/php.d)

TASK [geerlingguy.php : Place PHP configuration file in place.] ***************************************************************************************************
changed: [cos7-server1] => (item=/etc)

TASK [geerlingguy.php : include_tasks] ****************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.php/tasks/configure-apcu.yml for cos7-server1

TASK [geerlingguy.php : Check for existing APCu config files.] ****************************************************************************************************
ok: [cos7-server1] => (item=/etc/php.d)

TASK [geerlingguy.php : Remove any non-role-supplied APCu config files.] ******************************************************************************************

TASK [geerlingguy.php : Ensure APCu config file is present.] ******************************************************************************************************
changed: [cos7-server1] => (item=/etc/php.d)

TASK [geerlingguy.php : Remove APCu config file if APC is disabled.] **********************************************************************************************
skipping: [cos7-server1] => (item=/etc/php.d) 

TASK [geerlingguy.php : include_tasks] ****************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.php/tasks/configure-opcache.yml for cos7-server1

TASK [geerlingguy.php : Check for existing OpCache config files.] *************************************************************************************************
ok: [cos7-server1] => (item=/etc/php.d)

TASK [geerlingguy.php : Remove any non-role-supplied OpCache config files.] ***************************************************************************************

TASK [geerlingguy.php : Ensure OpCache config file is present.] ***************************************************************************************************
changed: [cos7-server1] => (item=/etc/php.d)

TASK [geerlingguy.php : Remove OpCache config file if OpCache is disabled.] ***************************************************************************************
skipping: [cos7-server1] => (item=/etc/php.d) 

TASK [geerlingguy.php : include_tasks] ****************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.php/tasks/configure-fpm.yml for cos7-server1

TASK [geerlingguy.php : Define php_fpm_daemon.] *******************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.php : Define php_fpm_pool_conf_path.] ***********************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.php : Define php_fpm_pool_user.] ****************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.php : Define php_fpm_pool_group.] ***************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.php : Stat php_fpm_pool_conf_path] **************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.php : Ensure the default pool directory exists.] ************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.php : Create fpm pools.] ************************************************************************************************************************
changed: [cos7-server1] => (item={'pool_name': 'www', 'pool_template': 'www.conf.j2', 'pool_listen': '127.0.0.1:9000', 'pool_listen_allowed_clients': '127.0.0.1', 'pool_pm': 'dynamic', 'pool_pm_max_children': 50, 'pool_pm_start_servers': 5, 'pool_pm_min_spare_servers': 5, 'pool_pm_max_spare_servers': 5, 'pool_php_fpm_pm_max_requests': 0})

TASK [geerlingguy.php : Ensure php-fpm is started and enabled at boot (if configured).] ***************************************************************************
changed: [cos7-server1]

TASK [geerlingguy.mysql : include_tasks] **************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.mysql/tasks/variables.yml for cos7-server1

TASK [geerlingguy.mysql : Include OS-specific variables.] *********************************************************************************************************
ok: [cos7-server1] => (item=/home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.mysql/vars/RedHat-7.yml)

TASK [geerlingguy.mysql : Define mysql_packages.] *****************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Define mysql_daemon.] *******************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Define mysql_slow_query_log_file.] ******************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Define mysql_log_error.] ****************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Define mysql_syslog_tag.] ***************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Define mysql_pid_file.] *****************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Define mysql_config_file.] **************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Define mysql_config_include_dir.] *******************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Define mysql_socket.] *******************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Define mysql_supports_innodb_large_prefix.] *********************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : include_tasks] **************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.mysql/tasks/setup-RedHat.yml for cos7-server1

TASK [geerlingguy.mysql : Ensure MySQL packages are installed.] ***************************************************************************************************
changed: [cos7-server1]

TASK [geerlingguy.mysql : include_tasks] **************************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : include_tasks] **************************************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : Check if MySQL packages were installed.] ************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : include_tasks] **************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.mysql/tasks/configure.yml for cos7-server1

TASK [geerlingguy.mysql : Get MySQL version.] *********************************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Copy my.cnf global MySQL configuration.] ************************************************************************************************
changed: [cos7-server1]

TASK [geerlingguy.mysql : Verify mysql include directory exists.] *************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : Copy my.cnf override files into include directory.] *************************************************************************************

TASK [geerlingguy.mysql : Create slow query log file (if configured).] ********************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : Create datadir if it does not exist] ****************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Set ownership on slow query log file (if configured).] **********************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : Create error log file (if configured).] *************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : Set ownership on error log file (if configured).] ***************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : Ensure MySQL is started and enabled on boot.] *******************************************************************************************
changed: [cos7-server1]

TASK [geerlingguy.mysql : include_tasks] **************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.mysql/tasks/secure-installation.yml for cos7-server1

TASK [geerlingguy.mysql : Ensure default user is present.] ********************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : Copy user-my.cnf file with password credentials.] ***************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : Disallow root login remotely] ***********************************************************************************************************
ok: [cos7-server1] => (item=DELETE FROM mysql.user WHERE User='root' AND Host NOT IN ('localhost', '127.0.0.1', '::1'))

TASK [geerlingguy.mysql : Get list of hosts for the root user.] ***************************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Update MySQL root password for localhost root account (5.7.x).] *************************************************************************
skipping: [cos7-server1] => (item=127.0.0.1) 
skipping: [cos7-server1] => (item=::1) 
skipping: [cos7-server1] => (item=localhost) 

TASK [geerlingguy.mysql : Update MySQL root password for localhost root account (< 5.7.x).] ***********************************************************************
changed: [cos7-server1] => (item=127.0.0.1)
changed: [cos7-server1] => (item=::1)
changed: [cos7-server1] => (item=localhost)

TASK [geerlingguy.mysql : Copy .my.cnf file with root password credentials.] **************************************************************************************
changed: [cos7-server1]

TASK [geerlingguy.mysql : Get list of hosts for the anonymous user.] **********************************************************************************************
ok: [cos7-server1]

TASK [geerlingguy.mysql : Remove anonymous MySQL users.] **********************************************************************************************************
changed: [cos7-server1] => (item=cos7-server1)
changed: [cos7-server1] => (item=localhost)

TASK [geerlingguy.mysql : Remove MySQL test database.] ************************************************************************************************************
changed: [cos7-server1]

TASK [geerlingguy.mysql : include_tasks] **************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.mysql/tasks/databases.yml for cos7-server1

TASK [geerlingguy.mysql : Ensure MySQL databases are present.] ****************************************************************************************************
changed: [cos7-server1] => (item={'name': 'wordpress', 'encoding': 'utf8', 'collation': 'utf8_general_ci'})

TASK [geerlingguy.mysql : include_tasks] **************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.mysql/tasks/users.yml for cos7-server1

TASK [geerlingguy.mysql : Ensure MySQL users are present.] ********************************************************************************************************
changed: [cos7-server1] => (item=None)
changed: [cos7-server1]

TASK [geerlingguy.mysql : include_tasks] **************************************************************************************************************************
included: /home/aleksei/Documents/GeekBrains/SCM/Lesson3/roles/geerlingguy.mysql/tasks/replication.yml for cos7-server1

TASK [geerlingguy.mysql : Ensure replication user exists on master.] **********************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : Check slave replication status.] ********************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : Check master replication status.] *******************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : Configure replication on the slave.] ****************************************************************************************************
skipping: [cos7-server1]

TASK [geerlingguy.mysql : Start replication.] *********************************************************************************************************************
skipping: [cos7-server1]

TASK [wordpress : create /var/www/192.168.0.26 directory for unarchiving] *****************************************************************************************
changed: [cos7-server1]

TASK [wordpress : Download and unpack latest WordPress] ***********************************************************************************************************
changed: [cos7-server1]

TASK [wordpress : Set ownership Redhat] ***************************************************************************************************************************
changed: [cos7-server1]

TASK [wordpress : Set ownership Debian] ***************************************************************************************************************************
skipping: [cos7-server1]

TASK [wordpress : Set permissions for directories] ****************************************************************************************************************
changed: [cos7-server1]

TASK [wordpress : Set permissions for files] **********************************************************************************************************************
changed: [cos7-server1]

TASK [wordpress : Set up wp-config] *******************************************************************************************************************************
changed: [cos7-server1]

TASK [Enabling http for zone public] ******************************************************************************************************************************
changed: [cos7-server1]

RUNNING HANDLER [geerlingguy.nginx : reload nginx] ****************************************************************************************************************
changed: [cos7-server1]

RUNNING HANDLER [geerlingguy.php : restart webserver] *************************************************************************************************************
changed: [cos7-server1]

RUNNING HANDLER [geerlingguy.php : restart php-fpm] ***************************************************************************************************************
changed: [cos7-server1]

RUNNING HANDLER [geerlingguy.mysql : restart mysql] ***************************************************************************************************************
[WARNING]: Ignoring "sleep" as it is not used in "systemd"
changed: [cos7-server1]

PLAY RECAP ********************************************************************************************************************************************************
cos7-server1               : ok=79   changed=32   unreachable=0    failed=0    skipped=38   rescued=0    ignored=0  

</pre>