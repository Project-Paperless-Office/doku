# Umsetzung
## Benutzer- und Inhaltsverwaltung
### Projektverwaltung
	Die Datenhaltung im Projekt erfolgt in einer MySQL-Datenbank. Legt ein Nutzer ein neues Projekt an, werden Projektname, Speicherort der PDF-Dokumente und der Besitzer des Projekts gespeichert. Auf der Projektverwaltungsseite können zusätzliche Bearbeiter zum Projekt hinzugefügt oder aus diesem entfernt werden. Außerdem kann der Nutzer Projekte löschen oder diese zu Favoriten machen, sodass sie auf der Startseite priorisiert angezeigt werden.
	Um eine PDF-Datei zu bearbeiten, kann diese in der Projektverwaltung ausgewählt werden. Der Server gibt die Datei dann zum Download frei und erzeugt einen Link, mit welchem die PDF automatisch mit Microsoft Edge geöffnet wird. Microsoft Edge wurde als Standardprogramm für die PDF-Bearbeitung ausgewählt, weil es eine sehr gute Unterstützung für Stifteingaben bietet und auf den meisten Microsoft-Geräten vorhanden sein sollte.
### Synchronisationsprogramm
	Nachdem die Datei geändert wurde, kann sie im Standard-Downloadverzeichnis abgespeichert werden. Dort überprüft ein in Java geschriebenes Hintergrundprogramm das Dokument alle 10 Minuten auf Änderungen. Falls die Datei geändert wurde, wird sie automatisch hochgeladen und in der Datenbank aktualisiert.	
### Benutzerverwaltung
	Jedes Projekt verwaltet eine Liste von Nutzern, die das Projekt bearbeiten dürfen. Der Projektbesitzer kann auf der Projektverwaltungsseite neue Bearbeiter zum Projekt hinzufügen oder bereits bestehende wieder entfernen.
	
## Analyse der PDF-Dokumentengruppe
	Die Analyse der PDF-Dokumente übernimmt das Java-Programm, welches bereits Thema der Projektarbeit "Wie auch immer die hieß" im Modul "Software Engineering" war. Zur Referenz befindet sich eine Kopie der Arbeit  Das Programm überprüft mehrere gleichartige PDF-Dateien. Gleichartig heißt, dass die Inhalte der Dokumente immer gleich strukturiert sind und sich zusammengehörige Informationen immer an der gleichen Stelle im Dokument befinden. Solche Dateien werden normalerweise automatisch generiert. (Wollen wir Sporer hier auch unsere Beispiel-PDFs geben, falls die auf CD passen?) Das Java-Programm vergleicht alle Zeichenketten, die an ungefähr denselben Koordinaten im PDF-Dokument stehen und weißt ihnen sogenannte Attribute zu. Der Nutzer kann diese Attribute übernehmen oder entfernen, ihnen Namen zuordnen und die Attributwerte mithilfe von regulären Ausdrücken weiter filtern.
	
## Datensicherung und -wiederherstellung
	Über die Backup-Funktion kann der Nutzer die Dokumente wieder herunterladen und lokal abspeichern. Später kann dieses Backup wieder in ein vorhandenes Projekt eingespielt werden. Außerdem wird ein Backup-Verlauf angelegt, der alle Backup- und Wiederherstellungsvorgänge protokolliert.