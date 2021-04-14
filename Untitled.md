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
Aus einer sortierten Benutzerliste wird das mittlere Element als Wurzelknoten des Baumes verwendet. Dadurch teilt sich die Liste in zwei Teile auf. Aus der Liste mit lexikographisch kleineren Einträgen wird nun das mittlere Element entnommen und links unter dem Wurzelknoten als neuer Teilbaum gespeichert. Aus der Liste mit  Dieses Vorgehen hat die halbierte Liste erneut in zwei Teile geteilt, von denen wieder aus der Liste mit lexikographisch kleineren Einträgen das mittlere Element entnommen werden kann und links unter dem im vorherigen Schritt kreierten Knoten einsortiert wird. Dieses Vorgehen wird so lange wiederholt, bis die geteilte Liste keine Elemente mehr enthält. Dann kann mit den lexikographisch größeren Teilen der Listen weitergearbeitet werden. Ausgehend von der im ersten Schritt übrig gebliebenden Liste wird die das mittlere Element halbiert und 