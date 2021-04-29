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
$#$: Vorbelegungszeichen des Kellers
$N$: Nichtterminalsymbole
$T$: Terminalsymbole
$S \in N$: Start-Nichtterminalsymbol
$P$: Produktionsregeln
### DEA - NEA - reguläre Grammatik (Typ III)
Ein DEA (deterministischer endlicher Automat) ist ein Akzeptor (er erkennt Sprachen) und wird als Vier-Tupel mit $A=(\Sigma,Q,q_0,F)$ beschrieben. Die Übergangsfunktion eines DEA $\delta :Q\times \Sigma \to Q$ kann als Tabelle dargestellt werden. 
Wichtig ist: Eine Kombination aus Eingabesymbol und Zustand führt immer zu *einem* neuen Zustand. Ist dies nicht der Fall, spricht man von einem NEA, einem Nichtdeterministischen endlichen Automaten, da Nichtdeterminismus in Form von zwei möglichen Folgezuständen vorliegt. Ein NEA kann jedoch mithilfe von zusätzlichen Zuständen immer in einen DEA umgewandelt werden, da beide Automaten sogenannte reguläre Sprachen erkennen. Eine Typ-3-Grammatik ein NEA und ein DEA sind also äquivalente Beschreibungsmethoden einer regulären Sprache.
Reguläre Grammatiken lassen sich als Vier-Tupel mit $G=(N,T,S,P)$ beschreiben. Hier gilt für $P$, dass eine Produktion $l \to r$ nur mit $l\in N$ und $r\in NT^+|T^+$ für eine linksreguläre Sprache oder $r\in T^+N|T^+$

## Codierung von Daten
## Verschlüsselung von Daten
## Datenstrukturen und Sortieralgorithmen
## Datenbanken