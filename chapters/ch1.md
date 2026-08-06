# Chapitre I — Le seul calcul qu'un nœud puisse faire

> **Question.** Que peut calculer un point qui ne connaît que ses voisins ?

Avant de parler de mouvement, d'objet ou de temps, il faut répondre à une question plus élémentaire : quelle opération spatiale allons-nous autoriser ? La réponse ne sera pas « tout ce qu'un nœud peut imaginer », mais l'opération la plus simple compatible avec nos règles. Elle fournira l'appareil mathématique du livre.

## 1. Un chiffre sur chaque point

Donnons-nous la seule chose qu'un point puisse porter : un nombre. Sur chaque sommet $`v`$ du graphe, nous écrivons une valeur $`u_v \in \mathbb{R}`$. La donnée de tous ces nombres à la fois est une fonction
```math
u : V \longrightarrow \mathbb{R},
```
que nous appellerons un **champ**. C'est notre unique matière première : une hauteur, une amplitude, une intensité — peu importe le nom — posée sur chaque point de l'univers.

Nous voudrions maintenant faire *évoluer* ce champ. Mais avant d'introduire le temps, posons la question minimale : à un instant donné, quel calcul un point est-il seulement *capable* d'effectuer sur lui-même ?

**Pourquoi cette question est décisive.** Toute loi physique locale sera, au fond, une règle qui dit à chaque point comment se transformer. Or un point ne dispose que de deux informations : sa propre valeur $`u_v`$, et les valeurs $`u_w`$ de ses voisins $`w \sim v`$. Il ne connaît ni sa position, ni la forme globale du champ, ni ce qui se passe à trois arêtes de là. **Tout ce que la physique pourra dire de local devra s'écrire à partir de ces seules quantités.** Comprendre le répertoire d'un point, c'est donc borner à l'avance tout ce que la théorie pourra faire.

## 2. Comparer, faute de mieux

Que faire de $`u_v`$ et des $`u_w`$ ? Le premier geste raisonnable est de **comparer** le point à son entourage :

> « Suis-je plus grand, ou plus petit, que ce qui m'entoure ? »

Cette intuition a une conséquence immédiate, presque une évidence physique : **si un point vaut exactement la moyenne de ses voisins, rien ne le distingue de son entourage, et il n'a aucune raison de changer.** Un champ parfaitement plat doit être inerte. À l'inverse, un point qui dépasse nettement ses voisins — un pic — est dans une situation « tendue » : on s'attend à ce qu'il évolue davantage.

Ce que nous cherchons, c'est donc une mesure de l'**écart à l'entourage local**. Sur une chaîne $`A-B-C`$, si le champ vaut $`u=(1,3,2)`$, le sommet $`B`$ dépasse la moyenne de ses voisins, qui vaut $`(1+2)/2=1{,}5`$. Une opération de nivellement doit donc produire en $`B`$ un nombre positif, dont le signe indiquera « trop haut ». Formalisons cette intuition, puis comptons exactement la liberté restante.

## 3. Les hypothèses qui conduisent à la formule

Partons de la forme la plus générale d'un calcul **linéaire** utilisant seulement le sommet $`v`$ et ses voisins :

```math
(\mathcal Lu)_v=a_vu_v+\sum_{w\sim v}b_{vw}u_w.
```

Cette écriture contient encore beaucoup de choix. Nous allons les retirer un par un.

**(a) Linéarité.** Doubler toutes les valeurs double le résultat ; additionner deux champs additionne leurs résultats. C'est une hypothèse, pas une conséquence de la localité. Nous la choisissons parce qu'elle est la première à essayer et qu'elle permet de comprendre exactement ce qui se passe. La non-linéarité reviendra au chapitre X.

**(b) Aucun voisin n'est distingué au même sommet.** Le nœud $`v`$ ne possède ni boussole ni étiquette « voisin de gauche ». Ses voisins entrent donc avec un même coefficient, que nous pouvons d'abord noter $`b_v`$ :

```math
(\mathcal Lu)_v=a_vu_v+b_v\sum_{w\sim v}u_w.
```

**(c) Même couplage sur chaque arête.** Nous faisons maintenant un choix supplémentaire : une différence de valeur agit avec la même intensité sur toutes les arêtes. Ainsi $`b_v`$ ne dépend plus du sommet ; nous l'écrivons $`b`$. C'est cette hypothèse de **couplage universel** qui écarte, par exemple, la moyenne normalisée où un sommet partage une influence totale entre ses voisins.

**(d) Un champ constant ne produit aucun signal.** Si $`u_w=c`$ partout, alors

```math
0=a_vc+b\,\deg(v)c \qquad \text{pour tout }c.
```

Il faut donc

```math
a_v=-b\,\deg(v).
```

Le coefficient diagonal n'a pas été choisi : une fois le couplage des arêtes fixé, l'annulation des constantes le détermine. En prenant $`b=-1`$ — choix d'échelle et de signe — on obtient

```math
\boxed{(\mathcal Lu)_v=\deg(v)u_v-\sum_{w\sim v}u_w
      =\sum_{w\sim v}(u_v-u_w).}
```

C'est le **Laplacien combinatoire** du graphe. Sous les quatre hypothèses que nous venons d'énoncer, il est unique à un facteur multiplicatif près. Sans l'hypothèse (c), d'autres opérateurs restent possibles. Le Laplacien normalisé $`I-D^{-1}A`$, par exemple, mesure directement l'écart à la moyenne des voisins. Nous choisissons $`D-A`$ parce qu'il attribue la même raideur à chaque arête et parce qu'il est symétrique sur un graphe non orienté — deux propriétés qui deviendront essentielles.

Sous forme matricielle,

```math
L=D-A,
```

où $`A`$ est la matrice d'adjacence et $`D`$ la matrice diagonale des degrés.

### Un calcul complet sur trois sommets

Pour la chaîne $`A-B-C`$,

```math
A=\begin{pmatrix}0&1&0\\1&0&1\\0&1&0\end{pmatrix},\qquad
D=\begin{pmatrix}1&0&0\\0&2&0\\0&0&1\end{pmatrix},\qquad
L=\begin{pmatrix}1&-1&0\\-1&2&-1\\0&-1&1\end{pmatrix}.
```

Avec $`u=(1,3,2)^T`$,

```math
Lu=\begin{pmatrix}-2\\3\\-1\end{pmatrix}.
```

Au centre, le résultat $`3=(3-1)+(3-2)`$ additionne exactement les deux écarts aux voisins. Aux extrémités, il n'y a qu'un écart. On peut également vérifier que les composantes de $`Lu`$ se somment à zéro : ce qui est compté positivement d'un côté d'une arête est compté négativement de l'autre.

> **Le déclic.** Le terme $`D`$ n'est pas sorti d'un chapeau. Il est le prix exact à payer pour que les champs constants soient annulés lorsque chaque arête porte le même couplage.

## 4. Ce que le Laplacien voit

Prenons la mesure de l'objet que nous venons d'obtenir. Trois lectures suffisent à en bâtir l'intuition.

**Un champ plat : rien.** Si $`u`$ est constant, $`(\mathcal{L}u)_v = 0`$ partout. En langage matriciel, le vecteur constant $`\mathbf{1} = (1,\dots,1)`$ vérifie
```math
L\,\mathbf{1} = 0 .
```
C'est notre exigence (c) devenue théorème : $`\mathbf 1`$ est vecteur propre de $`L`$ pour la valeur propre $`0`$.

**Un pic : beaucoup.** Prenons un point $`v`$ à $`1`$ entouré de voisins à $`0`$. Alors $`(\mathcal{L}u)_v = \deg(v) > 0`$ : le Laplacien est grand et positif. Un creux donnerait une valeur grande et négative. Le Laplacien mesure exactement **de combien un point dévie de ses voisins**, et dans quel sens.

**Une pente régulière : rien à l'intérieur.** Sur la chaîne $`\mathbb{Z}`$ (chaque point $`n`$ a pour voisins $`n-1`$ et $`n+1`$), prenons un champ affine $`u_n = \alpha n + \beta`$. Alors
```math
(\mathcal{L}u)_n = (u_n - u_{n-1}) + (u_n - u_{n+1}) = -\bigl(u_{n+1} - 2u_n + u_{n-1}\bigr) = 0 .
```
Une rampe régulière est « invisible » pour le Laplacien : ce qu'il détecte, ce n'est pas la pente, mais la **courbure** — le défaut de linéarité. On reconnaît d'ailleurs, au signe près, la différence seconde discrète $`u_{n+1} - 2u_n + u_{n-1}`$, l'analogue exact de $`-\,\partial_x^2`$. C'est pourquoi $`L`$ est le cousin discret de $`-\Delta`$, l'opposé du Laplacien continu.

## 5. Deux propriétés qui serviront partout

Le Laplacien de graphe possède deux propriétés structurelles dont nous ferons un usage constant.

**$`L`$ est symétrique.** Puisque $`A`$ est symétrique ($`v\sim w \iff w \sim v`$) et $`D`$ diagonale, $`L = D - A`$ est une matrice symétrique réelle. Elle est donc diagonalisable dans une base orthonormée de vecteurs propres, à valeurs propres réelles. Cette phrase, anodine aujourd'hui, sera au chapitre V la clé de toute la dynamique : elle garantit l'existence de « mouvements élémentaires ».

**$`L`$ est positive.** Un petit calcul, qu'il vaut la peine de faire une fois, révèle la vraie nature de $`L`$. Pour tout champ $`u`$,
```math
u^\top L\, u \;=\; \sum_{v} u_v \sum_{w\sim v}(u_v - u_w)
\;=\; \sum_{\{v,w\}\in E} (u_v - u_w)^2 \;\ge\; 0 .
```
(La somme se réorganise en sommant *une fois* sur chaque arête.) Cette quantité, appelée **énergie de Dirichlet**, mesure la « rugosité » totale du champ : elle est nulle si et seulement si $`u`$ est constant sur chaque composante connexe. Retenons-la : lorsque, au chapitre IV, nous partirons en quête d'une quantité que l'univers ne sait ni créer ni détruire, cette forme quadratique — la seule que le graphe nous offre naturellement — sera notre première suspecte.

## 6. Où nous en sommes

Nous étions partis de points reliés et d'un nombre par point. En exigeant un calcul local et linéaire, aucun voisin distingué, un même couplage sur chaque arête et l'annulation des champs constants, nous avons obtenu le Laplacien $`L=D-A`$. L'opérateur n'est donc pas « le seul imaginable » : il est celui que force ce cahier des charges précis. Il ne connaît que l'adjacence, et toute dynamique construite directement avec lui sera locale et sans coordonnées imposées.

Mais nous n'avons encore rien fait *bouger*. Le Laplacien est un instantané : il évalue un champ figé. Pour faire de la physique, il faut du mouvement. La tentation est irrésistible : essayons la chose la plus naïve du monde. Posons une jolie bosse sur quelques points, décrétons que chaque point se corrige un peu en direction de la moyenne de ses voisins, et regardons la bosse se déplacer.

Nous allons voir qu'elle ne se déplace pas.

Elle se **dissout**.

Et c'est de cet échec que naîtra toute la mécanique.

> **Chapitre suivant — II. Peut-on déplacer un objet ?**
> *Nous ne connaissons pas encore la vitesse.*
