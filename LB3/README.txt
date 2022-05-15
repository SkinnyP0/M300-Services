<h1>LB3</h1>
<h2>Inhaltsverzeichnis<h2<
<ul>
    <li>Service Beschreibung</li>
    <li>Service Anwendung</li>
    <li>Grafische Übersicht</li>
    <li>Code Beschreibungo </li>
    <li>Service Testen</li>
    <li>Quellenangaben wo nötig</li>
<ul>

<h2>Service Beschreibung</h2<

<p>Eine Webschnittstelle für die Verwaltung 
von Docker-Containern mit Schwerpunkt auf
 Templates, um die Bereitstellung von 
 Docker-Anwendungen mit nur einem Klick 
 zu ermöglichen. Stellen Sie es sich wie 
 einen dezentralen App Store für Server 
 vor, für den jeder Pakete erstellen kann.</p>

<h2>Service Anwendung</h2>
<p>Yacht wird meistens bei Linux Geräten ohne grafische Oberfläche benutzt.
Dank Yacht hat man auf jedem Gerät eine abgespeckte Version vom Dockerhub. 
Das alleinstelllungsmerkmal von Yacht sind die Templates, mit welcher man 
seine Weboberfläche so gestalten kann wie man will.<\p>

<h2>Grafische Übersicht</h2>
<p>Das GUI von Yacht sieht von User zu User immer sehr unterschiedlich aus.
 Die Farben sind meistens anderst und die Menüpunkte anderst sortiert. Wie oben schon erwähnt kann man
 Templates verwenden um die Farben und die Menü-Struktur zu verändern.<\p>

<p>Ich habe Screenshot von der Standart Menü-Struktur gemacht um Ihnen zeigen zu können, was es alles zu sehen gibt. <\p>

images\YachtDashboard.png
<p>Nach dem Anmeldescreen sieht man als erstes sein Dashboard. Hier kann man selber entscheiden was man als erstes zu Gesicht bekommen möcht.<\p>

images\YachtApplications.png
<p>Hier sieht man die Applikationen, welche man zuer verfügung hat. Diese kann man auch von hier aus ein -oder ausschalten.<\p>

images\Templates.png
<p>Unter diesem Fenster sieht man seine Templates. Ich habe zuerzeit keine Templates installiert.<\p>

images\Projects
<p>Unter Projects sieht man seine Docker Projekte und kann auch neue erstellen in dem man auf das Plus klickt.
Sobald man auf das Plus klickt erscheint ein Editor in welchem man eine compose Datei erstellen kann.<\p>

images\YachtRessourcesImages.png
<p>Hier sieht man alles Images, welche man heruntergeladen hat. <\p>

images\YachtRessourcesNetworks.png
<p>Hier sieht man seine Docker Netzwerke.<\p>

images\YachtRessourcesVolumes.png
<p>Hier sieht man wie die verschiedenen Volumes belastet sind.<\p>

images\Settings.png
<p>Unter den Einstellungen kann man seine Templates anpassen, seinen Papierkorb leeren oder alte 
Dateien wiederherstellen und Yacht updaten. <\p>

<h2>Code Beschreibung</h2>
<code>
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
<\code>
<p>
In der obersten Zeile steht die SoftwareVersion.
Darunter wird der Name vom Container definiert.
Eine Zeile weiter unten wird definiert wann der container neustarten soll.
Danach werden die Ports angegeben, über welche man auf die Weboberfläche gelangen kann und die Volumes, weche verwendet werden.
Ganz zum Schluss wird dan noch das Image angegeben. 
<\p>

<h2>Service Testen<\h2>
<p>
Ich habe die anzeige auf der Weboberfläche mit der auf DockerHub verglichen und es wurde alles richtig angezeigt. 
Das ändern und erstellen von Templates verlief auch reibungslos.
Das erstellen von Projekten funktionierte auch problemlos.
<\p>
