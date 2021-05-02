# Klassendiagramme

Ein Klassendiagramm zeigt den Aufbau einer Entitaet.
Diese besteht aus Eigenschaften und Funktionen.

Bsp. Auto
Das Auto hat eine Farbe wie Blau oder Rot, eine Anzahl an Sitzen usw.
Ein Auto kann gestartet und gestoppt werden.

Als Klassendiagramm wuerde das Auto so dargestellt werden.

Sowohl Funktionen, als auch die Eigenschaften, haben einen sogenannten Modifier.
Wenn eine Instanz dieser Klasse erstellt wird, gibt der Modifier an, ob auf die Eigenschaft oder Funktion
zugegriffen werden kann. 

Aufbau ist folgender:

modifier nameDerEigenschaft: Datentyp

modifier sind "+ - #"\
\+ kann von ueberall zugegriffen werden\
\- kann nur von innerhalb der Klasse zugegriffen werden.\
\# Nur erbende Klassen koennen auf diese Eigenschaft oder Funktion zugreifen.\


    AUTO
-------------
- farbe: string
- anzahlSitze: int
-------------
+ setFarbe(string) : void

## Generieren des Pseudocodes

erstellen einer variable

Datentyp variablenName = wert;

modifier Datentyp nameDerEigenschaft(parameter)
{
}
