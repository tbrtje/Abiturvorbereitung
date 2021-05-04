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

## Verschlüsselung von Daten
## Datenstrukturen und Sortieralgorithmen
### Suchmethoden
#### Binärsuche
Aus einer sortierten Reihung wird das mittlere Element entnommen. Entspricht dieses Element nicht dem Gesuchten, wird geprüft, ob es größer als das Gesuchte ist.
1. Wenn ja, dann wird das Verfahren mit der größeren Hälfte der Reihung wiederholt.
2. Wenn nein, dann wird das Verfahren mit der kleineren Hälfte wiederholt.
Für das Worst-Case-Szenario liegt die Zeitkomplexität bei $O(\log n)$
#### Lineare Suche
Eine Reihung wird von vorne bis hinten nach dem gesuchten Element durchsucht.
Die Zeitkomplexität liegt bei $O(n)$
## Datenbanken