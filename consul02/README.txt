#
# // -- Instructions -- \\
#
# cd ~
#
## Clone git@github.com:pexessj/clusterconsul.git
#
# mkdir -p /opt/consul/consul.d/
# cd /opt/consul/
# wget https://releases.hashicorp.com/consul/0.6.3/consul_0.6.3_linux_amd64.zip
# unzip consul_0.6.3_linux_amd64.zip
# ln -s /opt/consul/consul /sbin/consul
# 
## Copy consul configuration file
#
# cp ~/clusterconsul/consul02/files/config.json /opt/consul/
#
## Configure LOCAL0 on Rsyslog
#
# vim /etc/rsyslog.d/50-default.conf
# 
## Add this line:
#
# local0.*			-/var/log/consul.log
#
## Restart Rsyslog service
#
# service rsyslog restart
#
## Install Supervisord (Ubuntu 14.04 LTS)
#
# apt-get install supervisor
#
## Append the consul-start-stop-supervisord configuration to Supervisord config file.
#
# cat ~/clusterconsul/consul01/files/consul-start-stop-supervisord >> /etc/supervisor/supervisord.conf
#
## Restart supervisord service
#
# service supervisor restart
#
## Access Consul Web UI on the node01 http://IP_NODE01:8500/ui
#
