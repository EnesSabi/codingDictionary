#Docker
## Konfiguration
Einfach Docker Desktop für Windows installieren. Damit spart man sich so einiges an Arbeit :)
Docker-compose muss bei Linux nach installiert werden. Bei Linux muss man vor jeden Code noch ```sudo``` hinzufügen
Die Installation kann man einfach überprüfen mittels Powershell: ```docker info```

## Erste Kommandos mit Busybox
```docker run busybox``` --> Damit kann man eine Busybox erschaffen, welches da ist um kleine Funktionaliäten zu testen. Die Funktionalitäten und deren Codes sind oftmals deckungsgleich mit Linux-Befehlen. Am besten man öffnet man die Windows Powershell und gibt dort ```docker run busyboy echo "Hallo Welt!"``` ein. Damit hat man seinen ersten Container mit einer Wiedergabe gestartet und sieht sofort Ergebnisse.

## NGINX
```docker run nginx``` Falls NGINX nicht installiert isst wird es automatisch geladen und ausgeführt. Zum Verlassen kann man einfach Strg+C frücken. Falls man die Ports verändern will nimmt man den Standart Port 80 und den gewünschten Port ```docker run -p 5000:80 nginx```.

## Detached-Mode
Um nicht die Shell dauerhaft an den Container zu binden, kann man hier den "Detached-Mode" verwenden. Dazu muss man nur als Option ```-d``` noch hinzufügen und dann kann man aus dem Container springen mit ```exit```. Man kann dann entgültig mittels ```docker attach [ContainerID]```. Da man häufig mehrmals aus der Containershell raus und wieder hinein will, kann man auch die Option ```-ti``` verwenden, welche man dann mittels Strg+P danach Strg+Q "Escape-Sequence" verlassen kann.

## Verlinken
Damit man nicht nur die Standard NGINX Seite sieht, sondern auch die eigenen kann man Verlinken. Dazu einfach ```docker run -p 5000:80 -d -v '[Quell_URL]':/usr/share/nginx/html nginx```

## Stoppen und Löschen
Um alle laufenden Container zu sehen muss man ```docker ps -a``` eingeben. Dann werden einem alle container gezeigt mit der jeweiligen abgekürzten ContainerID. Falls bei Status nicht Existed steht, sondern Up, dann kann man die laufenden Container stoppen, in dem man ```docker stop [ContainerID]``` eingibt. Zum Löschen verwendet man ```docker rm [ContainerID]```. Zum Finden von Images kann man ```docker image ls``` zum finden aller Images und dann zum engültigen Löschen kann man ```docker rm [Image]``` verwenden. Um alle gestoppten Container auf einmal zu löschen, kann man ```docker container prune``` verwenden. Container und Images ist relativ gleich in der Verwendung.

## Auto-Run
Falls man seinen eigenen Containernamen haben möchte, dann ist es einfach gemacht und zwar kann man es einfach ins Skript einbetten ```docker run -p 5000:80 -dit --name [eigenerName] -v '[Quell_URL]':/usr/share/nginx/html nginx```. Für das automatische Neustarten kann man den Container mit einer kleinen Änderung auf gewisse Sachen reagieren lassen: ```docker run -p 5000:80 -dit --name [eigenerName] --restart [RestartOptionen] -v '[Quell_URL]':/usr/share/nginx/html nginx```. Zu den Neustart Optionen zählen unteranderem "unless-stopped", "always" und "on-failure". Man kann den gesamten Docker daemon stoppen/starten indem man ```docker systemctl stop/start docker```.

## Statistiken
Um die Statistiken der Container sich zeigen zu lassen, dann kann man ganz einfach ```docker stats```. Dann bekommt man alle laufenden Container mit Aktualisierungen.

## Ressourcen Limitierungen
Am besten gegen DDOS oder großem Ansturm auf den Server. ```docker run -p 5000:80 -dit --name nginx_container -m 4m --cpus"[Float.]" --restart unless-stopped -v '[Quell_URL]':/usr/share/nginx/html nginx``` --> -m b=byte, k=kilobyte, m=megabyte, g=gigabyte

## Logs
 ```docker logs [ContainerID]``` Damit kann man die Logs finden und durchschauen. Um Logging zu aktivieren muss der Container aufjedenfall gestopped sein. ```docker run -p 5000:80 -dit --name nginx_container -m 4m --cpus"0.5" --restart unless-stopped --log-driver json-file --log-opt max-size=100m -- log-opt max-file=100 -v '[Quell_URL]':/usr/share/nginx/html nginx```. Um den Log zu finden muss man sich nur in die Shell ```docker inspect - {{.LogPath}} [ContainerID]``` eingeben und dann wird einem der Pfad zur Datei offen gelegt.

## Dockerfiles
Man kann auch Docker Files verwenden, welches den Container später baut. Dazu kann man einfach die Endung .Dockerfile verwenden.