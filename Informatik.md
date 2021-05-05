# Informatik
## Automaten und Sprachen
### Symbolerklärungen
$\Sigma$: Endliches, nichtleeres Eingabealphabet
$Q$: Endliche, nicht leere Menge an Zuständen
$q_0 \in Q$: Startzustand
$F\subset Q$: Endliche, nicht leere Menge an Endzuständen
$\Omega$: Endliches Ausgabealphabet
$\delta$: Zustandsübergangsfunktion
$\lambda$: Ausgabefunktion
$K$: Kelleralphabet
$\#$: Vorbelegungszeichen des Kellers
$N$: Nichtterminalsymbole
$T$: Terminalsymbole
$S \in N$: Start-Nichtterminalsymbol
$P$: Produktionsregeln
### DEA - NEA - reguläre Grammatik (Typ III)
Ein DEA (deterministischer endlicher Automat) ist ein Akzeptor (er erkennt Sprachen) und wird als Fünf-Tupel mit $A=(\Sigma,Q,q_0,F,\delta)$ beschrieben. Die Übergangsfunktion eines DEA $\delta :Q\times \Sigma \to Q$ kann als Tabelle dargestellt werden. 
Wichtig ist: Eine Kombination aus Eingabesymbol und Zustand führt immer zu *einem* neuen Zustand. Ist dies nicht der Fall, spricht man von einem NEA, einem Nichtdeterministischen endlichen Automaten, da Nichtdeterminismus in Form von zwei möglichen Folgezuständen vorliegt. Ein NEA kann jedoch mithilfe von zusätzlichen Zuständen immer in einen DEA umgewandelt werden, da beide Automaten sogenannte reguläre Sprachen erkennen. Eine Typ-3-Grammatik ein NEA und ein DEA sind also äquivalente Beschreibungsmethoden einer regulären Sprache.
Reguläre Grammatiken lassen sich als Vier-Tupel mit $G=(N,T,S,P)$ beschreiben. Hier gelten für eine Produktion $l \to r$ folgende Regeln:
1. die linke Seite darf nur ein Nichtterminalsymbol enthalten: $l\in N$ 
2. die rechte Seite darf nur ein oder mehrere Terminalsymbole oder 
	1. ein Nichtterminalsymbol gefolgt von ein oder mehreren Terminalsymbolen $r\in NT^+|T^+$ für eine linksreguläre Sprache oder 
	2. ein oder mehreren Terminalsymbolen gefolgt von einem Nichtterminalsymbol $r\in T^+N|T^+$ für eine rechtsreguläre Sprache.
Das bedeutet, dass ein Wort einer regulären Sprache nur in eine Richtung wächst.
### Mealy-Automat
Ein Mealy-Automat ist ein Transduktor (Übersetzer). Er wird als Sechs-Tupel mit $A=(\Sigma,\Omega,Q,q_0,\delta,\lambda)$beschrieben. Dieser Automat besitzt keine Endzustände.
Die Zustandsübergangsfunktion des Mealy-Automaten ist identisch zu der des DEA. Auch hier gilt: Eine Kombination aus Eingabesymbol und Zustand führt immer nur zu *einem* Nachfolgezustand. Hinzu kommt bei diesem Automaten eine Ausgabefunktion, die aus einer Kombination aus Zustand und Eingabezeichen zu einem Ausgabezeichen führt: $\delta: Q\times\Sigma\to\Omega$
### Keller-Automat
Ein Keller-Automat ist wie ein DEA ein Akzeptor und kann als 7-Tupel mit $A=( \Sigma,Q,q_0,K,\#,F,\delta)$ beschrieben werden. Der einzige Unterschied zum DEA ist die Erweiterung um einen Keller. In ihm können Symbole des Kelleralphabetes gespeichert werden und wieder entnommen werden. Zustandsübergänge werden durch Kombinationen aus Kellerzeichen und Eingabesymbol bestimmt. Es wird verbrauchend vom Keller gelesen.
Die Sprachen, die durch den Kellerautomaten erkannt werden können gehören der Klasse der deterministischen kontextfreien Sprachen an. Sie sind eine echte Teilmenge der kontextfreien Sprachen. 
**Kontextfreie Sprachen können nur durch nichtdeterministische Kellerautomaten vollständig erkannt werden.**
Eine kontextfreie Sprache kann ebenfalls durch eine Typ-II-Grammatik beschrieben werden.
Die Produktionen $l \to r$ dieser Grammatik müssen folgende Eigenschaften aufweisen:
1. $l\in N$
2. Für $r$ ist jede Kombination aus Terminalen und Nichtterminalen möglich.

## Codierung von Daten
### Fehlerkorrektur
#### Hammingcodes
Hammingcodes sind fehlertolerante, optimale Codes.
Beispiel: Der 7,4-Hammingcode besteht aus 4 Datenbits und 3 Paritybits. Er hat den Hammingabstand 3 und ist somit ein-Fehler-korrigierend.
| D   | D   | D   | P   | D   | P   | P   |
| --- | --- | --- | --- | --- | --- | --- | 
| 7   | 6   | 5   | 4   | 3   | 2   | 1   |
| D   | /   | D   | /   | D   | /   | P   |
| D   | D   | /   | /   | D   | P   | /   |
| D   | D   | D   | P   | /   | /   | /   |
Die Paritybits befinden sich an Stelle 1,2 und 4.
Paritybit 1 steht für alle Datenbits, deren Position binär codiert an der ersten Stelle (least significant bit) eine eins hat (3,5,7).
Paritybit 2 steht für alle Datenbits, deren Position binär codiert an der zweiten Stelle (sencond least significant bit) eine eins hat (2,6,7).
Paritybit 3 steht für alle Datenbits, deren Position binär codiert an der dritten Stelle (third least significant bit) eine eins hat (5,6,7).

Tritt ein Fehler auf, so geben die Paritybits binär codiert die Position des Fehlers an, wenn man einen Fehler als 1 und ein korrektes Bit als 0 wertet.
Sind die Bits also wie folgt gesetzt:
P1 falsch, P2 richtig, P3 falsch, so wäre die Position des Fehlers 100, also 4.
## Verschlüsselung von Daten
### Symmetrische Verfahren
Bei symmetrischen Verfahren wird der selbe Schlüssel zur Ver- und  Entschlüsselung verwendet. Daher muss dieser Schlüssel kommuniziert werden.
| Vorteile                                                                           | Nachteile                          |
| ---------------------------------------------------------------------------------- | ---------------------------------- |
| schneller, weniger rechenintensiv, kleinere Schlüssellänge bei gleicher Sicherheit | Schlüssel muss kommuniziert werden |
### Asymmetrische Verfahren
Bei einem asymmetrischen Verfahren gibt es zwei Schlüssel, einen sogenannten öffentlichen Schlüssel und einen privaten Schlüssel. Der öffentliche Schlüssel kann verteilt werden. Mit ihm können andere Personen Daten verschlüsseln, die nur mit dem zugehörigen privaten Schlüssel entschlüsselt werden können.
| Vorteile                       | Nachteile                                                                        |
| ------------------------------ | -------------------------------------------------------------------------------- |
| kein Schlüsseltausch notwendig | deutlich größere Schlüssellänge und Rechenaufwand für gleichbleibende Sicherheit |
### Hybridverfahren
Um die Nachteile beider Verfahren auszugleichen kann ein Hybridverfahren genutzt werden. Hierzu wird mithilfe eines Asymmetrischen Verfahrens ein Session-Key (Sitzungsschlüssel) übertragen, mit dem für die Dauer der Sitzung alle übertragenen Daten symmetrisch verschlüsselt werden.
### Monoalphabetisch
Monoalphabetische Verfahren besitzen nur ein Geheimtextalphabet.
Beispiel: Caesar, Vigenere, AES, DES
### Polyalphabetisch
Polyalphabetische Verfahren besitzen mehrere Geheimtextalphabete.
Beispiel: Vigenere
### Transposition
Ein Buchstabe bleibt was er ist, jedoch nicht an seinem ursprünglichen Ort.
-> Tauschchiffren
### Substitution
Ein Buchstabe bleibt wo er ist, jedoch nicht was er ist.
-> Caesar
### Blockchiffren
Blockchiffren verschlüsseln nicht einzelne Symbole, sondern Blöcke von Daten.
Beispiele sind DES (56bit) oder AES.
Bei Blockchiffren werden verschiedene Betriebsmodi unterschieden, also wie ein Block die Verschlüsselung des nächsten beeinflusst.
### Kryptoanalyse
In der Kryptoanalyse gibt es verschiedene Methoden:
Brute-Force: Systematisches Durchprobieren von Schlüsseln
Dictionary-Attack: Wörterbuchangriffe um schwache Passwörter herauszufinden
Ist die Art der Verschlüsselung bekannt, so lassen sich weitere Methoden anwenden.
Bei Caesar ist z.B. eine simple Häufigkeitsanalyse möglich, da jeder Klartextbuchs
## Datenstrukturen und Sortieralgorithmen
### Abstrakte Datentypen
#### Schlange
Eine Schlange hat einen Kopf und ein Ende. Sie besteht aus beliebig vielen Knoten, welche jeweils den nächsten Knoten verknüpfen. Hinten kann etwas an die Schlange angefügt werden (`void enqueue(Object x)`) und vorne ein Element entfernt werden (`Object dequeue()`), es besteht also das FIFO-Prinzip (First-In-First-Out). Einzelne Positionen sind nicht addressierbar.
#### Stapel
Auf einen Stapel kann oben beliebig viel gelegt werden (`void push(Object x)`). Eine Entnahme entfolgt ebenfalls von oben (`Object pull()`), es besteht also das FILO-Prinzip (First-In-Last-Out), eine Liste, dessen Elemente auf einen Stapel gelegt und wieder entnommen wird, liegt also am Ende in umgekehrter Reihenfolge vor. Einzelne Positionen sind auch hier nicht addressierbar.
#### Dynamische Reihung
Eine dynamische Reihung ähnelt der statischen Reihung, hat jedoch keine feste Länge. Es können Elemente von bestimmten Positionen geholt oder eingefügt werden, hinten angefügt werden oder von vorne, bzw. hinten entnommen werden.
#### Binärbaum
Ein Binärbaum besteht aus einem Knoten, der ein Objekt speichert und auf der linken und rechten Seite einen Teilbaum speichern kann. Er kann beliebig viele Ebenen haben, jedoch immer nur zwei "Kinderbäume".
##### Traversierungen
Traversierung beschreibt das systematische Absuchen eines Baumes. Es gibt drei Arten:
Preorder: Ein Knoten wird vor seinen Kindern durchsucht.
In-Order: Ein Knoten wird zwischen seinen Kindern durchsucht.
Postorder: Ein Knoten wird nach seinen Kindern durchsucht.
### Suchmethoden
#### Binärsuche
Aus einer sortierten Reihung wird das mittlere Element entnommen. Entspricht dieses Element nicht dem Gesuchten, wird geprüft, ob es größer als das Gesuchte ist.
1. Wenn ja, dann wird das Verfahren mit der größeren Hälfte der Reihung wiederholt.
2. Wenn nein, dann wird das Verfahren mit der kleineren Hälfte wiederholt.
Für das Worst-Case-Szenario liegt die Zeitkomplexität bei $O(\log n)$
#### Lineare Suche
Eine Reihung wird von vorne bis hinten nach dem gesuchten Element durchsucht.
Die Zeitkomplexität liegt bei $O(n)$
### Sortieralgorithmen
#### 
## Datenbanken
### SQL
#### Wichtige Befehle
````SQL
SELECT [DISTINCT | ALL] * | spalte1 [AS alias 1], spalte2 [AS alias 2], ..., spalten [AS alias n]

FROM tabelle1, tabelle2, ..., tabelle m

[WHERE bedingung1 (AND | OR) bedingung2 ... (AND|OR) bedingung k]

[GROUP BY spalte1 , spalte2 , ... , spalte l]

[HAVING gruppenBedingung1 (AND | OR) gruppenBedingung2 ... (AND | OR) gruppenBedingung s]

[ORDER BY spalte1 [ASC | DESC], spalte2 [ASC | DESC], ..., spalte t [ASC | DESC]]

[LIMIT anzahl]
````
Rechenoperationen:
```SQL
+, -, *, /
```
Vergleichsfunktionen:
```SQL
=
!=
>
<
>=
<=
NOT
LIKE (mit den Platzhaltern _ und %)
BETWEEN
IN
IS NULL
```
Aggregatfunktionen:
```SQL
AVG( ), COUNT( ), MAX( ), MIN( ), SUM( )
```
#### Normalformen und Abhängigkeiten
Abhängigkeiten:
- Ein Merkmal A ist *funktional abhängig* von einem Merkmal S, wenn zu jedem möglichen Wert von S genau ein Wert aus A existiert. $S\to A$
- Ein Attribut C ist von einem Attribut A *transitiv abhängig*, wenn es ein Attribut B gibt mit $A\to B\to C$. Dabei darf A nicht funktional abhängig von B sein.
NF1:
- Daten sind atomar
NF2:
- Einfüge-, Lösch-, und Änderungsanomalien durch Vermeidung von Redundanzen verhindern
- Alle Attribute, die funktional abhängig von einem Teil des Primärschlüssels, aber nicht voll funktional abhängig vom gesamten Primärschlüssel sind, werden aus der Tabelle entfernt und in eine neue ausgelagert.
- Besteht der Primärschlüssel nur aus einem Attribut, so liegt bei jeder Relation, die sich in 1NF befindet, zwangsläufig die 2NF vor.
NF3:
- Ein Datenbankschema ist in der 3. Normalform, wenn es in der 2NF ist und es zusätzlich kein Nichtschlüsselattribut gibt, das transitiv abhängig von einem Schlüsselattribut ist.

#### ER-Modell
Ein Entity-Relation-Modell stellt Entitäten und Relationen graphisch dar. In einem ER-Diagramm 
## Datenschutz
Grundlegende Prinzipien beim Sammeln von personenbezogenen Daten:
- Prinzip der Verhältnismäßigkeit
- Prinzip der Zweckbindung
- Prinzip der Transparenz
-> Verbotsprinzip: Ich darf Daten nicht ohne Erlaubnis oder gegen Widerspruch sammeln.