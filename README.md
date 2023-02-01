# Домашнее задание к занятию 9.2 «Zabbix. Часть 1» - Карпов Роман
 ---

### Задание 1 

Установите Zabbix Server с веб-интерфейсом.

*Приложите скриншот авторизации в админке.*
*Приложите текст использованных команд в GitHub.*

### Ответ:  
Скрин админки ![Скрин](https://github.com/Karhq/9.2_hw_zabbix/blob/main/1.9.png)  

Список команд (ставил полностью по презентации):  
- sudo apt install postgresql  
- wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bdebian11_all.deb  
- dpkg -i zabbix-release_6.0-4+debian11_all.deb  
- apt update   
- sudo apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts nano -y zabbix-agent  
- sudo -u postgres createuser --pwprompt zabbix  
- sudo -u postgres createdb -O zabbix zabbix  
- zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix   
- sudo nano /etc/zabbix/zabbix_server.conf  
- sudo systemctl restart zabbix-server apache2 # zabbix-agent  
- sudo systemctl enable zabbix-server apache2 # zabbix-agent  


---

### Задание 2 

Установите Zabbix Agent на два хоста.

*Приложите скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу.*
*Приложите скриншот лога zabbix agent, где видно, что он работает с сервером.*
*Приложите скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.*
*Приложите текст использованных команд в GitHub.*

### Ответ:   

