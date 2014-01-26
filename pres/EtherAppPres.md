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

* Keine Oberfläche zur Administration eine EPL
* Zugriff nur über die HTTP API

# Zielstellung

## Überblick

* Erstellung einer App die den administrativen Zugang ermöglicht

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
* Verwaltung mehrerer EPL-Instanzen und Profilverwaltung
* Rücksetzen des Inhalts auf ältere Revision
* Teilen der Pad-URL über soziale Dienste und E-Mail

# Demo

## 

\begin{center}
\includegraphics[scale=0.15]{inc/IMG_4425.jpg}
\end{center}

# Probleme

## Listen

    %s/^#[^#] \?\(.\+\)/\\section{\1}/g

\begin{center}
\includegraphics[scale=0.3]{inc/etherapp.png}
\end{center}

## Asynchrones Laden der API

* AsyncLoader
* \texttt{Text in spezieller Schrift}

## Datenspeicherung

* sql
* sharedpreferences

# Ausblick

## Wie kann es weiter gehen

* neue Ideen

## Fragen

\begin{center}
\huge{\textbf{Noch Fragen?}}
\\[3em]
\large{\textrm{"I'm an egotistical bastard, and I name all my projects after myself. First Linux, now git."}}
\end{center}
\flushright{\footnotesize{Torvalds, Linus (2007-06-14)}}
