# Ansible Use Cases (14. Juni 2021)

## Clientmanagement (Linux + Windows): vordergründig
* Linux: Ubuntu (aktuelle LTS)
* Windows: 10

## Servermanagement
*	Linux: Ubuntu, RHEL

Reini Fink: eigenes Tool LAUS (Client holt sich Funktionen, PULL)
Ansible hat PUSH-Architektur, kommt von der Server-Orchestrierung

Ansible führt die Konfiguration nur auf jenen Clients durch, die noch nicht abgearbeitet wurden
Ansibel ist agent-los (man muss jedes Mal hin-PUSHEN)

## Windows-Clients:
*	Bildschirm automatisch klonen, wenn Bildschirm dran hängt (z.B. wenn sich User anmeldet) -> Registry / PowerShell Scripts
*	Anbindung von Druckern (Treiber)
*	Domain Join
*	Updates (Stefan: nur bei neuen Images, WSUS?)
*	Software installieren
*	Shell Commandos
*	Registry-Edits
*	User einrichten
https://docs.ansible.com/ansible/latest/collections/ansible/windows/index.html

## Linux-Clients:
*	Updates
*	Software installieren
*	auf Ursprungszustand zurück setzen (lvm, btrfs-snapshot)
*	SSSD-Config
* LDAP Configuration
*	bestehende Scripte laufen lassen
*	Prüfungsumgebungen (Sperren von Netzwerk, nur bestimmte Netzlaufwerke zur Verfügung stellen, ...)

### Schritt 1: Darlegen was der Linux-Client können soll
Nimm auch Win dazu, das mache ich parallel...
einfacher Client (lokaler gemeinsamer User) -> komplexerer Client (LDAP-Anbindung, klassische Client-Server Umgebung)

### Schritt 2: Automatisierung

