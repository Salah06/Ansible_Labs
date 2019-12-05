# Installation Docker CE : CF doc docker

## Recuperaiton de l'image docker avec sshd

  docker pull rastasheep/ubuntu-sshd
  docker run -it -p 24:22 --name container1 rastasheep/ubuntu-sshd
  docker run -it -p 23:22 --name container2 rastasheep/ubuntu-sshd
  Recuperation de l'adress IP du container
  docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container2
  ssh 172.17.0.2
  ssh 172.17.0.3

  user : root
  mdp : root


## Copie de la clé ssh
  
  ansible web -m authorized_key -a "user=root key='contenue du fichier id_rsa.pub'" -i hosts --user root --ask-pass


## Lister les hosts et les var associé :
  
  ansible-inventory -i hosts --list
