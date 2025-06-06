# Cheats

## Enable apache worker | event mod
Check which module is running  
```
apachectl -V | grep -i mpm
```


List Available MPM Modules  
```
ls /etc/apache2/mods-available/mpm*
```

Stop apache  
```
systemctl stop apache2
```

Disable MPM_PREFORK module  
```
a2dismod mpm_prefork
```

Enable MPM_WORKER or MPM_EVENT module  
```
a2enmod mpm_worker | mpm_event
```

## Configuring MPM
Apache configuration  
```
/etc/httpd/conf/httpd.conf` or `/etc/apache2/apache2.conf
```
```
<IfModule mpm_worker_module>
    StartServers         2
    MinSpareThreads     25
    MaxSpareThreads     75 
    ThreadLimit         64
    ThreadsPerChild     25
    MaxClients          150
    MaxRequestsPerChild  0
</IfModule>
```
```
<IfModule mpm_event_module>
	ServerLimit		16
	StartServers		8
	MinSpareThreads		25
	MaxSpareThreads		75
	ThreadLimit		64
	ThreadsPerChild		25
	MaxRequestWorkers	400
	MaxConnectionsPerChild  3000
</IfModule>
```
Verify config  
```
apachectl configtest
```


