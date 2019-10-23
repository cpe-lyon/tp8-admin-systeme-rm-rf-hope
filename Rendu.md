# TP 8 - Ansible

Participans:
- Eloi Desbrosses
- Robin Amouret
- Rémi Quemin
- Victor magat
- Thibault Louapre

## Exercice 1 Configuration

La configuration des machines à été effectué sur virtualbox et VMWare. Une machine 'superviseur' et 'node' ont été créer à partir d'une machine de base utilisant ubuntu server live 19.10.

Sur VMWare, les VM ont été directement raccordé au réseau du poste hôte pour obtenir leurs propre adresse IP du DHCP. Cela simplifie la gestion des adresse IP ainsi que les connexions en SSH pour pouvoir effectuer deux connexion SSH en même temps (pur comfort).

Conformément à la [documentation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#basics-what-will-be-installed), Ansible à été installé via le gestion de packet apt sur la VM superviseur. 
```
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo apt-add-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
```

Une fois l'installation effectué avec succès, un nouveau groupe de machine cliente à donc été mis en place:

```
/etc/ansible/hosts

...

[servers]
node

...

```
PS: node réfère à l'adresse IP de la VM node installé précédemment.

Dans le cas ou nous aurions plus de machine cibles avec lesquels nous souhaiterions intéragir, nous avons juste à rajouter leurs adresse IP à cette liste.

Pour automatiser la connexion par SSH nous avons mis en place une clè d'authentification conformément à la  [documentation SSH](https://www.ssh.com/ssh/copy-id#sec-Generate-an-SSH-Key). 

## Exercice 2 Tâche à réaliser
