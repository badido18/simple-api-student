ssh -i ssh-keys/id_rsa centos@madjid.boudis.takima.cloud
sudo ansible all -m service -a "name=httpd state=started" --private-key=ssh-keys/id_rsa -u centos --become