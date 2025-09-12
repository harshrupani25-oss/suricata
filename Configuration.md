1. Download and extract the Emerging Threats Suricata ruleset:

       cd /tmp/ \&\& curl -LO https://rules.emergingthreats.net/open/suricata-6.0.8/emerging.rules.tar.gz
       sudo tar -xvzf emerging.rules.tar.gz \&\& sudo mv rules/\*.rules /etc/suricata/rules/
       sudo chmod 640 /etc/suricata/rules/\*.rules



2. Modify Suricata settings in the /etc/suricata/suricata.yaml file and set the following variables:

       Go to the nano /etc/suricata/suricata.yaml and change the following content and also set the ip of your machine:
       HOME\_NET: "<UBUNTU\_IP>"
       EXTERNAL\_NET: "any"



default-rule-path: /etc/suricata/rules

rule-files:

   "\*.rules"


Global stats configuration

stats:
enabled: Yes


Linux high speed capture support

af-packet:
  - interface: eth0



3.  Useful Commands:

        sudo systemctl status suricata
        sudo systemctl restart suricata
        sudo tail -f /var/log/suricata/eve.json



4. Logs:

       Default logs are stored in /var/log/suricata/:
       eve.json → JSON alerts/logs
       fast.log → Short alerts
       stats.log → Performance statistics
       suricata.log → Service logs



5. you can also read the file using this command:

       sudo tail -f /var/log/suricata/eve.json
 


6. Rules \& Updates:

       sudo suricata-update
       sudo suricata-update list-sources
       sudo suricata-update enable-source <source\_name>
       sudo suricata-update



