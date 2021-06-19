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

* regelmäßige Software-Updates
* zusätzliche Software installieren
* auf Standard Installation zurück setzen
* Admin Account einrichten
* User Account anlegen
* sudo for shared account aktivieren


TODO:
1. Woher kommen die Software updates? Haben wir eine Ubuntu Repo? (foreman?) 

Rene:

@4: default installation

@7: kann eine eindeutige ID bestimmt werden?

@todo1: reicht es nicht, die Ubuntu eigenen Repos anzustoßen? 

Reini:

@2: Spracheinstellungen eher Deutsch

@4: Ubuntu - Desktop ist sicher eine gute Ausgangsbasis

@5: hier sollten unsere "Playbooks" zum Einsatz kommen. Aber je gemeinsamer um so besser.
    Spezialprogramme wie IntelliJava, AndroidStudio funktionieren auch gut von Netzwerklaufwerken
    und lassen sich so auch gut aktuell halten. (Erstz für snapd)
    
@7: für Anbindung an Kerberos = AD = SAMBA4 leider eindeutig notwendig 
    hostname wird bei preseed Installation normalerweise nach dhcp-Eintrag gesetzt
    bei UEFI Installation mittels Ubuntu-Serverinstaller leider nicht mehr :-( d.h. wieder ein bißchen frickeln
    
@9: stört nicht, schadet nicht :-)

@wobei:
* regelmäßige Software-Updates
bin bisher mit den Sicherheitsupdates bis auf eine Ausnahme gut gefahren.
d.h. Firefox immer letzte Version
Argument dafür: "wir Linuxer tun was für die Sicherheit ;-) 

ZIEL:
Wir wollen die Leute motivieren Linux am Desktop zu verwenden. 

Daher macht eine gängige Distribution (im Augenblick Ubuntu) als Ausgangsbasis Sinn.

Der OS² - Desktop ergänzt den Standarddesktop um:
1. Sinnvolle Programme für den Bildungsbereich
2. einen selbstheilenden User, der aber bei Bedarf gepflegt werden kann.
   z.B.: Sinnvolle Bookmarks wie z.B.: Zugang Webuntis und andere häufig im Unterricht benötigte URLs
   
Diese Änderungen des OS² - Desktops können von jedem  Benutzer auf seinem Rechner mittels Ansible/Bash - Skript selbst installiert werden.
installOSOSSoftwareSelection.sh
installOSOSSelfHealingUser.sh

Claudio:
@2: Spracheinstellungen wäre ich auch eher bei Deutsch
@4: Lässt sich ein standard Ubuntu Desktop per netinstall installieren?
    Ich dachte, dass netinstall nur für Ubuntu-Server zur Verfügung steht und man dann hald alles nachinstallieren muss.
    Nach dieser Installation sollte idealerweise der SSH-Schlüssel vom Ansible schon drauf sein.
@7: Die Vergabe der Hostnames erfolgt wohl sehr standortspezifisch (Raumnummer, Stock, usw.)
    Könnte man das mit einem Inventar-File (Hostname, MAC) umsetzen?

Zusätzliche Programme können ja einfach über Rollen modular dazu genommen werden.

Wir haben in unseren Playbooks noch ein paar Anpassungen:
- Welche Apps sind im launcher
- Zusätzliches Menü oben rechts
- default apps
- autologin in einen Guest-User (In den Klassen keine Anbindung an den LDAP über sssd)
Macht ihr hier auch noch Anpassungen, oder soll das dann einfach Standortspezifisch bleiben?
Hier eine Übersicht über unser Client-PC Ansible Setting: https://pro.files.cnow.at/index.php/s/iLrW5QQSpZ6paJH
