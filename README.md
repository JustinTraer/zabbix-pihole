# Zabbix PiHole template
# Tested on Zabbix 7.0 

## Installation 
- Install jq: `sudo apt install jq`
- Copy `pihole_data.sh` to `/usr/local/bin`: `sudo cp pihole_data.sh /usr/local/bin` (If the bin directory does not exist, create it `sudo mkdir /usr/local/bin`)
- Make it executable: `sudo chmod a+x /usr/local/bin/pihole_data.sh`
- Install the systemd service and timer: `sudo cp pihole_data.service /etc/systemd/system` and `sudo cp pihole_data.timer /etc/systemd/system`
- Start and enable the timer: `systemctl enable --now pihole_data.timer`
- Copy pihole_data.conf into /etc/zabbix/zabbix-agentd.d: `sudo cp pihole_data.conf /etc/zabbix/zabbix_agenti2.d`
- Restart zabbix-agent: `sudo systemctl restart zabbix-agent2`
- Import `template_pihole_data.xml` on your Zabbix server
- Add template to server that has the pihole_data.sh service on in Zabbix
