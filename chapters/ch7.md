
# Chapitre VII — Qu'est-ce qu'une direction ?

> **Question.** Un objet libre conserve-t-il quelque chose qui mémorise *où il va* — et peut-on définir cette chose sans jamais parler de coordonnées ?

Ce chapitre est plus algébrique que les précédents, et c'est voulu : nous allons voir le théorème de Noether *fonctionner*, pièce par pièce. Le plan, pour ne jamais se perdre :

1. Donner un sens mathématique précis à « l'univers est le même partout » : un opérateur $`T`$, et une équation, $`TL = LT`$.
2. En tirer mécaniquement une quantité conservée $`P`$ — la démonstration tient en cinq lignes et n'utilise que deux ingrédients.
3. Vérifier sur des exemples calculés à la main que $`P`$ mesure bien *le sens du mouvement*.
4. Comprendre ce que $`P`$ vaut sur les ondes, et retrouver $`k`$.
5. En déduire une réponse à la question du titre — et voir ce qu'elle prédit pour les graphes *sans* symétrie.

## 1. La symétrie, écrite comme une matrice

Plaçons-nous sur l'anneau à $`N`$ nœuds. « Tous les lieux se valent » signifie : si je décale toute la configuration d'un cran, les lois ne s'en aperçoivent pas. Donnons un nom à ce décalage.

> **Définition (opérateur de translation).** $`T`$ est l'opérateur qui pousse tout le champ d'un cran :
> $$(Tu)_n = u_{n-1} \qquad (\text{indices modulo } N).$$

$`T`$ est une matrice $`N \times N`$ parfaitement concrète : des $`1`$ juste sous la diagonale, un $`1`$ dans le coin pour reboucler. Trois propriétés, chacune vérifiable en une ligne :

**(i) $`T`$ est inversible**, d'inverse $`T^{-1} = T^\top`$ (décaler dans l'autre sens) : $`(T^\top u)_n = u_{n+1}`$. Décaler ne perd aucune information.

**(ii) $`T`$ préserve les longueurs** : $`\|Tu\|^2 = \sum_n u_{n-1}^2 = \|u\|^2`$ (on somme les mêmes nombres dans un autre ordre).

**(iii) $`T`$ commute avec $`L`$** :
$$
\boxed{\;TL = LT.\;}
$$
*Preuve.* Calculons les deux membres sur un champ $`u`$, au nœud $`n`$ :
$$
(TLu)_n = (Lu)_{n-1} = 2u_{n-1} - u_{n-2} - u_n, \qquad
(LTu)_n = 2(Tu)_n - (Tu)_{n-1} - (Tu)_{n+1} = 2u_{n-1} - u_{n-2} - u_n. \;\blacksquare
$$

Ne passons pas trop vite sur (iii) : c'est **la** traduction mathématique de l'homogénéité. Elle dit : *mesurer la rugosité puis décaler, ou décaler puis mesurer la rugosité, c'est pareil* — le Laplacien ne sait pas où il est. Sur un graphe quelconque, cette équation serait fausse : elle est vraie ici parce que l'anneau se superpose exactement à lui-même après décalage. Conséquence immédiate, qui justifie tout :

> **Proposition.** Si $`u(t)`$ est une solution de la dynamique, alors $`Tu(t)`$ est une solution.
>
> *Preuve.* Appliquons $`T`$ à la règle $`u(t{+}1) = 2u(t) - u(t{-}1) - c^2Lu(t)`$ :
> $$Tu(t{+}1) = 2\,Tu(t) - Tu(t{-}1) - c^2\,TLu(t) = 2\,Tu(t) - Tu(t{-}1) - c^2\,L\,\bigl(Tu(t)\bigr),$$
> où l'on a utilisé $`TL = LT`$ à la dernière étape. C'est exactement la règle, appliquée au champ décalé. $`\blacksquare`$

L'histoire d'un objet, jouée un cran plus loin, est une histoire tout aussi légale. Voilà notre symétrie. Noether promet un trésor : allons le chercher.

## 2. La quantité conservée : cinq lignes

Comment fabriquer une quantité conservée à partir de $`T`$ ? Guidons-nous sur le seul succès que nous ayons : l'énergie du chapitre IV, $`E = \frac12\|u(t)-u(t{-}1)\|^2 + \frac{c^2}{2}u(t)^\top L\, u(t{-}1)`$. Sa pièce maîtresse était une forme *enjambant les deux photographies*, $`u(t)^\top M\, u(t{-}1)`$, avec $`M = L`$. Essayons la même architecture, en remplaçant $`L`$ par un opérateur construit sur $`T`$. Lequel ? Il nous faut un objet qui *distingue les deux sens* — qui change de signe quand on retourne l'anneau. Le candidat s'impose : $`T - T^\top`$ (décaler à droite *moins* décaler à gauche).

> **Définition (quantité de mouvement).**
> $$\boxed{\;P(t) \;=\; u(t)^\top \bigl(T - T^\top\bigr)\, u(t-1) \;=\; \sum_n u_n(t)\,\bigl(u_{n-1}(t{-}1) - u_{n+1}(t{-}1)\bigr).\;}$$

> **Théorème.** $`P(t+1) = P(t)`$ pour toute solution. *Exactement.*

*Preuve.* Notons $`A = T - T^\top`$. Deux ingrédients, et seulement deux :
- **(S)** $`L`$ est symétrique et $`A`$ est antisymétrique ($`A^\top = -A`$) ;
- **(C)** $`L`$ et $`A`$ commutent ($`LA = AL`$, conséquence directe de $`TL = LT`$).

Ligne 1. $`P(t{+}1) - P(t) = u(t{+}1)^\top A\, u(t) - u(t)^\top A\, u(t{-}1)`$.

Ligne 2. Remplaçons $`u(t{+}1)`$ par la règle : $`u(t{+}1)^\top A\,u(t) = u(t)^\top(2 - c^2L)A\,u(t) \;-\; u(t{-}1)^\top A\, u(t)`$.

Ligne 3. Le premier morceau est nul. En effet, posons $`M = (2 - c^2L)A`$ : alors $`M^\top = A^\top(2 - c^2L) = -A(2-c^2L) = -(2-c^2L)A = -M`$, en utilisant **(S)** puis **(C)**. $`M`$ est antisymétrique, et pour toute matrice antisymétrique, $`u^\top M u = 0`$ (car $`u^\top M u = (u^\top M u)^\top = -u^\top M u`$).

Ligne 4. Le second morceau se retourne par antisymétrie : $`-\,u(t{-}1)^\top A\, u(t) = +\,u(t)^\top A\, u(t{-}1)`$.

Ligne 5. Bilan : $`P(t{+}1) - P(t) = u(t)^\top A\,u(t{-}1) - u(t)^\top A\,u(t{-}1) = 0`$. $`\blacksquare`$

Relisons la preuve pour voir *où la symétrie a travaillé* : uniquement à la ligne 3, dans l'étape **(C)**. Si le graphe n'était pas invariant par décalage, $`LA \ne AL`$, $`M`$ ne serait pas antisymétrique, et la conservation tomberait. C'est le théorème de Noether réduit à son squelette algébrique :

> **une symétrie de la loi** ($`TL = LT`$) **+ une structure de la loi** ($`L`$ symétrique, héritée du chapitre I) **⇒ une conservation**.

Rien d'autre. Pas de coordonnées, pas de vecteurs, pas de limite continue. (Et l'expérience confirme : champ initial *aléatoire* sur un anneau, $`300`$ pas, $`P`$ constante à la douzième décimale — tout comme $`E`$.)

## 3. Que mesure $`P`$ ? Trois calculs à la main

Une formule conservée ne vaut que si l'on comprend ce qu'elle *dit*. Reprenons l'objet du chapitre VI, sur l'anneau à $`4`$ nœuds : la bosse $`u(0) = (2,1,0,1)`$, et calculons $`P = \sum_n u_n(0)\bigl(u_{n-1}(-1) - u_{n+1}(-1)\bigr)`$ dans trois situations.

**Bosse lancée vers la droite** ($`u(-1) = (1,0,1,2)`$, la bosse était un cran à gauche) :
$$
P = \underbrace{2\,(u_3 - u_1)}_{n=0} + \underbrace{1\,(u_0 - u_2)}_{n=1} + \underbrace{0\,(\cdots)}_{n=2} + \underbrace{1\,(u_2 - u_0)}_{n=3}
= 2(2-0) + (1-1) + 0 + (1-1) = \mathbf{+4}.
$$

**Bosse lancée vers la gauche** ($`u(-1) = (1,2,1,0)`$) : le même calcul donne $`2(0-2) + 0 + 0 + 0 = \mathbf{-4}`$.

**Bosse au repos** ($`u(-1) = u(0)`$) : $`2(1-1) + 1(2-0) + 0 + 1(0-2) = \mathbf{0}`$.

Le verdict est net : $`P`$ est **positive vers la droite, négative vers la gauche, nulle au repos** — et sa valeur est verrouillée pour toute l'éternité du mouvement. C'est un élan. Notons aussi ce que ces petits calculs révèlent de la structure de la formule : le terme $`u_{n-1}(t{-}1) - u_{n+1}(t{-}1)`$ compare *hier à gauche* et *hier à droite* — il détecte de quel côté l'objet arrive ; et il est pondéré par $`u_n(t)`$ — là où l'objet se trouve. $`P`$ est un produit « présence $`\times`$ provenance », sommé sur l'univers. (Le lecteur qui connaît la mécanique des milieux continus reconnaîtra son vieil ami $`\int \dot u\, \partial_x u\, dx`$ : notre $`A = T - T^\top`$ est, au facteur $`-2`$ près, la dérivée spatiale centrée, et l'enjambement des deux instants tient lieu de $`\dot u`$.)

## 4. $`P`$ sur les ondes : le retour de $`k`$

Évaluons maintenant $`P`$ sur une onde progressive pure, $`u_n(t) = \cos(kn - \omega t)`$, notre objet élémentaire du chapitre VI. Le calcul (identités produit-somme, les termes oscillants s'annulant sur l'anneau) donne une formule fermée :
$$
\boxed{\;P_{\text{onde}} = N \sin(k)\,\sin(\omega).\;}
$$
(Vérifiée numériquement à $`10^{-6}`$ près.) Lisons-la, car chaque facteur parle. Elle est **impaire en $`k`$** : l'onde $`-k`$, qui court dans l'autre sens, porte l'élan opposé — et une onde stationnaire, superposition de $`+k`$ et $`-k`$, porte un élan exactement nul, conformément au « bosse au repos » du §3. Elle est nulle pour $`k = 0`$ (le fond uniforme ne va nulle part) et — plus subtil — pour $`k = \pi`$ : le zigzag, dont le chapitre VI a montré qu'il *piétine* ($`v_g = 0`$), a beau vibrer de toutes ses forces, son élan est nul. $`P`$ ne se laisse pas impressionner par l'agitation : il ne compte que le *transport*.

Aux grandes longueurs d'onde ($`k`$ petit, $`\omega \approx ck`$), la formule devient $`P \approx N\,c\,k^2 \cdot \tfrac{1}{c} \cdot \tfrac{\omega}{k}`$… tenons-nous en au fait essentiel : à énergie donnée, $`P`$ *croît avec $`k`$*. Le nombre d'onde $`k`$, entré au chapitre VI comme un simple compteur de tours par arête, se révèle être la **densité d'élan par unité d'énergie** de chaque composante. C'est pourquoi les physiciens l'appellent la **quasi-impulsion** : sur un réseau, $`k`$ joue le rôle que l'impulsion $`p`$ joue dans le continu. (Le préfixe *quasi* rappelle une particularité de bon aloi : $`k`$ vit sur un cercle — $`k`$ et $`k + 2\pi`$ décrivent la même ondulation, puisque seuls comptent les nœuds. L'élan d'un monde discret est une grandeur *périodique*. Retenons cette bizarrerie : elle aura des conséquences.)

## 5. Alors, qu'est-ce qu'une direction ?

Nous pouvons répondre à la question du titre, et la réponse renverse l'intuition géométrique.

Dans l'espace ordinaire, on croit l'ordre suivant : *d'abord* il y a des directions (des vecteurs), *ensuite* les objets en mouvement en choisissent une, *enfin* la conservation de l'élan est un théorème. Notre reconstruction inverse tout. Au départ, il n'y a **aucune** direction — un graphe n'a pas de vecteurs. Il y a en revanche des **symétries** : des transformations $`T`$ qui laissent le graphe invariant, et l'algèbre $`TL = LT`$ fabrique pour chacune une quantité conservée $`P`$. Une « direction », c'est le *signe et la grandeur de cet élan conservé* : aller à droite, c'est avoir $`P > 0`$. Le mouvement rectiligne uniforme du chapitre III reçoit ici sa vraie explication : l'objet ne « suit » pas une droite (il n'y en a pas) — il conserve son $`P`$, et conserver son $`P`$, *c'est* aller tout droit.

> **Le déclic.** Une direction n'est pas une propriété de l'espace : c'est une propriété du *groupe de symétrie* de l'univers. Il y a exactement autant de directions que de translations que le graphe supporte. L'anneau en supporte une (et son inverse) : son monde est unidimensionnel. Une grille en supporte deux indépendantes : monde bidimensionnel. La *dimension* elle-même, que nous n'avions jamais définie, vient de recevoir sa définition : c'est le nombre de translations indépendantes — le nombre de conservations d'élan que l'univers offre.

Et la contraposée est physique, vérifiable, et un peu vertigineuse : sur un graphe **sans symétrie de translation** — un réseau désordonné, un arbre irrégulier — il n'existe ni $`T`$, ni $`P`$, ni directions. Aucun objet ne peut y « aller tout droit », non par maladresse, mais parce que *tout droit n'y veut rien dire*. Le chapitre VI l'avait pressenti (pas de dégénérescence, pas de relais) ; nous savons maintenant le dire en une phrase : **le mouvement inertiel est la monnaie d'une symétrie, et les univers irréguliers sont insolvables**. C'est un phénomène bien réel de la physique des matériaux : dans un milieu suffisamment désordonné, les ondes cessent de se propager et restent piégées — le lecteur curieux cherchera *localisation d'Anderson*.

## 6. Où nous en sommes

Le butin du chapitre, en tableau — car il complète une structure entamée au chapitre IV :

| Symétrie de la loi | Équation | Quantité conservée |
|---|---|---|
| Indifférence à la date | mêmes coefficients à tout $`t`$ | énergie $`E`$ (chap. IV) |
| Indifférence au niveau du champ | $`L\mathbf 1 = 0`$ | dérive du total $`S(t) - S(t{-}1)`$ (chap. IV) |
| Indifférence au lieu | $`TL = LT`$ | quantité de mouvement $`P`$ (ce chapitre) |

Trois indifférences, trois trésors : la grille de Noether, annoncée en aparté, est devenue une machine qui tourne. Et nous tenons désormais les deux monnaies fondamentales de toute mécanique — $`E`$ et $`P`$ — sans avoir jamais importé un seul concept géométrique.

Mais ce tableau dessine en creux la prochaine étape. Toute notre physique est celle d'un monde *parfaitement homogène* — et un monde parfaitement homogène est un monde où il ne se passe rien : les objets y vont tout droit, éternellement, et c'est tout. Le monde intéressant commence quand *quelque chose, quelque part, est différent* : un lieu qui attire, un lieu qui repousse. Or nous savons maintenant exactement ce que « casser l'homogénéité » coûtera : $`TL \ne LT`$, la ligne 3 de notre preuve s'effondre, et $`P`$ cesse d'être conservée. Loin d'être une catastrophe, ce sera notre définition : le taux de variation de l'élan, $`P(t{+}1) - P(t)`$, mesurera *ce que le monde inflige à l'objet*. Les physiciens ont un nom pour cette grandeur. Il figure dans la plus célèbre équation de Newton.

> **Chapitre suivant — VIII. Qu'est-ce qu'une force ?**
> *Où l'on casse l'homogénéité, et où $`\;F = \Delta P/\Delta t\;`$ cesse d'être un axiome pour devenir une définition.*

---
