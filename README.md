# K.knock_WebHack_CTF   

This is the club's own competition.   
Competition is held in CTF format. Participants are divided into teams,   
and team members take part with their personal website created during the study.   
Each participant is given a server and a total of 2 flags are stored in the server's "/flag" path and DB.   
Of course, flags within the server score higher than DB flags.   
Flags change automatically every 3 hours from the start of the competition.   
   
   
   
***
# Preparations

## Server
>  - Install CTFd   
>  (install it Ubuntu 18.04) Ubuntu 16.04 didn't work   
>  https://github.com/CTFd/CTFd.git   
>  
>  
>  - Change TimeZone   
>  ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime     
>  
>  
>  - Install cron   
>  apt-get install -y cron   
>  
>  
>  - Set Crontab   
>  crontab -e   
>  input >> 0 */3 * * * /usr/bin/python3 /home/user/server.py   
>  (Execute server.py Every 3 hours) save it!   
>  service cron restart   



## Client   
>  - Change TimeZone   
>  ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime   
>     
>  
>  - Install cron, pip   
>  apt-get install -y cron   
>  apt-get install -y python3-pip   
>  pip3 install pymysql   
>  
>  
>  - Make directory and file   
>  mkdir /flag   
>  cd /flag   
>  touch flag   
>  
>  
>  - Set Mysql   
>  create database flag;   
>  use flag;   
>  create table flag (flag varchar(50));   
>  insert into flag values ("flag{}");   
>  
>  
>  - Change mode client.py   
>  chmod 600 client.py   
>  (Shouldn't read with root)   
>  
>  - Set Crontab   
>  crontab -e   
>  input >> 0 */3 * * * /usr/bin/python3 /flag/client.py   
>  (Execute client.py Every 3 hours) save it!   
>  service cron restart   
>  
