
Baumgenerator 
=============

erstellt: 7.12.2019
bearbeitet: 9.9.2024
Autor: J. Bauer (generator.xls) und F. Borchers (makefile)

Der Baumgenerator ist gemacht für das Erstellen von Baumdiagrammen, wie sie in der Wahrscheinlichkeitsrechnung typisch sind. Dabei wird vor allem an die Anwendung in der Schule gedacht.


System-Voraussetzungen
----------------------

Der Generator arbeitet mit MS Excel, wobei Open Office ebenfalls funktionieren sollte. Außerdem wird eine TeX-Installation benötigt, weil die Ausgabe des Baumes (das Plotten) mithilfe von PSTricks geschieht. Weitere Hilfsprogramme
  - soffice
  - sed
  - Gnu make


Manuelles Anwenden
------------------

In MS Excel werden in die blau hinterlegten Felder die entsprechenden Angaben gemacht. Excel berechnet automatisch und sofort ("on the fly") den entsprechenden Code. Die fett gedruckten Zeilen werden kopiert und in "baum.tex" eingefügt. Das Wrapper-File "baumgenerator.tex" wird mit 
	latex baumgenerator.tex
übersetzt.