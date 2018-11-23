# Ansible playground

Ce dépôt permet de s'exercer avec Ansible sur des machines locales ou en ligne.

## Installer Ansible

    $ sudo apt install python-pip && sudo pip install ansible


## Machines virtuelles locales

Utilisation:

    $ cd vagrant
    $ vagrant up
    
Ces deux commandes permettent de créer deux machines virtuelles Centos 7 accessible sur 10.0.0.5 et 10.0.0.6.

Pour arrêter les machines:

    $ vagrant halt
    
Pour détruire les machines:

    $ vagrant destroy    
    
Les mot de passe root est `azerty`.    


## Commandes utiles

Avant toutes chose, il faut s'assurer de pouvoir se connecter aux machines en SSH:

    $ ssh root@10.0.0.5     ->  azerty
    $ ssh root@10.0.0.6     ->  azerty

Lancer un playbook ansible sur les machines:

    $ cd ansible-playground
    $ ansible-playbook -i inventory/inventory.cfg playbooks/example1.cfg
    
Lancer un playbook mais demander le mot de passe de connexion:

    $ ansible-playbook -i inventory/inventory.cfg playbooks/example1.yml --ask-pass
    
N'éxécuter que les tâches taggées Yum ou Configuration:

    $  ansible-playbook -i inventory/inventory.cfg playbooks/example1.yml -t yum,configuration         


## Erreurs courantes
    
### Received disconnect from 10.0.0.5 port 22:2: Too many authentication failures    
    
Vous devriez configurer votre client SSH dans le fichier ~/.ssh/config

    Host 10.0.0.*
        IdentityFile ~/.ssh/agysoft/id_rsa
        User root

Vous pouvez aussi utiliser cette commande:    

    $ 🐼 ssh -o pubkeyauthentication=no root@10.0.0.5 
    Received disconnect from 10.0.0.5 port 22:2: Too many authentication failures
    Disconnected from 10.0.0.5 port 22
