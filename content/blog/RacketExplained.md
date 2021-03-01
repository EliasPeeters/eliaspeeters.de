---
type: post
title: Racket explained
description: Just the important racket stuff
author: Elias Peeters
categories:
  - Racket
tags:
  - Racket
date: 2020-03-01
linktitle: ""
---

# Die Regeln

## Regel 1
Verwende aussagekräftige Namen für Funktionen und Variablen („sprechende Bezeichner“). 

## Regel 2

Dokumentiere den Zweck der Funktion durch einen Satz, der das Resultat der Funktion in Abhängigkeit von ihren Argumenten beschreibt. 

## Regel 3 (1)

Schreibe Beispielanwendungen der Funktion auf, die das Resultat der Funktion mit dem Erwartungswert vergleichen. Die Auswertung der Ausdrücke muss dabei immer den Wahrheitswert #true liefern. 

## Regel 3 (2)

Schreibe Test für Funktionen unter
Verwendung einer der check-...-Prozeduren von Racket auf.

## Regel 4
Definiere für jeden Zusammenhang zwischen Größen, die sich aus der Problembeschreibung ergeben, eine Funktion. 

## Regel 5
Ersetze jede Konstante, deren Bedeutung sich nicht aus dem Kontext ergibt, durch einen sprechenden Variablennamen. 

## Regel 6

Für den Funktionsrumpf
-	ein cond-Skelett mit je einem Frage-Antwort-Paar pro Fall formulieren,
-	für jeden Fall die Bedingung als Frage formulieren,
-	für jeden Fall den Ausdruck für die Berechnung der Antwort ermitteln. 

## Regel 7

1. Analyse: Identifikation der Komponenten, aus denen die Datenstuktur besteht.
2. Beschreibung
3. Definition 

## Regel 8
1. Bestimme die für die Berechnung des Ergebnisses erforderlichen Komponenten der Datenstruktur(en).
2. Schreibe den Selektor jeder Komponente der Datenstruktur(en) in die Funktionsschablone, von deren Wert das Ergebnis der Funktion abhängt.
3. Nimm den Aufruf des Konstruktors in die Schablone mit auf, falls die Funktion eine Datenstruktur als Resultat liefern muss. 

## Regel 9
1. Ergibt die Datenanalyse, dass gemischte Daten zu verarbeiten sind, schreiben Sie zunächst eine Datendefinition der folgenden Form auf:
```rktl
;; Ein s ist entweder
;; - ein t1 oder
;; - ...
;; - ein tn
;; Name: x
```
1. Für eine s-verarbeitende Funktion ist mindestens je ein Testfall für jede Variante von s aufzuschreiben.
2. Seien t1?, . . . , tn? die Prädikate (Erkennungsfunktionen) zu den in s vorkommenden Varianten t1, . . . , tn. Dann ergibt sich die Schablone einer bedingten Funktion (Regel 6) mit diesen Fällen. 

## Regel 10
-	Formuliere einen Vertrag für jede Funktion! (Schreibe ihn als Kommentar vor den Funktionskopf.)
-	Der Vertrag beschreibt:
   - Arten von Daten (Datentypen) der Argumente
   - Art von Daten des Resultats 

```rktl
;; name : argument-typ-1 ... argument-typ-n -> resultat-typ 
```

## Regel 11
Schreibe eine präzise Datendefinition für die zu verarbeitende rekursive Datenstruktur auf. Folge dabei dem im Abschnitt Datendefinition angegebenen Muster.

## Regel 12
Formuliere mindestens einen Test für den
Fall, dass die rekursive Datenstruktur
-	keine Elemente,
-	genau ein Element,
-	mehr als ein Element
enthält.  

## Regel 13
Entwickle eine Funktionsschablone, die der rekursiven Struktur der Daten folgt.
-	Schreibe das Skelett eines cond-Ausdrucks auf mit je einer Frage-Antwort-Klausel für jeden nicht-rekursiven und jeden rekursiven Fall.
-	Notiere dabei für die rekursiven Fälle die passenden Selektionsausdrücke ((first ...), (rest ...)).
-	Dabei ist zu beachten, dass auf den Ausdruck (rest ...), der dem Selbstbezug der Datenstuktur entspricht, die zu entwickelnde Funktion rekursiv anzuwenden ist. 


# Definitionen

## Programm
Ein Programm ist eine Folge von Anweisungen (Befehlen) an eine
Maschine (Rechner, Computer), die von dieser „verstanden“ wird und damit ausgeführt werden kann. 

## Maschinensprache
Die vollständige Liste der Dinge (Befehle), die ein Computer tun kann, kann als seine Maschinensprache (machine language) bezeichnet werden.

## Maschinencode
Interne (ausführbare) Darstellung eines Maschinenprogramms als Bitmuster.

## Assemblersprache
Symbolische, textorientierte Darstellung einer Maschinensprache.
Ihre Merkmale sind:
- Die Liste der Befehle ist dieselbe wie die der Maschinensprache.
- Symbolische Namen für Befehle
- Dezimalzahlen, symbolische Adressen

## Quellprogramm 
Programm in Hochsprache.

## Syntax
Syntax legt fest,
-	welche Sprachelemente und -konstrukte es gibt und
-	wie mit ihrer Hilfe korrekte Sätze in der Sprache formuliert werden können.
-	Syntax = Menge von Regeln, die die Struktur von Programmen bestimmen

## Semantik
Semantik legt fest,
-	welche Bedeutung syntaktisch korrekte Sätze haben und
-	welche Wirkung jedes Sprachelement oder -konstrukt im Programmablauf hervorruft.
-	Semantik = Menge von Verhaltensregeln, die die Funktionsweise von Programmen bestimmen
-	orientiert sich bei funktionalen Programmiersprachen an der Mathematik

## Pragmatik
Pragmatik
-	Intention des Programmierers mit einem Programm
-	Nutzen der Ausdrucksmöglichkeiten einer Programmiersprache für die Formulierung von Lösungen

## Bedingte Funktion
Eine Funktion wird bedingt genannt, wenn für die Ermittlung ihres Resultats eine Fallunterscheidung erforderlich ist.

## Akkumulierende Parameter  
Akkumulierende Parameter sind die Teile einer Funktion, die die Effizienz durch Verschachtelung und Rekursion einschränken.
