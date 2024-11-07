# file check untuk prepare env ambari

#!/bin/bash

echo ""
echo -e "========== Checking ALL Environment ==========\n"
sleep 1

echo "# Checking Hostname-FQDN"
for node in $(cat all-nodes.txt); do
    status=$(ssh root@$node "hostname -f")
    echo "Hostname: $status"
done
sleep 2
echo ""

echo "# Checking /etc/hosts"
for node in $(cat all-nodes.txt); do
    status=$(ssh root@$node "cat /etc/hosts | grep -v 'localhost'")
    echo "$node, $status"
done
sleep 2
echo ""

echo "# Checking firewall"
for node in $(cat all-nodes.txt); do
    status=$(ssh root@$node "systemctl status firewalld | grep Active")
    echo "$node, (firewall: $status)"
done
sleep 2
echo ""

echo "# Checking SELinux"
for node in $(cat all-nodes.txt); do 
   status=$(ssh root@$node "sestatus")
   echo "$node, ($status)"
done
sleep 2
echo ""

echo "# Checking Network-Host"
for node in $(cat all-nodes.txt); do
    status=$(ssh root@$node "cat /etc/sysconfig/network | grep -v 'anaconda'")
    echo "$node, $status"
done
sleep 2
echo ""

echo "# Checking NTP"
for node in $(cat all-nodes.txt); do
    status=$(ssh root@$node "systemctl status chronyd | grep Active")
    echo "$node, (chronyd service: $status)"
done
sleep 2
echo ""

echo "# Checking Python Version"
for node in $(cat all-nodes.txt); do
    ssh root@$node "echo -n '$node,' 'Python Version: ' && python -V"
done
sleep 2
echo ""

echo "# Checking Repository Epel"
for node in $(cat all-nodes.txt); do
    status=$(ssh root@$node "rpm -qa | grep epel-release")
    echo "$node, (package: $status)"
done
sleep 2
echo ""

echo "# Checking RPM Java"
for node in $(cat all-nodes.txt); do
    status=$(ssh root@$node "rpm -qa | grep openjdk") 
    echo "$node"
    echo "Package: $status"
    echo -e "Locate: $JAVA_HOME\n"
done
sleep 2
echo ""

echo -e "========== Checking ALL Environment Done! ==========\n"
sleep 1

# mesin pencari untuk mencari dan copy file ke dir tujuan
#!/bin/bash

# Tempat file berada dan lokasi tujuan
# sesuaikan dengan direktori induk tempat file berada
tempat_file="/home/adam/hadoop-3.3.6/" 
read -p "Masukkan nama file: " nama_file
# sesuaikan dengan direktori tujuan
lokasi_tujuan="/home/adam/rpmbuild/SOURCES/hadoop_3.2.0.0-3.3.6_S247.3.2.0.0/etc/hadoop/conf.empty" 

# Mencari file yang sesuai dengan pola dan menyalinnya ke direktori tujuan
find "$tempat_file" -name "$nama_file" -exec cp {} "$lokasi_tujuan" \;

echo "Proses pencarian dan penyalinan selesai."

