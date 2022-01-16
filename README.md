# APC-KAGGLE

<h3> Nom: Francesc Gallego Palomo </h3>

<h3> DATASET: smart grid Stability </h3>

https://www.kaggle.com/pcbreviglieri/smart-grid-stability

<h2> Introducció </h2>

Aquest dataset correspoin a una versió augmentada del "Conjunt de dades simulat d'estabilitat de la xarxa elèctrica", creat per Vadim Arzamasov i donat al Repositori d'aprenentatge automàtic de la Universitat de Califòrnia (UCI).

<h2>Llista d'atributs </h2>


<ul>
    <li>tau1: Temps de reacció - Productor d'energia</li>
    <li>tau2: Temps de reacció - Consumidor 1</li>
    <li>tau3: Temps de reacció - Consumidor 2</li>
    <li>tau4: Temps de reacció - Consumidor 3</li>
    <li>p1: Balanç de potència - Productor d'energia</li>
    <li>p2: Balanç de potència - Consumidor 1</li>
    <li>p3: Balanç de potència - Consumidor 2</li>
    <li>p4: Balanç de potència - Consumidor 3</li>
    <li>g1: Coeficient d'elasticitat preu (gamma) - Productor d'energia</li>
    <li>g2: Coeficient d'elasticitat-preu (gamma) - Consumidor 1</li>
    <li>g3: Coeficient d'elasticitat-preu (gamma) - Consumidor 2</li>
    <li>g4: Coeficient d'elasticitat-preu (gamma) - Consumidor 3</li>
    <li>stab: Part real màxima de l'arrel característica de l'equació diferencial (si és positiva, el sistema és linealment inestable).</li>
    <li>stabf: Etiqueta d'estabilitat del sistema (categòric: estable / inestable)</li>    
</ul>


<h2>Objectius del dataset</h2>

Volem aprendre si la red elèctrica és estable o no, depèn dels valors que tingui tots els altres atributs.

<h2>Tractament de dades</h2>

Durant aquesta pràctica hem realitzat diferents experiments per de pulir el nostres dataset:

<ul>
    <li>Hem mirat la correlació de les dades i hem vist que els atributs p1,p2,p3,p4 tenien una correlació no gaire bona dintre dels atributs relacionats amb l'equilibri de potència, per tant el que he fet és eliminar-los perquè així augmentariem el rendiment dels nostres models </li>
    <li>El atributs target, que en aquest cas és el atribut stabf, aquest ens dius si és estable o inestable, per tant com que és un atribut que dues opcions le passsat a binari, o sigui le transformat en 0 si és estable i en 1 si és inestable</li>
    <li>El que he fet també abans de treballar amb els models, ha sigut mirar si el nostre dataset tenia valors nulls, en aquest cas no hem obtingut cap valor null, per tant no hem hagut de tractar-los</li>
    <li>Treure l'atribut stab, ja que té una directe relació amb el nostre atribut target stabf, ja que si un valor de stab és positiu significa que el resultat de stabf serà inestablle, i el treiem obviament perquè això ens portaria problemes a la hora de classificar les dades</li>
</ul>
    
    
<h2>Resultats dels Models entrenats</h2>

| Model | Temps d'execució | Accuracy del test |
|-----------|:------------|:-----------:|
| Regressió Logística | 0.1181 s | 81,4% | 
| MLP |21.742s | 97,7%|
| SVM | 0.9303 s | 95.58% |
| MLP amb millors paràmetres | 23.292s | 97.80% |


<h2>Conclusions</h2>

Un cop que ja hem obtingut els nostres resultats de les prediccions del set de test, podem veure que els nostres models implementats per aquesta base de dades estan funcionantn molt bé, ja que estem obtenint uns valors de accuracy de més del 90%.

M'ha sorprès molt que una base de dades com aquesta amb una correlació força normal, pugui tenir una classificació molt bona, també haig de dir que el SVM classifica bé amb la BD reduïda però amb una quantitat menor de 10000 dades, el resultat es veu bastant reduït, amb un accuracy sobre el 60%.

Com es pot veure en la taula, el pitjor dels casos és la regressió logistica, que ens ha donat un accuracy força bo, però és el més baix dels 4 models. En canvim el millor model amb l'accuracy més alt ha sigut el MLP amb millors paràmetres, ja que ens ha donat un resultat de 97.8%, però el temps d'execució d'aquest model és força lent ja que el learning rate l'hem baixat bastant i triga molt en fer les iteracions, tot i així amb el resultat que hem obtingut podem dir que aquest model per classificar les dades val molt la pena.

També vaig provar de escalar les dades per tal d'obtenir millor resultats, però com heu pogut veure en les execucions del codi, la diferència de resultats no varia molt, per tant vaig decidir plasmar els resultats sense les dades escalades.


