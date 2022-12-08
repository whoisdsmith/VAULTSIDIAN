---
tags:: notes
---
# nextcloud-zabbix
With this template you can monitor a nextcloud via xml file
1. Import "zbx_export_templates.xml" to your zabbix templates
2. change domain in nextcloud.conf file copy it to /etc/zabbix/zabbix_agentd.d/nextcloud.conf
3. add line 'Include=/etc/zabbix/zabbix_agentd.d/nextcloud.conf' to zabbix_agentd.conf file
4. add additional macro to your nextcloud host called "{$NCPW}" and add your api user password as value