# Space Assault – Browserspiel

Ein Weltraum Browserspiel als Prüfungsleistung im Modul Database Engineering im SoSe 2022 der Hochschule Osnabrück.

Das Browserspiel SpaceAssault lässt sich grundsätzlich in eine Architektur mit drei Schichten einteilen: Die Datenhaltungsschicht stellt einen Speicherplatz in geeigneter Struktur bereit, um die Daten und Relationen der Anwendung zu persistieren. Darauf aufbauen folgt die Serveranwendung bzw. Fachkonzeptschicht, die die Daten der verschiedenen Anwender entgegennimmt, diese verarbeitet und an die Datenhaltungsschicht zur Speicherung weitergibt. Die Clients, die von den Anwendern bedient und wo die Daten eingetragen werden, wird GUI-Schicht genannt. Wie die Anwender mit der GUI-Schicht interagieren und die daraus entstehenden Daten verarbeitet und gespeichert werden, wird anhand von drei Anwendungsfälle exemplarisch gezeigt.

Das Datenbank-System ist nicht Bestandteil dieses Repositories und wird vorrausgesetzt. Die Initialisierung der Datenbank kann aber mit dem [Script](https://github.com/hendrik-Sch/SpaceAssault/blob/master/server/initialise%20database%20Space%20Assault.sql) vorgenommen werden.

## Voraussetzungen
* Server zum Bereitstellen im Netzwerk
* [node.js](https://nodejs.org/) v17.6.0 (andere Version mögen auch funktionieren, sind allerdings nicht getestet)
* Endgeräte mit dem Chrome oder Safari Webbrowser (andere Browser mögen auch funktionieren, sind allerdings nicht getestet)

## Installation
1. dieses [Repository](https://github.com/hendrik-Sch/SpaceAssault) herunterladen
2. Datenbank mit [SQL-Script](https://github.com/hendrik-Sch/SpaceAssault/blob/master/server/initialise%20database%20Space%20Assault.sql) initialisieren
3. [Konfiguration](#configuration) anpassen
4. Terminal öffnen
5. in das Verzeichnis *client* wechseln
  ```sh
  cd client
  ```
6. Dependencies installieren
  ```sh
  npm install
  ```
7. produktive Clientanwendung erzeugen
  ```sh
  npm run build
  ```
8. in das Verzeichnis *server* wechseln
  ```sh
  cd ../server
  ```
9. Dependencies installieren
  ```sh
  npm install
  ```
10. Serveranwendung starten
  ```sh
  npm run start
  ```

## Start des Clients im Entwicklungsmodus
1. Terminal öffnen
2. in das Verzeichnis *client* wechseln
  ```sh
  cd client
  ```
3. Dependencies installieren
  ```sh
  npm install
  ```
4. Clientanwendung starten
  ```sh
  npm run start
  ```

## <a name="configuration"></a>Konfiguration
### Server
Ort der Konfigurationsdatei: `/server/config/dev.json`
| Parameter | Bedeutung |
|---|---|
| http.port | Port, auf den die Serveranwendung horcht und auch den Client bereitstellt |
| websocket | Konfigurationen des Websockets (s. [socket.io](https://socket.io/docs/v4/server-options/) für weitere Konfigurationsmöglichkeiten) |
| websocket.cors | Eine Liste von erlaubten Quell-URLs |
| database | Konfigurationen des Datenbank-Connectors (s. [mysql](https://github.com/mysqljs/mysql#connection-options) für weitere Konfigurationsmöglichkeiten) |
| database.host | Der Hostname des Datenbank-Servers, mit der man sich verbinden möchte (Default: localhost) |
| database.port | Der Port des Datenbank-Servers, mit der man sich verbinden möchte (Default: 3306) |
| database.user | Der MySQL Benutzer |
| database.password | Das Passwort des MySQL Benutzers |
| database.database | Der Name der Datenbank, mit der man sich verbinden möchte. |

### Client
Ort der Konfigurationsdatei: `/client/public/config.json`

**Nach Äderungen der Konfiguration muss die produktive Version der Clientanwendung neu erzeugt werden! (s. Instllation 7.)**

| Parameter | Bedeutung |
|---|---|
| websocketUrl | URL zum Websocket der Server Anwendung inkl. Port |

## Kontakt
Bei Fragen wenden Sie sich bitte an Hendrik Schürmann schuermann11@googlemail.com.
