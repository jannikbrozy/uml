# Klassendiagramme

Ein Klassendiagramm zeigt den Aufbau einer Entitaet.\
Diese besteht aus Eigenschaften und Funktionen.

Bsp. Auto\
Das Auto hat eine Farbe wie Blau oder Rot, eine Anzahl an Sitzen usw.\
Ein Auto kann gestartet und gestoppt werden.

Als Klassendiagramm wuerde das Auto so dargestellt werden.

Sowohl Funktionen, als auch die Eigenschaften, haben einen sogenannten Modifier.
Wenn eine Instanz dieser Klasse erstellt wird, gibt der Modifier an, ob auf die Eigenschaft oder Funktion
zugegriffen werden kann. 

Aufbau ist folgender:

modifier nameDerEigenschaft: Datentyp

modifier sind "+ - #"\
\+ bzw. public kann von ueberall zugegriffen werden\
\- bzw. private kann nur von innerhalb der Klasse zugegriffen werden.\
\# bzw. protected kann nur von der Klasse selbst oder erbenden Klassen zugegriffen werden 

    AUTO
-------------
- farbe: string
- anzahlSitze: int
-------------
+ setFarbe(string) : void
+ getFarbe() : string

## Generieren des Pseudocodes

erstellen einer variable

Datentyp variablenName = wert;

parameter sind optional
modifier Datentyp nameDerEigenschaft(parameter)
{
}
 
Die Funktion setFarbe wird so dargestellt\
+ setFarbe(string) : void

public void setFarbe(string farbe)
{
    this.farbe = farbe;
    // this wird verwendet, 
    // da die uebergebene variable farbe, 
    // genau so heisst wie oben genannte eigenschaft farbe.
    // this ist immer die Klasse selbst.
    // wenn eine Instanz der Klasse Auto erstellt wird, 
    // bezieht sich this auf die Instanz
}

public string getFarbe()
{
    // this wird hier eigentlich nicht benoetigt
    return this.farbe;
}


# Scopes einer Klasse
Es gibt 2 Arten von Scopes (Es gibt noch mehr, aber die muessen hier nicht erklaert werden)
- Funktion-Scope
- Global-Scope

## Global-Scope 
Zugriff auf die Eigenschaften und Funktion der Klasse

## Funktion-Scope 
Zugriff auf die Eigenschaften, Funktion der Klasse und
der in der Funktion uebergebenen Parameter

```csharp
public class Auto
{
    private string farbe;
    private int anzahlSitze;

    public Auto(string farbe)
    {
    }

    public string getFarbe()
    {
        // der Methode werden keine Parameter mitgegeben.
        // Uebrig bleiben die Eigenschaften und Funktionen
        // aus dem Global-scope
        // bzw. die Methode setFarbe(string)
        // und die Eigenschaften farbe und anzahlSitze
        return this.farbe;
    }

    public void setFarbe(string farbe)
    {
        // Der Methode wird die variable farbe mitgegeben
        // aus dem Global-Scope bekommen wird auch noch
        // Zugriff auf die Eigenschaft farbe, anzahlSitze 
        // und der Methoden setFarbe und getFarbe

        // jetzt stehen uns folgende variablen zur verfuegung.
        // global-scope: farbe und anzahlSitze
        // funktion-scope: farbe
        // da die variable aus dem global-scope genau so
        // heisst, wie die variable aus dem funktion-scope
        // muss hier mit this unterschieden werden

        // die variable farbe aus dem global-scope
        // soll auf den wert der variable farbe
        // aus dem funktion-scope gesetzt werden
        this.farbe = farbe;
    }
}
```
