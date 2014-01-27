% EtherApp - App zur Verwaltung von Etherpad Lite 
% Ferdinand Malcher und Martin Stoffers
% 30. Januar 2014


# Einführung

## Etherpad Lite  (EPL)

* Kollaborativer Onlineeditor
* Javascript/Node.js

### Ermöglicht
* Gemeinsames schreiben von Text 
* Export in andere Formate
* Zugriff via HTTP API

### Links 
[http://etherpad.org/](http://etherpad.org/)
[https://github.com/ether/etherpad-lite/](https://github.com/ether/etherpad-lite/)
[http://etherpad.org/doc/v1.3.0/](http://etherpad.org/doc/v1.3.0/)

## Motivation

* Keine Oberfläche zur Administration eines EPL
* Zugriff nur über die HTTP API

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
* Abruf des Pad-Inhalts
* Rücksetzen des Inhalts auf ältere Revision
* Abrufen und Anlegen von Gruppen

## Ausgewählte Features

* Anzeige aller Pads
* Anzeige von Meta-Informationen für einzelne Pads
    * (Benutzer online, Revisionen, Datum , …)
* Anlegen neuer Pads
* Löschen von Pads
* Anzeige des Pad-Inhalts
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
    * Item wird schon Angezeigt

### Bestehend
2) Wie stoppt man die Aktualisierung?

## Datenspeicherung

### Problem
1) Persistente Speicherung zur Verwaltung der Daten

### Lösungsmöglichkeiten
* SharedPreferences
* Sqlite Datenbank

### Lösung
* Sqlite Datenbank mit zwei Tabellen
    * Globale Einstellungen
    * API Liste

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

* Datenbank der App zurücksetzten
* Tabs durch modernere Fragmente ersetzten
* Zeitgesteuertes Update der Padliste
* Festlegen des Textes in einem neuen Pad durch den Benutzer

\begin{center}
\includegraphics[scale=0.15]{inc/etherapp.png}
\end{center}

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
