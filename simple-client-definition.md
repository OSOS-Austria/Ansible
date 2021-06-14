## DEFINITION zur Funktionsweise eines einfachen Linux-Clients

shared account ohne LDAP-Anbindung

Expected details, prerequirements for standardization playbooks: 
1. Distro version: Ubuntu 20.04.2.0 LTS
2. Spracheinstellung: Englisch 
3. Keyboard Layout: German/German 
4. Default Installation (kein Minimal Install, oder? -> nein) 
5. Add additional driver/software 
6. Timezone: Vienna 
7. Hostname? 
8. Ansible user/password?
9. SSH Keys falls im Netzwerk vorhanden
10. Disable livepatch 
11. Dis/Enable Location sharing

...wobei einiges auch von Ansible gesetzt werden können. 

regelmäßige Software-Updates

zusätzliche Software installieren

auf Standard Installation zurück setzen

Admin Account einrichten

User Account anlegen

sudo for shared account aktivieren


TODO:
1. Woher kommen die Software updates? Haben wir eine Ubuntu Repo? (foreman?) 

Rene:
@4: default installation
@7: kann eine eindeutige ID bestimmt werden?
@todo1: reicht es nicht, die Ubuntu eigenen Repos anzustoßen? 
