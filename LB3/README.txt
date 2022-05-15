#LB3#
##Inhaltsverzeichnis##

    -Service Beschreibung
    -Service Anwendung
    -Grafische Übersicht
    -Code Beschreibungo 
    -Service Testen
    -Quellenangaben wo nötig


##Service Beschreibung##

Eine Webschnittstelle für die Verwaltung 
von Docker-Containern mit Schwerpunkt auf
 Templates, um die Bereitstellung von 
 Docker-Anwendungen mit nur einem Klick 
 zu ermöglichen. Stellen Sie es sich wie 
 einen dezentralen App Store für Server 
 vor, für den jeder Pakete erstellen kann.

##Service Anwendung##
Yacht wird meistens bei Linux Geräten ohne grafische Oberfläche benutzt.
Dank Yacht hat man auf jedem Gerät eine abgespeckte Version vom Dockerhub. 
Das alleinstelllungsmerkmal von Yacht sind die Templates, mit welcher man 
seine Weboberfläche so gestalten kann wie man will.

##Grafische Übersicht##
Das GUI von Yacht sieht von User zu User immer sehr unterschiedlich aus.
 Die Farben sind meistens anderst und die Menüpunkte anderst sortiert. Wie oben schon erwähnt kann man
 Templates verwenden um die Farben und die Menü-Struktur zu verändern.

Ich habe Screenshot von der Standart Menü-Struktur gemacht um Ihnen zeigen zu können, was es alles zu sehen gibt. 

images\YachtDashboard.png
Nach dem Anmeldescreen sieht man als erstes sein Dashboard. Hier kann man selber entscheiden was man als erstes zu Gesicht bekommen möcht.

images\YachtApplications.png
Hier sieht man die Applikationen, welche man zuer verfügung hat. Diese kann man auch von hier aus ein -oder ausschalten.

images\Templates.png
Unter diesem Fenster sieht man seine Templates. Ich habe zuerzeit keine Templates installiert.

images\Projects
Unter Projects sieht man seine Docker Projekte und kann auch neue erstellen in dem man auf das Plus klickt.
Sobald man auf das Plus klickt erscheint ein Editor in welchem man eine compose Datei erstellen kann.

images\YachtRessourcesImages.png
Hier sieht man alles Images, welche man heruntergeladen hat. 

images\YachtRessourcesNetworks.png
Hier sieht man seine Docker Netzwerke.

images\YachtRessourcesVolumes.png
Hier sieht man wie die verschiedenen Volumes belastet sind.

images\Settings.png
Unter den Einstellungen kann man seine Templates anpassen, seinen Papierkorb leeren oder alte 
Dateien wiederherstellen und Yacht updaten. 

##Code Beschreibung##
''
    version: "3"
services:
  yacht:
    container_name: yacht
    restart: unless-stopped
    ports:
      - 3000:3000
    volumes:
      - yacht:/config
      - //var/run/docker.sock:/var/run/docker.sock
    image: selfhostedpro/yacht

  volumes:
  yacht:
''

In der obersten Zeile steht die SoftwareVersion.
Darunter wird der Name vom Container definiert.
Eine Zeile weiter unten wird definiert wann der container neustarten soll.
Danach werden die Ports angegeben, über welche man auf die Weboberfläche gelangen kann und die Volumes, weche verwendet werden.
Ganz zum Schluss wird dan noch das Image angegeben. 


##Service Testen##

Ich habe die anzeige auf der Weboberfläche mit der auf DockerHub verglichen und es wurde alles richtig angezeigt. 
Das ändern und erstellen von Templates verlief auch reibungslos.
Das erstellen von Projekten funktionierte auch problemlos.

