% EtherApp - App zur Verwaltung von Etherpad Lite 
% Ferdinand Malcher und Martin Stoffers
% 30. Januar 2014


# Einführung

## Etherpad Lite  (EPL)

* Kollaborativer Onlineeditor
* Javascript/Node.js

### Ermöglicht
* Gemeinsames Schreiben von Text über ein Webfrontend
* Export in andere Formate
* Administrativer Zugriff via HTTP-API

### Links 
[http://etherpad.org/](http://etherpad.org/)
[https://github.com/ether/etherpad-lite/](https://github.com/ether/etherpad-lite/)
[http://etherpad.org/doc/v1.3.0/](http://etherpad.org/doc/v1.3.0/)

## Motivation

* Keine Oberfläche zur Administration eines EPL
* Zugriff nur über die HTTP-API

\begin{center}
\includegraphics[scale=0.14]{inc/etherpad.png}
\end{center}

# Zielstellung

## Überblick
\begin{center}
\huge{\textbf{Komfortabler Zugriff auf administrative Bestandteile des EPL via App}}
\end{center}


## Features der API

* Abruf aller Pads
* Abruf von Meta-Informationen für einzelne Pads
    * (Benutzer online, Revisionen, Datum , …)
* Anlegen neuer Pads
* Löschen von Pads
* Ersetzen des Textes in einem Pad
* Abruf des Pad-Inhalts
* Abrufen und Anlegen von Gruppen
* Anlegen und Verwalten von Autoren
* Anlegen und Verwalten von Sessions

## Ausgewählte Features

* Anzeige aller Pads
* Anzeige von Meta-Informationen für einzelne Pads
    * (Benutzer online, Revisionen, Datum , …)
* Anlegen neuer Pads
* Löschen von Pads
* Anzeige des Inhalts eines Pads
* Anzeige und Verwaltung von Gruppen
* Rücksetzen des Inhalts auf ältere Revision

### Ergänzend
* Verwaltung mehrerer EPL-Instanzen und Profilverwaltung
* Teilen der Pad-URL über soziale Dienste und E-Mail


# Probleme

## Listen

### Problem
1) Vordefinierte Adapter für Listen nicht ausreichend

### Lösung
* Von BaseAdapter abgeleitet
    * PadlistAdapter
    * GrouplistAdapter
    * APIlistAdapter
* Eigene Item-Klassen erstellt
    * APIlistItem
    * GrouplistItem
    * PadlistItem

## Asynchrones Laden der API

### Probleme
1) Abrufen aller Informationen für alle Pads dauert zu lange
2) Aktualisierung immer, wenn Item in Liste sichtbar wird

### Lösung
1) Implementierung eines Loaders mit AsyncTask
    * Abruf erst beim Anlegen eines Items
    * Item wird schon angezeigt

### Bestehend
2) Wie stoppt man die Aktualisierung?

## Datenspeicherung

### Problem
1) Persistente Speicherung zur Verwaltung der Daten

### Lösungsmöglichkeiten
* SharedPreferences
* SQLite Datenbank

### Lösung
* SQLite-Datenbank mit zwei Tabellen
    * Globale Einstellungen
    * API-Liste

## Threads

### Problem
* Blockieren der Activity
    * Pad erstellen/löschen
    * Gruppe erstellen/löschen
    * Inhalt eines Pads abrufen

### Lösung
* Auslagern in eigene AsyncTasks
    * Noch nicht implementiert

# Demo

## 

\begin{center}
\includegraphics[scale=0.15]{inc/IMG_4425.jpg}
\end{center}

# Ausblick

## Wie kann es weiter gehen

* Datenbank der App zurücksetzen
* Tabs durch Fragmente ersetzen (Deprecated)
* Zeitgesteuertes Update der Padliste
* Festlegen des Textes in einem neuen Pad durch den Benutzer
* Teilen der Pad-URL über soziale Netze, Chat und Email 
* Benutzerdefinierte Einstellungen zum Appverhalten
* Verwaltung von Revisionen

### Speziellere Funktionen

* Anlegen von Pads innerhalb einer Gruppe
* Anzeige und Verwaltung von Autoren


## Links

\begin{center}
\includegraphics[scale=0.2]{inc/launcher.png}
\\[2em]
[ \url{http://etherapp.de/} ]
\\[1em]
[ \url{https://github.com/EtherApp/EtherAppDoc/} ]
\end{center}

## Fragen

\begin{center}
\huge{\textbf{Noch Fragen?}}
\\[3em]
\large{\textrm{"I'm an egotistical bastard, and I name all my projects after myself. First Linux, now git."}}
\end{center}
\flushright{\footnotesize{Torvalds, Linus (2007-06-14)}}
