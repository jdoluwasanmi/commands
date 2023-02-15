# commands
command to put a file under a specific pattern on a local vm
sed -i -e '/^items/a host_support_level: full-baseline' /root/ansible/*.yaml 

on another vm 
for i in $(<hosts); do echo $i; ssh -q -t -o StrictHostKeyChecking=no $i "sudo -S sed -i '/<items/a host_support_level: full-baseline' /var/lib/jenkins/queue.xml.bak.bk"; done
