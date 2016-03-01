# Use zabbix to Monitor OpenStack
#####1: Import template to zabbix
#####2: add user parameter to zabbix
	# cat zabbix_agentd.conf | grep Include
	Include=/etc/zabbix/zabbix_agentd/
	# ls /etc/zabbix/zabbix_agentd/
	ceph.conf  rabbitmq.conf  mysql.conf
#####3: add cron to get data
	# crontab -l
	*/1 * * * * /usr/bin/ceph -s -f json | python -m json.tool > /tmp/cstatus.log
	*/2 * * * * /usr/sbin/rabbitmqctl report > /tmp/rabbitmq.txt

### Demo 
> Some graph
######Rabbitmq
![](http://7xkmxw.com1.z0.glb.clouddn.com/mysql.jpg)
######Ceph
![](http://7xkmxw.com1.z0.glb.clouddn.com/ceph.jpg)
######Mysql
![](http://7xkmxw.com1.z0.glb.clouddn.com/FuikS-glvskDebgSG04xtTUUusTb)



