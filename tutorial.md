# Umgang mit Docker Client

## Ausführen eines einfachen Containers

Startet die Bash in einem ubuntu Container

```bash
docker run -it --rm ubuntu /bin/bash
``` 

Den Container könnt ihr mit `exit` verlassen.

### Zusatzfragen

* Was passiert, wenn ihr `--rm` weglasst und den Container mit `exit`
verlasst?
* Restartet den Container. Wie könnt ihr wieder mit der Kommandozeile
interagieren? 

## Login in einen laufenden Container

Zur Vorereitung braucht ihr zwei Terminalfenster.

1. Terminalfenster: `docker run httpd:2.4`
2. Terminalfenster: 

* Findet die Container-Id mittels `docker ps` raus
* Logged euch in den Container ein `docker exec -it <containerId>
/bin/bash`

### Zusatzfragen

* Worin unterscheiden sich `docker run httpd` und `docker run httpd:2.2`
und warum?

## Informationen zu einem laufenden Container erhalten
Aus der letzten Übung solttet ihr noch einen laufenden MySQL Container
haben. Schaut euch Details zu dem Container an

* `docker inspect <containerId>`: Achtet einmal auf die IP Adresse.
* `docker logs <containerId>`

Stopt und Startet den laufenden container. Hat er die gleiche IP Adresse
wie vorher?

## Anzeige der laufenden Prozesse eines Containers

Falls der httpd Container (s.o.) nicht mehr läuft, bitte erneut starten.

`docker top <containerId>` zeigt die laufenden Prozesse des Containers an.

## Anzeige der Images und deren Historie

* Mittels `docker images` die Images anzeigen.
* Mittels `docker history <imageId>` history anzeigen
* Mittels `docker history <repository>:tag`(also etwa `docker histroy
httpd:2.4`) die History anzeigen.


## Port Mappings

* Mittels `docker run -P -d httpd:2.4` httpd daemon starten.
* Mittels `docker port <containerId>` das Portmapping anschauen.
* Container stoppen und entfernen
* Mittels `docker run -p 127.0.0.1:8080:80 -d httpd:2.4` den Container
starten und das Port mapping nochmals anschauen
* Mittels `curl http://127.0.0.1:8080` einmal einen HTTP Request absetzen.

## Container Limits

* Mittels `docker stats <containerId>` den CPU und Speicherverbrauch
anzeigen
* Container stoppen und löschen
* Mittels `docker run -p 127.0.0.1:8080:80 -d -m 100m httpd:2.4` einen
neuen Container starten und mit `docker stats` dessen Resourcenverbrauch
abfragen. Was hat sich geändert?

## Volumes

* Volumes generell
* Host Directory Mapping

### Zusatz

* Data volume container zum Datenaustausch

## Links

* Linked Containers erstellen
* Login, um sich /etc/hosts anzusehen
*

# Docker-Compose

