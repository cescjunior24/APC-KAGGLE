# APC-KAGGLE

<h3> Nom: Francesc Gallego Palomo </h3>

<h3> DATASET: smart grid Stability </h3>

<h3 href="https://www.kaggle.com/pcbreviglieri/smart-grid-stability"> kaggle </h3>


<h2> Resum </h2>

Aquest dataset correspoin a una versió augmentada del "Conjunt de dades simulat d'estabilitat de la xarxa elèctrica", creat per Vadim Arzamasov i donat al Repositori d'aprenentatge automàtic de la Universitat de Califòrnia (UCI).

<h2>Llista d'atributs </h2>


<ul>
    <li>tau1: Reaction time - Energy producer</li>
    <li>tau2: Reaction time - Consumer 1</li>
    <li>tau3: Reaction time - Consumer 2</li>
    <li>tau4: Reaction time - Consumer 3</li>
    <li>p1: Power balance - Energy producer</li>
    <li>p2: Power balance - Consumer 1</li>
    <li>p3: Power balance - Consumer 2</li>
    <li>p4: Power balance - Consumer 3</li>
    <li>g1: Price elasticity coefficient (gamma) - Energy producer</li>
    <li>g2: Price elasticity coefficient (gamma) - Consumer 1</li>
    <li>g3: Price elasticity coefficient (gamma) - Consumer 2</li>
    <li>g4: Price elasticity coefficient (gamma) - Consumer 3</li>
    <li>Maximal real part of the characteristic differential equation root (if positive, the system is linearly unstable).</li>
    <li>g4: Price elasticity coefficient (gamma) - Consumer 3</li>
    <li>System's stability label (categorical: stable / unstable)</li>    
</ul>


<h2>Objectius del dataset</h2>

Volem aprendre si la red elèctrica és estable o no, depèn dels valors que tingui tots els altres atributs.

<h2>Tractament de dades</h2>

Durant aquesta pràctica hem realitzat diferents experiments per de pulir el nostres dataset:

<ul>
    <li>Hem mirat la correlació de les dades i hem vist que els atributs p1,p2,p3,p4 tenien una correlació no gaire bona dintre dels atributs relacionats amb l'equilibri de potència, per tant el que he fet és eliminar-los perquè així augmentariem el rendiment dels nostres models </li>
    <li>El atributs target, que en aquest cas és el atribut stabf, aquest ens dius si és estable o inestable, per tant com que és un atribut que dues opcions le passsat a binari, o sigui le transformat en 0 si és estable i en 1 si és inestable</li>
    <li>El que he fet també abans de treballar amb els models, ha sigut mirar si el nostre dataset tenia valors nulls, en aquest cas no hem obtingut cap valor null, per tant no hem hagut de tractar-los</li>
<ul>
    
    
<h2>Models</h2>
    
| Model | Temps d'execució | Accuracy del test |
|-----------|:------------|:-----------:|
| Regressió Logística | 0.1632 s | 96.7% | 
| MLP |18.164s | 99.8% |
| SVM | 0.9463 s | 95.45% |
| MLP amb millors paràmetres | 20.555s | 99.7% |



