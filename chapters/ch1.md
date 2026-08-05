# Chapitre I — Le seul calcul qu'un nœud puisse faire

> **Question.** Que peut calculer un point qui ne connaît que ses voisins ?

Avant de parler de mouvement, d'objet ou de temps, il faut répondre à une question beaucoup plus élémentaire, presque triviale en apparence — et pourtant elle va, à elle seule, imposer tout l'appareil mathématique du livre.

## 1. Un chiffre sur chaque point

Donnons-nous la seule chose qu'un point puisse porter : un nombre. Sur chaque sommet $v$ du graphe, nous écrivons une valeur $u_v \in \mathbb{R}$. La donnée de tous ces nombres à la fois est une fonction
$$
u : V \longrightarrow \mathbb{R},
$$
que nous appellerons un **champ**. C'est notre unique matière première : une hauteur, une amplitude, une intensité — peu importe le nom — posée sur chaque point de l'univers.

Nous voudrions maintenant faire *évoluer* ce champ. Mais avant d'introduire le temps, posons la question minimale : à un instant donné, quel calcul un point est-il seulement *capable* d'effectuer sur lui-même ?

**Pourquoi cette question est décisive.** Toute loi physique locale sera, au fond, une règle qui dit à chaque point comment se transformer. Or un point ne dispose que de deux informations : sa propre valeur $u_v$, et les valeurs $u_w$ de ses voisins $w \sim v$. Il ne connaît ni sa position, ni la forme globale du champ, ni ce qui se passe à trois arêtes de là. **Tout ce que la physique pourra dire de local devra s'écrire à partir de ces seules quantités.** Comprendre le répertoire d'un point, c'est donc borner à l'avance tout ce que la théorie pourra faire.

## 2. Comparer, faute de mieux

Que faire de $u_v$ et des $u_w$ ? Le seul geste raisonnable est de **comparer** le point à son entourage :

> « Suis-je plus grand, ou plus petit, que ce qui m'entoure ? »

Cette intuition a une conséquence immédiate, presque une évidence physique : **si un point vaut exactement la moyenne de ses voisins, rien ne le distingue de son entourage, et il n'a aucune raison de changer.** Un champ parfaitement plat doit être inerte. À l'inverse, un point qui dépasse nettement ses voisins — un pic — est dans une situation « tendue » : on s'attend à ce qu'il évolue davantage.

Ce que nous cherchons, c'est donc une mesure de l'**écart à la moyenne locale**. Formalisons cette intuition, puis montrons qu'elle ne laisse presque aucune liberté.

## 3. La contrainte force la formule

Cherchons la forme la plus générale d'un calcul local $ (\mathcal{L}u)_v $ que le point $v$ puisse produire, en imposant trois exigences — chacune est une traduction directe des règles du jeu.

**(a) Linéarité.** *(Parcimonie.)* C'est l'hypothèse la plus pauvre : nous supposons que doubler le champ double le résultat, et que le résultat d'une somme est la somme des résultats. Nous verrons plus tard que la non-linéarité ouvre des possibilités fascinantes (chapitre X) ; mais on ne l'introduit que lorsqu'on y est forcé. Sous cette hypothèse, le calcul est nécessairement une combinaison linéaire des valeurs disponibles :
$$
(\mathcal{L}u)_v \;=\; a_v\, u_v \;+\; \sum_{w \sim v} b_{vw}\, u_w .
$$

**(b) Absence de voisin privilégié.** *(Homogénéité/isotropie locale.)* Rien, dans le graphe nu, ne distingue un voisin d'un autre : il n'y a pas de « voisin de droite ». Tous les voisins doivent donc entrer avec le **même poids** $b_{vw} = b$. D'où
$$
(\mathcal{L}u)_v \;=\; a_v\, u_v \;+\; b \sum_{w \sim v} u_w .
$$

**(c) Un champ constant ne fait rien.** *(Pas de référence absolue.)* Nous l'avons exigé au §2 : si $u_w = c$ pour tout point, aucun point ne se distingue, et le calcul doit rendre $0$. En injectant $u \equiv c$ :
$$
0 \;=\; a_v\, c \;+\; b\, \deg(v)\, c \qquad \text{pour tout } c,
$$
où $\deg(v)$ est le nombre de voisins de $v$. Cela force
$$
a_v \;=\; -\,b\,\deg(v).
$$

Voilà le point remarquable. Nous n'avions rien décidé sur le coefficient diagonal $a_v$ ; c'est l'exigence « un champ plat est inerte » qui l'a **calculé pour nous**, et qui l'a rendu égal au degré du point. En choisissant la normalisation $b = -1$ (un simple choix d'échelle et de signe), on obtient
$$
\boxed{\;(\mathcal{L}u)_v \;=\; \deg(v)\,u_v \;-\; \sum_{w \sim v} u_w \;=\; \sum_{w \sim v} \bigl(u_v - u_w\bigr).\;}
$$

Ce n'est pas *un* opérateur parmi d'autres. C'est, à une échelle près, **le seul** calcul local, homogène, linéaire et aveugle aux constantes qu'un point puisse effectuer. Les mathématiciens l'appellent le **Laplacien du graphe**, et l'écrivent sous forme matricielle
$$
L \;=\; D - A,
$$
où $A$ est la matrice d'adjacence ($A_{vw} = 1$ si $v \sim w$, sinon $0$) et $D$ la matrice diagonale des degrés. La formule locale $(\mathcal{L}u)_v = \sum_{w\sim v}(u_v - u_w)$ et l'écriture globale $Lu = (D-A)u$ sont une seule et même chose.

> **Le déclic.** Le terme diagonal $D$ n'est pas un ingrédient ajouté à la main. Beaucoup de présentations sortent $L = D - A$ d'un chapeau. Ici, on voit que $D$ est *forcé* : c'est le prix exact à payer pour qu'un champ plat ne bouge pas. La matrice des degrés est la trace, dans l'algèbre, d'une exigence purement physique.

## 4. Ce que le Laplacien voit

Prenons la mesure de l'objet que nous venons d'obtenir. Trois lectures suffisent à en bâtir l'intuition.

**Un champ plat : rien.** Si $u$ est constant, $(\mathcal{L}u)_v = 0$ partout. En langage matriciel, le vecteur constant $\mathbf{1} = (1,\dots,1)$ vérifie
$$
L\,\mathbf{1} = 0 .
$$
C'est notre exigence (c) devenue théorème : $\mathbf 1$ est vecteur propre de $L$ pour la valeur propre $0$.

**Un pic : beaucoup.** Prenons un point $v$ à $1$ entouré de voisins à $0$. Alors $(\mathcal{L}u)_v = \deg(v) > 0$ : le Laplacien est grand et positif. Un creux donnerait une valeur grande et négative. Le Laplacien mesure exactement **de combien un point dévie de ses voisins**, et dans quel sens.

**Une pente régulière : rien à l'intérieur.** Sur la chaîne $\mathbb{Z}$ (chaque point $n$ a pour voisins $n-1$ et $n+1$), prenons un champ affine $u_n = \alpha n + \beta$. Alors
$$
(\mathcal{L}u)_n = (u_n - u_{n-1}) + (u_n - u_{n+1}) = -\bigl(u_{n+1} - 2u_n + u_{n-1}\bigr) = 0 .
$$
Une rampe régulière est « invisible » pour le Laplacien : ce qu'il détecte, ce n'est pas la pente, mais la **courbure** — le défaut de linéarité. On reconnaît d'ailleurs, au signe près, la différence seconde discrète $u_{n+1} - 2u_n + u_{n-1}$, l'analogue exact de $-\,\partial_x^2$. C'est pourquoi $L$ est le cousin discret de $-\Delta$, l'opposé du Laplacien continu.

## 5. Deux propriétés qui serviront partout

Le Laplacien de graphe possède deux propriétés structurelles dont nous ferons un usage constant.

**$L$ est symétrique.** Puisque $A$ est symétrique ($v\sim w \iff w \sim v$) et $D$ diagonale, $L = D - A$ est une matrice symétrique réelle. Elle est donc diagonalisable dans une base orthonormée de vecteurs propres, à valeurs propres réelles. Cette phrase, anodine aujourd'hui, sera au chapitre V la clé de toute la dynamique : elle garantit l'existence de « mouvements élémentaires ».

**$L$ est positive.** Un petit calcul, qu'il vaut la peine de faire une fois, révèle la vraie nature de $L$. Pour tout champ $u$,
$$
u^\top L\, u \;=\; \sum_{v} u_v \sum_{w\sim v}(u_v - u_w)
\;=\; \sum_{\{v,w\}\in E} (u_v - u_w)^2 \;\ge\; 0 .
$$
(La somme se réorganise en sommant *une fois* sur chaque arête.) Cette quantité, appelée **énergie de Dirichlet**, mesure la « rugosité » totale du champ : elle est nulle si et seulement si $u$ est constant sur chaque composante connexe. Retenons-la : lorsque, au chapitre IV, nous partirons en quête d'une quantité que l'univers ne sait ni créer ni détruire, cette forme quadratique — la seule que le graphe nous offre naturellement — sera notre première suspecte.

## 6. Où nous en sommes

Nous étions partis d'un décor vide : des points, des voisins, rien d'autre. En exigeant seulement qu'un calcul local soit linéaire, aveugle à l'identité des voisins, et insensible aux champs plats, nous avons été **contraints** à un unique opérateur, le Laplacien $L = D - A$. Il ne connaît que l'adjacence : toute physique écrite avec lui sera automatiquement locale et sans coordonnées. C'est notre premier acquis solide, et il n'a rien coûté d'arbitraire.

Mais nous n'avons encore rien fait *bouger*. Le Laplacien est un instantané : il évalue un champ figé. Pour faire de la physique, il faut du mouvement. La tentation est irrésistible : essayons la chose la plus naïve du monde. Posons une jolie bosse sur quelques points, décrétons que chaque point se corrige un peu en direction de la moyenne de ses voisins, et regardons la bosse se déplacer.

Nous allons voir qu'elle ne se déplace pas.

Elle se **dissout**.

Et c'est de cet échec que naîtra toute la mécanique.

> **Chapitre suivant — II. Peut-on déplacer un objet ?**
> *Nous ne connaissons pas encore la vitesse.*