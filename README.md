# Playbook 說明

Playbook                               | Description
:--------------------------------------|:------------------------
apigee-port-check.yml                  | 單中心服務Port檢查
apigee-port-check-dr.yml               | 雙中心服務Port檢查


# Inventory 說明

Group                   | Description
:-----------------------|:---------------------------------------
ds | ZooKeeper 和 Cassandra
ms | Edge Management Server, Edge UI 和 OpenLDAP
rpm | Edge Router 和 Message Processor
qs | Qpid Server
ps | Postgres Server
dp | 開發者門戶
sso | Apigee SSO
ue | New Edge UI
ds_dr | DR Site ZooKeeper 和 Cassandra
ms_dr | DR Site Edge Management Server, Edge UI 和 OpenLDAP
rpm_dr | DR Site Edge Router 和 Message Processor
qs_dr | DR Site Qpid Server
ps_dr | DR Site Postgres Server
dp_dr | DR Site 開發者門戶 
sso_dr | DR Site Apigee SSO
ue_dr | DR Site New Edge UI 


# 使用說明

cd apigee_port_check

單中心服務Port檢查:

ansible-playbook -i inventory.ini apigee-port-check.yml

雙中心服務Port檢查:

ansible-playbook -i inventory-dr.ini apigee-port-check-dr.yml 

# 選項

Common Options | Value                 | Description
:--------------|:----------------------|:------------------------
--tags         | ex: ds,ld,ms....      | 執行部分 playbook
--extra-vars   | enable_listener=false | 不建立 listener