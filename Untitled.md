$P = \lbrace$
$A\to aA|bA|…zA|aB|bB|cB$
$B \to .C$
$C\to aZ|bZ|…zZ|aC|bC|…zC|aD|bD|cD$
$D\to .E$
$E\to aZ|bZ|…zZ|aE|bE|…zE$
$Z \to @apps4you.eu$


$T=\lbrace a,b,c,d,…,z\rbrace$
$N=\lbrace A,B,C,D,E,Z\rbrace$
$S=A$

$$A \to aA \to amA \to amyB \to amy.C \to amy.rC \to amy.roC \to amy.rotZ \to amy.rot@apps4you.eu$$
$$A\to tA \to tiA\to timB\to tim.C\to tim.kC\to tim.kaC\to tim.kaiD\to tim.kai.E \to tim.kai.mE\to tim.kai.maE\to tim.kai.mayZ \to tim.kai.may@apps4you.eu$$

c) Der dargestellte Benutzerbaum ist nach folgendem Prinzip sortiert.
Aus einer sortierten Benutzerliste wird das mittlere Element als Wurzelknoten des Baumes verwendet. Dadurch teilt sich die Liste in zwei Teile auf. Aus der Liste mit lexikographisch kleineren Einträgen wird nun das mittlere Element entnommen und links unter dem Wurzelknoten als neuer Teilbaum gespeichert. Aus der Liste mit lexikographisch größeren Elementen wird das mittlere Element als rechter Teilbaum des Wurzelknotens gespeichert.
Dieses Vorgehen hat die halbierten Listen erneut in jeweils zwei Teile geteilt, welche nach dem selben Vorgehen unter dem im vorherigen Schritt kreierten Knoten einsortiert werden. Dies kann auch parallel geschehen. Das Vorgehen wird dabei so lange wiederholt, wie es noch einzufuegende Elemente gibt.

Um ein Element im Suchbaum zu finden wird der Baum wie folgt abgesucht. Zuerst vergleichen wir das gesuchte Element mit dem Wurzelknoten lexikographisch. Das gesuchte Element `gero.genz`ist kleiner als `hans.pohl`, daher wird sich nun der linke Teilbaum angeschaut. Dort ist `cora.blau` kleiner als `gero.genz`, also wird der rechte Teilbaum dieses Elements betrachtet. `dorit.krug` ist kleiner als `gero.genz` also wird nun der rechte Teilbaum von `dorit.krug` betrachtet. Dort befindet sich der Eintrag `gero.genz`. Wäre `gero.genz` nicht Teil des Benutzersystems, so würde hier die Suche fehlschlagen, da `dorit.krug` ein Blatt des Baumes ist.
```
public boolean benutzerBaum(BinTree benutzerBaum, String benutzername) {
if(benutzerBaum.getItem()==benutzername)
	return true;
boolean result = false;
if(benutzerBaum.hasLeft()==true) {
	result = benutzerBaum(benutzerBaum.getLeft(),benutzername)
	if(result == true)
		return true;}
if(benutzerBaum.hasRight()==true) {
	result = benutzerBaum(benutzerBaum.getRight(),benutzername)
	if(result == true)
		return true;}
return result;
}
```

d) ```
public Queue fuelleDruckjob(BinTree benutzerBaum, Queue s) {
if(benutzerBaum.isLeaf())
	s.enqueue(benutzerBaum.getItem())
}
```