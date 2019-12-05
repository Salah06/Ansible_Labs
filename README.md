Installation Docker CE : CF doc docker

Recuperaiton de l'image docker avec sshd

docker pull rastasheep/ubuntu-sshd
docker run -it -p 24:22 --name container1 rastasheep/ubuntu-sshd
docker run -it -p 23:22 --name container2 rastasheep/ubuntu-sshd
Recuperation de l'adress IP du container
docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container2
ssh 172.17.0.2
ssh 172.17.0.3

user : root
mdp : root


Copie de la clé ssh
ansible web -m authorized_key -a "user=root key='ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC+nkXx86lM5Di15rIwcOAdippFbZOZBFLFaF7x1Co9XZXrpvfgBm9NRWA3eQ+/ZSaRHK+2SVbTcS2XFe64NndX2ksaUjajy34d1o1Ijyj3BM7lNvijMVmAuOJEjF0zFdj8aPnNf7kxEU/DKxqtEXfkd2lAxE0l481nkLeNXhLylNguIUViuZHif3EEB3enpE82VsmM6l5VpvqeXxOy9X35sp25ReBXVBdVY+J7oTd8xwQI2N6Lz2Ad4fQ2DqSTdf57KdPqGILBpuCKVZ/Axdvinx1DfiunfyFY2IUsUVgc9ApKrOitV2aTzTraIbP3pV+ij56KnPZm2NppmRHRapCJ dahmoul@dahmoul-VirtualBox'"
-i hosts --user root --ask-pass

Afficher le fichier host comme il est vu par ansible
ansible web -m authorized_key -a "user=root key='ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC+nkXx86lM5Di15rIwcOAdippFbZOZBFLFaF7x1Co9XZXrpvfgBm9NRWA3eQ+/ZSaRHK+2SVbTcS2XFe64NndX2ksaUjajy34d1o1Ijyj3BM7lNvijMVmAuOJEjF0zFdj8aPnNf7kxEU/DKxqtEXfkd2lAxE0l481nkLeNXhLylNguIUViuZHif3EEB3enpE82VsmM6l5VpvqeXxOy9X35sp25ReBXVBdVY+J7oTd8xwQI2N6Lz2Ad4fQ2DqSTdf57KdPqGILBpuCKVZ/Axdvinx1DfiunfyFY2IUsUVgc9ApKrOitV2aTzTraIbP3pV+ij56KnPZm2NppmRHRapCJ dahmoul@dahmoul-VirtualBox'" -i hosts --user root --ask-pass


Lister les hosts et les var associé :

ansible-inventory -i hosts --list
