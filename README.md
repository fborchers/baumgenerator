
Baumgenerator 
=============

erstellt am: 7.12.2019  
bearbeitet am: 14.9.2024  
Autoren: Jochen Bauer (`generator.xls`) und Florian Borchers (`makefile`)

Der Baumgenerator dient dem Erstellen von Baumdiagrammen, wie sie in der Wahrscheinlichkeitsrechnung typisch sind. Dabei wird vor allem an die Anwendung in der Schule gedacht. Folgende Parameter können eingestellt werden (`generator.xls`):

 1. Anzahl der Ziehungen (aus der Urne)
 2. Ergebnisse, d.h. die Elemente in der Urne
 3. Anzahlen der Elemente in der Urne
 4. Mit Zurücklegen (ja/nein)
 5. Wahrscheinlichkeiten auf den Pfaden gekürzt (ja/nein)
 6. Ergebnisse gekürzt (ja/nein)


System-Voraussetzungen
----------------------

Der Generator arbeitet mit MS Excel, wobei Open Office ebenfalls funktionieren sollte. Außerdem wird eine TeX-Installation benötigt, weil die Ausgabe des Baumes (das Plotten) mithilfe von PSTricks geschieht. Weitere Hilfsprogramme
  - soffice
  - sed
  - Gnu make
Mithilfe von 
```
make test
```
kann geprüft werden, ob diese Hilfsprogramme gefunden auf der lokalen Version vefügbar sind. 

Anwendung
---------
Das Baumdiagramm wird mit den Voreinstellungen in `generator.xls` ausgegeben. Die Routine erzeugt die Datei `out_baum.pdf`.
```
make pdf
```

In MS Excel (`generator.xls`) werden in den blau hinterlegten Felder die entsprechenden Parameter festgelegt. Excel berechnet automatisch und sofort ("on the fly") den entsprechenden Code innerhalb der Datei. Die fett gedruckten Zeilen werden kopiert und in `baum.tex` eingefügt. Das Wrapper-File `baumgenerator.tex` wird mit 
```
latex baumgenerator.tex
```
übersetzt. Dieser Teil der Anwendung ist in der Make-Routine zusammengefasst. 


Einschränkungen
---------------

Der Generator funktioniert für bis zu vier Ziehungen. Beim Ziehen ohne Zurücklegen wird auch der Fall berücksichtigt, dass eine Sorte bei der letzten Ziehung nicht mehr in der Urne vorhanden ist. Ein Fehler bei der Beschriftung der Pfade tritt auf, wenn ein Element bereits bei der vorletzen Ziehung nicht mehr in der Urne vorhanden ist, z.B. im Fall von zwei roten Kugeln in der Urne bei 4 Ziehungen ohne Zurücklegen. 
