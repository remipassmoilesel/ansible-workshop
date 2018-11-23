# Ansible playground

Ce dépôt permet de s'exercer avec Ansible sur des machines locales ou en ligne.

## Méthodologie

Avant toutes chose, il faut s'assurer de pouvoir se connecter aux machines en SSH:

    $ ssh root@10.0.0.5     ->  azerty
    $ ssh root@10.0.0.6     ->  azerty

Ensuite lancer les playbooks:

    $ cd ansible-playground
    $ ansible-playbook -i inventory/inventory.cfg playbooks/example1.yml
    

## Machines locales

Utilisation:

    $ cd vagrant
    $ vagrant up
    
Ces deux commandes permettent de créer deux machines virtuelles Centos 7 accessible sur 10.0.0.5 et 10.0.0.6.

Pour arrêter les machines:

    $ vagrant halt
    
Pour détruire les machines:

    $ vagrant destroy    


