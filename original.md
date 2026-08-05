# Une physique à partir de rien

### *Comment reconstruire la mécanique à partir d'un simple réseau de relations*

> « Les grandes théories ne sont pas seulement belles parce qu'elles expliquent le monde. Elles le sont aussi parce qu'elles montrent que ce monde ne pouvait presque pas être autrement. »

---

## Plan directeur

Ce livre raconte une seule histoire : la naissance progressive d'une mécanique. À chaque étape, nous exigeons qu'une propriété physique soit vraie ; cette exigence impose une structure mathématique précise, et une seule. Voici la carte du voyage — chaque ligne est une exigence, et la structure qu'elle force.

| Exigence physique | Structure imposée |
|---|---|
| Localité (un point ne connaît que ses voisins) | Laplacien de graphe |
| Inertie (un objet continue tout droit) | dynamique du **second ordre** en temps |
| Confiance (rien n'est créé ni détruit) | quantité conservée → **énergie** |
| Simplicité des mouvements | modes propres du Laplacien |
| Étalement | relation de dispersion, vitesse de groupe |
| Direction (aller tout droit sans coordonnées) | quasi-impulsion, Noether discret |
| Déviation d'une trajectoire | potentiel, théorème d'Ehrenfest |
| Objet localisé | paquet d'ondes, inégalité de Heisenberg |
| Objet indestructible | non-linéarité, solitons, charge topologique |
| Géométrie de l'univers | dimension, isotropie (exacte ou statistique), courbure |
| Espace et temps sur le même pied | graphe d'espace-temps, univers-bloc |

**Table des chapitres** (provisoire, susceptible d'évoluer) :

- **Prologue** — Peut-on reconstruire la physique ?
- **I.** Le seul calcul qu'un nœud puisse faire
- **II.** Peut-on déplacer un objet ?
- **III.** Pourquoi faut-il une mémoire ?
- **IV.** Comment savoir si notre univers triche ? *(+ aparté Noether)*
- **V.** Quels sont les objets élémentaires de cette dynamique ?
- **VI.** Pourquoi les objets s'étalent-ils ?
- **Interlude** — Pourquoi parle-t-on d'ondes ? *(ce qui est classique dans ce qui semble quantique ; ce qui manquerait vraiment : Born, mesure, intrication ; le teaser $\mathbb{C}$ = deux mémoires en un nombre)*
- **VII.** Qu'est-ce qu'une direction ?
- **VIII.** Qu'est-ce qu'une force ?
- **IX.** Pourquoi les particules ne sont-elles pas des points ?
- **X.** Comment fabriquer une vraie particule ?
- **XI.** Changer de géométrie — *grille 2D : deux élans, la dimension comme comptage de translations ; anisotropie du réseau et son **émergence de l'isotropie** aux grandes longueurs d'onde ; désordre : graphe de Poisson, symétrie **statistique** (en loi, pas par réalisation), milieu effectif, conservation à date de péremption (libre parcours moyen), localisation d'Anderson ; graphe qui change dans le temps : énergie non conservée, redshift, invariants adiabatiques ; chute : le chiasme cristal/hasard — le hasard est plus isotrope que le cristal.*
- **XII.** Et si le temps était une arête ? — *le graphe d'espace-temps (la règle du chap. III relue comme graphe de dépendance, arêtes temporelles non orientées par réversibilité) ; l'univers-bloc : la dynamique devient contrainte de cohérence ; énergie et impulsion, deux visages d'une même homogénéité ; $c$ géométrisé (rapport de maillage) ; discussion fine des hypothèses de Bell (localité vs libre choix, superdéterminisme, rétrocausalité — controversé, à étiqueter comme tel).*
- **Épilogue** — Ondes, particules, et le seuil du quantique

**Partie III (esquisse, après le corps principal)** : empaquetage complexe ($\psi$ = deux photographies en un champ, Schrödinger comme premier ordre dans $\mathbb{C}$, masse = bas de courbe parabolique) ; fentes d'Young sur graphe ; quantification = spectre discret ; effet tunnel ; Born rendu plausible (densité d'énergie) ; et le chapitre-mur : construire Bell/CHSH dans notre univers et le regarder donner $\le 2$ quand la nature donne $2\sqrt2$ — localiser exactement où commence le quantique (intrication, mesure, clic irréductible). Règle d'or de cette partie : étiqueter chaque énoncé — théorème, conjecture, ou opinion.

**Règles de travail.** On ne passe au chapitre suivant que lorsque le précédent donne la sensation « c'est évident maintenant ». Chaque chapitre commence par une question physique et se termine sur la question qui force le suivant. On préfère supprimer cinquante lignes plutôt que laisser un seul saut logique.

---

# Prologue — Peut-on reconstruire la physique ?

## Si l'on effaçait toute la géométrie

Supposons que nous ayons le droit de reconstruire l'Univers depuis zéro.

Interdiction d'utiliser les lois de Newton, celles d'Einstein, ou celles de la mécanique quantique. Interdiction, même, de supposer que l'espace ressemble à celui que nous connaissons. Nous allons être plus radicaux encore : nous effaçons **presque toute la géométrie**.

Plus de coordonnées. Plus de distances. Plus d'angles. Plus de droites. Plus de vecteurs. Plus de vitesse. Plus de masse. Plus d'énergie.

Il ne reste qu'une immense collection de points, reliés entre eux. Et chaque point ne sait répondre qu'à une seule question :

> **« Quels sont mes voisins ? »**

C'est tout. Aucun point ne connaît sa position, car il n'y a pas de position. Aucun ne connaît sa distance à un autre, car il n'y a pas de distance. Il n'y a que ce tissu de relations : *qui touche qui*.

À première vue, la situation paraît désespérée. Comment parler de mouvement lorsqu'il n'existe plus de direction ? Comment définir une vitesse lorsqu'il n'existe plus de distance ? Comment parler d'une force lorsqu'il n'existe plus de trajectoire ? Toute la physique semble s'être évaporée avec la géométrie.

Pourtant une question demeure, et c'est elle qui guide ce livre :

> Était-ce réellement la géométrie qui portait la physique ? Ou bien les lois physiques sont-elles plus profondes que les coordonnées dont nous nous servons d'habitude pour les décrire ?

## Une reconstruction, pas une présentation

Dans la plupart des cours, les concepts arrivent dans un ordre historique ou pratique : on définit l'énergie, puis la quantité de mouvement, puis les forces, puis les ondes, puis les particules. Chaque objet est présenté parce qu'il *existe* et qu'il faudra bien s'en servir.

Nous ferons exactement l'inverse.

Nous partirons d'un monde où **aucun** de ces concepts n'existe. À chaque étape, nous nous heurterons à une difficulté concrète. Nous chercherons alors la structure mathématique **la plus simple** capable de la résoudre. Si elle fonctionne, nous continuons ; sinon, nous l'abandonnons et nous comprenons pourquoi.

La règle est stricte : nous ne chercherons jamais à retrouver un concept familier *parce que nous savons qu'il existe*. Nous chercherons seulement à résoudre le problème qui se pose. Si, chemin faisant, apparaissent une inertie, une énergie, une masse, ou même des particules, ce sera parce que notre univers en aura **eu besoin** — et non parce que nous les aurons glissées d'avance dans les hypothèses.

C'est une contrainte inconfortable. C'est aussi ce qui rendra chaque découverte convaincante : quand un concept surgira, il sera *forcé*, pas invité.

## Les règles du jeu

Notre univers obéira à très peu de contraintes, mais elles seront intransigeantes.

**Localité.** Un point n'interagit qu'avec ses voisins. Aucune information ne peut apparaître spontanément à distance ; toute influence doit se propager de proche en proche.

**Homogénéité.** Les mêmes lois s'appliquent partout. Aucun point n'est privilégié : la règle qui gouverne un point doit être la même que celle qui gouverne tous les autres.

**Parcimonie.** À chaque bifurcation, lorsque plusieurs constructions sont possibles, nous retenons la plus pauvre — celle qui suppose le moins. Ce n'est pas un principe esthétique : c'est ce qui garantit que ce que nous obtiendrons aura vraiment été *imposé*, et non choisi en douce.

## Ce que nous ne savons pas encore faire

Au seuil de ce livre, aucune des questions suivantes n'a de réponse. C'est le programme :

- Peut-on définir un mouvement sans coordonnées ?
- Peut-on continuer *tout droit* là où il n'existe pas de droite ?
- Une notion de vitesse peut-elle émerger d'une simple mémoire ?
- Existe-t-il une quantité que notre univers ne puisse ni créer ni détruire ?
- Les objets élémentaires sont-ils des points, ou des ondes ?
- Une force peut-elle apparaître sans espace euclidien ?
- Pourquoi certaines structures se comportent-elles comme des particules ?

Nous ne supposerons aucune de ces réponses. Nous allons les découvrir — ou découvrir qu'elles n'existent pas.

## Le nom de la chose

La structure que nous venons de décrire — des points, et pour chaque point la seule donnée de ses voisins — porte un nom en mathématiques : c'est un **graphe**. Un ensemble de sommets $V$, et un ensemble d'arêtes $E$ qui disent quels sommets sont voisins. Rien de plus : pas de longueur d'arête, pas de position des sommets, pas d'orientation privilégiée.

Nous avons introduit l'idée avant le mot, et c'est délibéré. Ce livre n'est pas un cours sur la théorie des graphes ; c'est une tentative de faire naître la physique à partir du strict minimum. Le graphe n'est que le décor le plus pauvre que nous ayons su imaginer. Toute la question est de savoir ce qu'on peut y bâtir.

## Un dernier avertissement

Ce livre ne cherche pas à reconstruire *exactement* notre Univers. Il pose une question plus fondamentale :

> Quelle est la plus petite quantité de structure nécessaire pour que des lois physiques puissent émerger ?

Peut-être verrons-nous apparaître une mécanique proche de celle de Newton. Peut-être des ondes surgiront-elles d'elles-mêmes. Peut-être certaines idées rappelleront-elles la mécanique quantique. Mais nous ne partirons jamais de ces théories. Nous partirons d'un réseau de relations, et de rien d'autre. Et nous verrons jusqu'où cette seule idée peut nous mener.

---

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

---

# Chapitre II — Peut-on déplacer un objet ?

> **Question.** Comment définir un mouvement là où il n'y a ni coordonnées, ni directions ?
>
> *Nous ne savons même pas encore ce qu'est un objet.*

## 1. Qu'appellerons-nous un objet ?

Nous disposons d'un champ $u$ et d'un opérateur $L$. Nulle part il n'y a de « chose » qui se déplace. Il faut donc commencer par décider ce qu'un objet *pourrait être* dans ce monde.

La proposition la plus honnête est la suivante : un objet est une **configuration localisée du champ** — une région où $u$ est grand, entourée d'un fond où $u$ est nul. Concrètement, sur la chaîne $\mathbb{Z}$, une bosse :
$$
u_{-1} = 1,\quad u_0 = 2,\quad u_1 = 1, \qquad u_n = 0 \text{ ailleurs.}
$$

Et nous dirons que l'objet **se déplace** si, aux instants suivants, on retrouve *la même bosse*, simplement posée ailleurs. Pas une bosse déformée, pas une trace diluée : la même forme, translatée. C'est exigeant, mais c'est bien ce que fait une balle qu'on lance — elle ne se dissout pas en vol.

Reste à faire évoluer le champ. Introduisons le temps de la manière la plus économe possible : une suite d'instants discrets $t = 0, 1, 2, \dots$, et une règle qui fabrique $u(t+1)$ à partir de ce qui est disponible.

## 2. La règle la plus pauvre possible

Que peut utiliser un point $v$ pour décider de sa prochaine valeur ? Fidèles à la parcimonie, donnons-lui le strict minimum : **l'état présent, et rien d'autre**. Sa valeur $u_v(t)$, celles de ses voisins — c'est-à-dire, comme le chapitre I nous l'a appris, sa valeur et son Laplacien. La règle locale, linéaire et homogène la plus générale est alors
$$
u_v(t+1) \;=\; u_v(t) \;-\; \varepsilon\, (Lu(t))_v ,
$$
où $\varepsilon > 0$ est un petit pas. (Le coefficient devant $u_v(t)$ doit valoir $1$ : sinon un champ constant, censé être inerte, se mettrait à croître ou à fondre sur place.)

Lisons cette règle en français avant de la lancer :

> « À chaque instant, chaque point se rapproche un peu de la moyenne de ses voisins. »

Un point au-dessus de la moyenne locale ($Lu > 0$) redescend ; un point en dessous remonte. C'est la dynamique du nivellement. Elle semble raisonnable, presque inoffensive. Voyons ce qu'elle fait de notre bosse.

## 3. L'expérience : on lâche la bosse

Prenons $\varepsilon = \tfrac{1}{2}$ pour la lisibilité (sur la chaîne, la règle devient : *chaque point prend la moyenne de ses deux voisins*, puisque $u_n(t+1) = u_n - \tfrac12(2u_n - u_{n-1} - u_{n+1}) = \tfrac{u_{n-1}+u_{n+1}}{2}$). Calculons à la main.

**À $t=0$ :**
$$
\dots,\ 0,\ 0,\ 1,\ 2,\ 1,\ 0,\ 0,\ \dots
$$

**À $t=1$ :** chaque point prend la moyenne de ses voisins :
$$
\dots,\ 0,\ 0.5,\ 1,\ 1,\ 1,\ 0.5,\ 0,\ \dots
$$

**À $t=2$ :**
$$
\dots,\ 0.25,\ 0.5,\ 0.75,\ 1,\ 0.75,\ 0.5,\ 0.25,\ \dots
$$

Le verdict est sans appel, et il est double.

**Premier constat : la bosse ne va nulle part.** Elle est restée exactement centrée en $0$. Par symétrie, c'était couru d'avance : la configuration initiale est symétrique autour de $0$, la règle est symétrique, donc le champ reste symétrique pour toujours. Rien, dans cette dynamique, ne peut choisir la droite plutôt que la gauche.

**Second constat : elle se dissout.** Son maximum fond ($2 \to 1 \to 1 \to \dots$), sa largeur croît. Le total, lui, ne bouge pas — la somme $\sum_n u_n(t)$ vaut $4$ à chaque instant, car chaque point ne fait que redistribuer. L'objet ne disparaît pas : il **s'étale**, jusqu'à devenir un brouillard uniforme et indiscernable.

Ce comportement porte un nom : la **diffusion**. Notre règle est exactement l'équation de la chaleur discrète, $u(t+1) - u(t) = -\varepsilon L u(t)$, l'analogue de $\partial_t u = \Delta u$. Nous avons construit un excellent modèle… de goutte d'encre dans l'eau. Pas de balle.

## 4. Peut-on tricher en poussant la bosse ?

Un lecteur combatif objectera : la bosse était immobile au départ, rien d'étonnant à ce qu'elle le reste. Donnons-lui un élan ! Rendons la condition initiale asymétrique — plus de poids à droite :
$$
u_{-1} = 1,\quad u_0 = 2,\quad u_1 = 3,\qquad u_n = 0 \text{ ailleurs.}
$$
Un pas de calcul ($t=1$) : $\;\dots,\ 0.5,\ 1,\ 2.5,\ 1,\ 1.5,\ \dots$ — le centre de gravité, lui, n'a pas bougé. Ce n'est pas un accident. Calculons le **barycentre** $X(t) = \sum_n n\, u_n(t) \,/\, \sum_n u_n(t)$. Le dénominateur est conservé (§3). Pour le numérateur :
$$
\sum_n n\, u_n(t+1) = \sum_n n\,\frac{u_{n-1}(t) + u_{n+1}(t)}{2}
= \sum_m \frac{(m+1) + (m-1)}{2}\, u_m(t) = \sum_m m\, u_m(t).
$$
Le barycentre est **rigoureusement immobile**, quel que soit le profil initial. On peut sculpter la bosse comme on veut : son centre ne se déplacera jamais d'un pouce. La dynamique de nivellement est constitutionnellement incapable de transporter quoi que ce soit.

## 5. L'autopsie : où l'information de direction pourrait-elle vivre ?

Il faut comprendre cet échec en profondeur, car c'est lui qui va dicter la suite. Posons la question au niveau d'un seul pas de temps, $t \to t+1$, là où tout se joue.

Pour que la bosse avance vers la droite, il faudrait qu'au moment de la mise à jour, quelque chose distingue la droite de la gauche. Passons l'inventaire de ce que « sait » le système à l'instant $t$ :

- le graphe lui-même : parfaitement symétrique, aucune direction privilégiée ;
- la règle : la même partout, aveugle à l'identité des voisins (chapitre I, exigence (b)) ;
- l'état $u(t)$ : une photographie du champ.

Et c'est tout. Or une photographie ne contient pas de vitesse. Deux films — l'un où la balle va vers la droite, l'autre vers la gauche — peuvent passer par *la même image* à l'instant $t$. Si la loi d'évolution ne dépend que de cette image, elle doit produire **le même futur dans les deux cas**. La direction du mouvement n'est tout simplement **stockée nulle part**.

> **Le déclic.** L'échec n'est pas dû à un mauvais choix de coefficients, et aucun raffinement de la règle $u(t+1) = f(u(t))$ n'y changera rien. C'est un théorème d'impossibilité structurel : *toute* dynamique qui ne lit que l'instant présent est sans mémoire, et un système sans mémoire ne peut pas savoir d'où il vient — donc pas où il va. Le problème n'est pas la formule. C'est la **quantité d'information que nous avons accordée à l'état**.

La mécanique nous fait ici un clin d'œil qu'il faut savourer : c'est exactement pour cela que l'état d'une particule de Newton n'est pas sa position, mais le couple *(position, vitesse)*. Nous venons de redécouvrir, par l'échec, pourquoi ce doublement est inévitable. Mais dans notre monde sans coordonnées, « ajouter la vitesse » n'a aucun sens littéral — il n'y a pas de vecteurs. La seule chose que nous puissions ajouter, c'est du **passé**.

## 6. Une remarque avant de continuer : le hasard n'aurait pas fait mieux

On aurait pu tenter une autre voie naïve : lâcher un jeton sur un nœud, et le faire sauter à chaque instant vers un voisin choisi au hasard — une **marche aléatoire**. C'est le même échec, vu de profil. Sur la chaîne, la position après $t$ pas est $X_t = \xi_1 + \dots + \xi_t$ avec des pas indépendants $\xi_i = \pm 1$ ; d'où
$$
\mathbb{E}[X_t] = 0, \qquad \mathbb{E}[X_t^2] = t, \qquad \text{distance typique} \sim \sqrt{t}.
$$
Un mobile digne de ce nom parcourt une distance proportionnelle à $t$ — le régime **balistique**. La marche aléatoire fait $\sqrt t$ — le régime **diffusif** : pour aller deux fois plus loin, il lui faut *quatre* fois plus de temps. Et la raison profonde est identique : à chaque pas, le jeton ignore d'où il vient ; son prochain saut ne dépend que de sa position présente. Diffusion déterministe du champ, marche aléatoire du jeton : deux visages du même défaut, **l'absence de mémoire**. (Ce n'est pas un hasard si la densité de probabilité de la marche obéit précisément à notre équation de diffusion.)

## 7. Où nous en sommes

Nous voulions déplacer un objet. Nous avons essayé la dynamique la plus simple possible — chaque point se rapproche de la moyenne de ses voisins — et nous avons obtenu un monde où tout s'étale et où rien ne voyage : le barycentre de toute configuration est cloué sur place, à jamais. L'autopsie a livré la cause exacte : un état réduit à l'instant présent ne contient aucune information de direction. Aucune règle du premier ordre, si astucieuse soit-elle, ne fera jamais de mécanique.

Le remède est désormais sans mystère, et c'est l'état qui nous l'a soufflé : il faut que la mise à jour puisse consulter **deux instants**. Si un point connaît $u(t)$ *et* $u(t-1)$, alors le décalage entre les deux photographies encode « d'où vient » la configuration — une vitesse, sans le mot, sans vecteur, sans coordonnée. Une pure différence entre deux souvenirs.

Reste à écrire cette nouvelle règle. Et là, une surprise nous attend : en imposant nos exigences habituelles, plus une seule — que le futur et le passé jouent des rôles symétriques, comme dans toute la mécanique fondamentale —, la règle sera *presque entièrement forcée*. Et la première bosse que nous lancerons avec elle avancera d'un cran par pas de temps, sans se déformer, pour toujours.

> **Chapitre suivant — III. Pourquoi faut-il une mémoire ?**
> *Où l'on découvre qu'un souvenir suffit à fabriquer l'inertie.*

---

# Chapitre III — Pourquoi faut-il une mémoire ?

> **Question.** Que devient la dynamique si chaque point se souvient d'un instant de plus ?
>
> *Nous cherchons une règle. Nous allons découvrir qu'il n'y en a qu'une.*

## 1. Le cahier des charges

Le chapitre II s'est conclu sur un diagnostic précis : l'état du monde doit contenir **deux instants**, $u(t)$ et $u(t-1)$, faute de quoi aucune direction ne peut être mémorisée. La nouvelle règle aura donc la forme
$$
u(t+1) \;=\; F\bigl(u(t),\, u(t-1)\bigr).
$$
Mais laquelle ? Il y a *a priori* une infinité de fonctions $F$. Plutôt que d'en essayer une au hasard, dressons le cahier des charges complet — chaque exigence nous est déjà familière, sauf la dernière, qui est nouvelle et va tout verrouiller.

**(a) Localité.** Un point ne consulte que lui-même et ses voisins. D'après le chapitre I, toute dépendance spatiale passe donc par $u_v$ et $(Lu)_v$.

**(b) Linéarité.** *(Parcimonie, comme toujours : on ne complexifie que forcé.)*

**(c) Homogénéité.** Mêmes coefficients partout, et pour tous les temps : la loi ne dépend ni du lieu, ni de la date.

**(d) Un champ constant est inerte.** Un univers plat doit rester plat.

**(e) Réversibilité.** Voici la nouveauté. Nous exigeons que notre univers **ne perde pas d'information** : connaissant deux instants consécutifs, on doit pouvoir reconstituer le passé aussi bien que prédire le futur. Autrement dit, la loi doit pouvoir se lire dans les deux sens du temps.

Pourquoi imposer (e) ? D'abord par parcimonie encore : une loi irréversible *détruit* de l'information, et il faudrait expliquer où elle va — c'est une structure de plus, pas de moins. Ensuite parce que nous venons précisément de voir, au chapitre II, le visage d'un monde qui oublie : tout s'y dissout. La diffusion est irréversible (un brouillard uniforme ne « sait » plus de quelle bosse il provient), et c'est *exactement* le comportement dont nous cherchons à nous débarrasser. L'amnésie et l'étalement ne sont pas deux défauts, mais un seul.

## 2. La règle est forcée

Écrivons la forme la plus générale compatible avec (a)–(c) :
$$
u(t+1) \;=\; \alpha\, u(t) \;+\; \beta\, u(t-1) \;-\; \gamma\, L\,u(t) \;-\; \delta\, L\,u(t-1),
$$
avec quatre coefficients libres $\alpha, \beta, \gamma, \delta$. Faisons parler les deux dernières exigences.

**Le champ constant (d).** Pour $u \equiv c$, les termes en $L$ s'annulent (chapitre I : $L\mathbf 1 = 0$), et il reste $c = \alpha c + \beta c$, d'où
$$
\alpha + \beta = 1 .
$$

**La réversibilité (e).** Demandons que la loi, relue à rebours, soit *la même loi*. Renverser le temps, c'est échanger les rôles de $u(t+1)$ et $u(t-1)$. Réécrivons donc l'équation en isolant $u(t-1)$ :
$$
u(t-1) \;=\; -\frac{\alpha}{\beta}\,u(t) \;+\; \frac{1}{\beta}\,u(t+1) \;+\; \frac{\gamma}{\beta}\,L\,u(t) \;+\; \frac{\delta}{\beta}\,L\,u(t+1).
$$
Pour que cette lecture rétrograde ait la même forme que la lecture directe, il faut identifier les coefficients terme à terme : $\;1/\beta = \beta$, $\;-\alpha/\beta = \alpha$, $\;\gamma/\beta = -\gamma$, $\;\delta/\beta = -\delta$ avec le $L u(t\pm1)$ au bon poste. La seule solution non triviale est
$$
\beta = -1, \qquad \delta = 0,
$$
et donc, par (d), $\alpha = 2$. Il ne reste qu'un seul paramètre libre, le coefficient $\gamma$, que nous baptisons $c^2$ (le carré, dont le sens s'éclaircira, garantit le bon signe : le Laplacien doit *rappeler* les pics vers le bas, pas les amplifier). La règle est là :
$$
\boxed{\;u(t+1) \;=\; 2\,u(t) \;-\; u(t-1) \;-\; c^2\, L\,u(t).\;}
$$

Prenons le temps de mesurer ce qui vient de se passer. Nous ne l'avons pas *choisie* : localité, linéarité, homogénéité, inertie du champ plat et réversibilité ne laissaient **rien d'autre**. Le $2$ et le $-1$ ne sont pas des réglages : le $-1$ est la signature de la symétrie passé/futur, et le $2$ est son ombre portée par le champ constant. Quant au $\delta = 0$, il dit une chose élégante : la réversibilité interdit au Laplacien de s'appliquer ailleurs qu'à l'instant *présent* — le seul instant qui joue un rôle symétrique entre hier et demain.

**Vérification de (e), pour le plaisir.** De la règle on tire $u(t-1) = 2u(t) - u(t+1) - c^2 L u(t)$ : c'est *exactement la même formule*, lue dans l'autre sens. Notre univers est une horloge qui tourne aussi bien à l'envers. Rien ne s'y perd. (Le lecteur qui a fait de la mécanique reconnaîtra une différence seconde : $u(t+1) - 2u(t) + u(t-1)$ est l'accélération discrète, et notre règle s'écrit $\ddot u = -c^2 L u$. Nous venons d'écrire, sans le savoir, une loi de Newton — et, comme nous le verrons, une équation d'onde.)

## 3. L'expérience décisive

Assez d'algèbre : lançons une bosse. Plaçons-nous sur la chaîne avec $c = 1$ ; la règle devient adorablement simple. Puisque $(Lu)_n = 2u_n - u_{n-1} - u_{n+1}$ :
$$
u_n(t+1) \;=\; u_{n-1}(t) \;+\; u_{n+1}(t) \;-\; u_n(t-1).
$$

> « Chaque point somme ses voisins d'aujourd'hui, et soustrait son propre hier. »

Il nous faut maintenant une condition initiale — et c'est ici que la mémoire prend tout son sens. L'état, c'est *deux* photographies. Donnons au système la bosse $(1,2,1)$ centrée en $0$ à l'instant $t=0$, et **la même bosse, décalée d'un cran vers la gauche**, à l'instant $t=-1$ :
$$
\begin{array}{r|ccccccc}
n & -3 & -2 & -1 & 0 & 1 & 2 & 3\\ \hline
u_n(-1) & 0 & 1 & 2 & 1 & 0 & 0 & 0\\
u_n(0) & 0 & 0 & 1 & 2 & 1 & 0 & 0
\end{array}
$$
Ce décalage entre les deux souvenirs, c'est notre déclaration d'intention : « hier, l'objet était un cran plus à gauche ». Aucun vecteur, aucune coordonnée — une pure différence entre deux images. *C'est cela, une vitesse, dans un monde qui n'a que des voisins.*

Calculons $t = 1$, nœud par nœud :
$$
\begin{aligned}
u_{-2}(1) &= u_{-3}(0) + u_{-1}(0) - u_{-2}(-1) = 0 + 1 - 1 = \mathbf{0}\\
u_{-1}(1) &= u_{-2}(0) + u_{0}(0) - u_{-1}(-1) = 0 + 2 - 2 = \mathbf{0}\\
u_{0}(1) &= u_{-1}(0) + u_{1}(0) - u_{0}(-1) = 1 + 1 - 1 = \mathbf{1}\\
u_{1}(1) &= u_{0}(0) + u_{2}(0) - u_{1}(-1) = 2 + 0 - 0 = \mathbf{2}\\
u_{2}(1) &= u_{1}(0) + u_{3}(0) - u_{2}(-1) = 1 + 0 - 0 = \mathbf{1}
\end{aligned}
$$
Résultat :
$$
u(1) = (\dots,\ 0,\ 0,\ 0,\ 1,\ 2,\ 1,\ 0,\ \dots)
$$
La bosse $(1,2,1)$ est maintenant sur $(0,1,2)$. **Elle a avancé d'un cran vers la droite, sans se déformer.** Et le nouvel état — $u(1)$ décalé d'un cran par rapport à $u(0)$ — est la copie conforme de l'état initial, translaté : le pas suivant la fera avancer encore, et encore, indéfiniment. Personne ne pousse. Rien ne la guide. Elle continue, parce que rien ne l'arrête.

Nous venons d'assister à la naissance de l'**inertie**.

## 4. L'autopsie du miracle

Ne laissons pas passer ce moment sans comprendre *où*, dans le calcul, la direction s'est jouée. Regardons les deux nœuds critiques.

**À l'arrière ($n = -1$) :** les voisins apportent $0 + 2 = 2$… et le souvenir soustrait $2$. Annulation *exacte*. La moitié de l'onde qui voulait repartir vers la gauche est détruite par le terme $-u(t-1)$ — le passé de ce nœud, où la bosse se tenait, agit comme un contre-signal.

**À l'avant ($n = 1$) :** les voisins apportent $2 + 0 = 2$, et le souvenir ne retranche rien ($u_1(-1) = 0$ : la bosse n'était pas encore passée par là). Tout le signal survit.

Le mécanisme est donc une **interférence** : destructive vers l'arrière, libre vers l'avant. Le terme de mémoire ne stocke pas une flèche ; il stocke *l'empreinte du passage*, et cette empreinte suffit à casser la symétrie gauche/droite que la diffusion, elle, ne pouvait jamais briser. Voilà la réponse, au niveau du pas $t \to t+1$, à l'impossibilité du chapitre II : deux films différents ne passent plus par le même état, car l'état contient maintenant l'image précédente du film.

On peut même le dire en théorème. Sur la chaîne avec $c=1$, prenons *n'importe quel* profil $f$ et posons $u_n(t) = f(n - t)$ — le profil qui glisse d'un cran par pas. Alors
$$
u_{n-1}(t) + u_{n+1}(t) - u_n(t-1) = f(n-1-t) + f(n+1-t) - f(n-t+1) = f(n-1-t) = u_n(t+1). \checkmark
$$
**Tout profil translaté uniformément est une solution exacte.** Le mouvement rectiligne uniforme n'est pas une solution approchée ou privilégiée de notre univers : c'est une solution *parfaite*. Un objet libre continue tout droit, à vitesse constante, pour l'éternité — nous venons de démontrer la première loi de Newton, dans un monde qui ne sait même pas ce qu'est une droite.

> **Le déclic.** L'inertie n'est pas une propriété des objets. C'est une propriété de la *mémoire*. Un monde du premier ordre oublie et diffuse ; un monde du second ordre se souvient d'une image, et cette unique image suffit à entretenir le mouvement à jamais. « Masse point n'en faut » : il a suffi d'un souvenir.

## 5. Deux honnêtetés avant de fêter ça

**Première honnêteté : le rôle de $c$.** Le miracle du §3 utilise $c = 1$ sur la chaîne. Pour $c \neq 1$, ou pour un profil lancé « entre deux vitesses », la bosse avance *mais se déforme lentement* — un phénomène que nous disséquerons au chapitre VI (il porte un nom : la dispersion, et il est une signature profonde des mondes discrets). Retenons pour l'instant le résultat robuste : le **second ordre transporte**, là où le premier ordre étale. La qualité du transport, elle, dépendra de la géométrie — et c'est une richesse, pas un défaut.

**Seconde honnêteté : le nom de l'équation.** Notre règle $\ddot u = -c^2 Lu$ est la version discrète de
$$
\partial_t^2 u = c^2\, \Delta u,
$$
qui est l'**équation d'onde** — celle des cordes vibrantes, des membranes, du son. Le lecteur est en droit de tiquer : nous voulions une *particule*, et l'équation que nos axiomes nous ont imposée est celle des *ondes* ? Ce n'est pas un accident de parcours, et nous ne le balayerons pas sous le tapis : c'est peut-être la leçon la plus profonde de tout le livre, et nous lui consacrerons un interlude entier le moment venu. Pour l'instant, une chose est sûre : notre bosse, onde ou pas, avance tout droit.

## 6. Où nous en sommes

Nous avons exigé une mémoire, et cinq contraintes — localité, linéarité, homogénéité, inertie du plat, réversibilité — ont forcé une règle unique : $u(t+1) = 2u(t) - u(t-1) - c^2 Lu(t)$. Lancée sur la chaîne, elle transporte une bosse sans la déformer, d'un cran par pas de temps, pour toujours ; et nous avons vu le mécanisme à l'œuvre, une interférence destructive vers l'arrière orchestrée par le terme de mémoire. La première loi de Newton est devenue un théorème.

Mais un physicien qui découvre une dynamique ne demande pas d'abord « quels sont ses mouvements élégants ? ». Il demande :

> **« Puis-je lui faire confiance ? »**

Si je laisse tourner cette règle un million de pas, qu'est-ce qui me garantit qu'elle ne fabrique pas du mouvement à partir de rien — qu'une petite bosse ne va pas, quelque part, enfler sans cause jusqu'à dévorer l'univers ? La réversibilité y fait penser (rien ne se perd…), mais elle ne le *prouve* pas : il nous faudrait une quantité, calculable sur l'état, dont nous puissions démontrer qu'elle ne change **jamais**. Notre univers en possède-t-il une ?

Nous ne savons même pas encore comment une telle chose pourrait s'écrire. Nous allons la chercher — et nous essuierons quelques échecs instructifs avant de la trouver.

> **Chapitre suivant — IV. Comment savoir si notre univers triche ?**
> *À la recherche de ce qui ne peut être ni créé, ni détruit.*

---

# Chapitre IV — Comment savoir si notre univers triche ?

> **Question.** Existe-t-il une quantité que notre univers ne puisse ni créer, ni détruire ?
>
> *À ce stade, le mot « énergie » n'a jamais été prononcé. Nous ne savons pas ce que c'est. C'est précisément ce que nous allons découvrir.*

## 1. Pourquoi la confiance est un problème mathématique

Nous tenons une règle, et elle est belle. Mais avant de bâtir quoi que ce soit dessus, il faut répondre à une inquiétude de fond : si nous la laissons tourner un million de pas, comment savoir qu'elle ne fabrique pas du mouvement à partir de rien ? Qu'une petite ondulation, quelque part, ne va pas enfler sans cause jusqu'à tout submerger ?

On pourrait croire que la réversibilité nous protège : rien ne se perd, donc rien ne se crée ? Hélas, non — et il vaut la peine de le voir de ses yeux. Prenons l'état initial le plus innocent : $u(-1) = 0$ partout, et $u(0) = \delta_0$ (un seul point à $1$). Suivons la somme totale $S(t) = \sum_v u_v(t)$ au fil des pas. En sommant la règle sur tous les nœuds, le terme de Laplacien s'évanouit (chaque arête donne $+$ d'un côté ce qu'elle donne $-$ de l'autre : $\mathbf{1}^\top L = 0$), et il reste
$$
S(t+1) = 2S(t) - S(t-1).
$$
Avec $S(-1)=0$, $S(0)=1$, on trouve $S(1)=2$, $S(2)=3$, $S(3)=4$… **La quantité totale de champ croît linéairement, pour toujours.** Notre univers, pourtant parfaitement réversible, gonfle. La réversibilité garantit qu'on peut *rembobiner* le film ; elle ne garantit nullement que le film soit raisonnable.

Il nous faut donc autre chose : une grandeur $E$, calculable sur l'état, dont on puisse **démontrer** qu'elle ne change jamais :
$$
E(t+1) = E(t) \qquad \text{pour toute solution, sur tout graphe.}
$$
Si une telle grandeur existe et qu'elle contrôle la taille du champ, alors aucune explosion n'est possible : l'univers ne peut pas tricher, car le juge de paix est conservé. Toute la question est : *existe-t-elle ?*

Fixons les règles de la chasse. La quantité devra être calculée à partir de l'état complet — nous savons depuis le chapitre II que l'état, ce sont **deux photographies**, $u(t)$ et $u(t-1)$ ; il serait naïf de l'oublier maintenant. Elle devra être la même formule partout et à tout instant (homogénéité). Et elle devra être conservée *exactement* — pas approximativement, pas en moyenne.

## 2. Premier suspect : la somme totale

Le calcul du §1 semble condamner $S$, mais regardons-le mieux, car il cache un trésor. L'équation $S(t+1) = 2S(t) - S(t-1)$ se réécrit
$$
S(t+1) - S(t) \;=\; S(t) - S(t-1).
$$
La somme n'est pas conservée — mais **son accroissement l'est**. La quantité $P = S(t) - S(t-1)$, la « vitesse du total », est rigoureusement constante, sur tout graphe, pour toute solution. Nous venons de trouver, presque par accident, notre *première* loi de conservation !

Rangeons-la précieusement : cette grandeur, différence entre les deux photographies, sent la quantité de mouvement à plein nez, et nous la retrouverons. Mais elle ne peut pas être notre gardienne. D'abord parce qu'elle ne borne rien (dans notre exemple, $P = 1$ est constant… pendant que le champ enfle). Ensuite parce qu'elle est aveugle à la forme : elle vaut $0$ pour la bosse au repos comme pour deux bosses fonçant l'une vers l'autre. Un juge de paix doit voir *l'agitation* du monde, pas seulement son bilan comptable.

## 3. Deuxième suspect : la taille de la photographie

Cherchons donc une grandeur qui mesure « combien il se passe de choses ». Le réflexe du géomètre : la norme du champ,
$$
N(t) = \sum_v u_v(t)^2 .
$$
Elle est positive, grande quand le champ s'agite, nulle quand tout est éteint. Testons-la sur l'expérience la plus simple qui soit : un point excité *au repos*, $u(-1) = u(0) = \delta_0$, sur la chaîne avec $c=1$. Un pas de calcul : $u(1) = \delta_0 - L\delta_0 = (\dots, 0, 1, -1, 1, 0, \dots)$. D'où
$$
N(0) = 1, \qquad N(1) = 3.
$$
Verdict immédiat : $N$ a triplé en un pas. (Elle continuera : $5, 7, 9, \dots$ — le pic se brise en deux ondes qui s'éloignent, et la norme instantanée compte mal ce qui est en transit.) La photographie seule, même au carré, ne connaît pas l'histoire. Suspect suivant.

## 4. Troisième suspect : la rugosité

Le chapitre I nous avait légué une suspecte toute désignée : l'**énergie de Dirichlet**,
$$
D(t) = u(t)^\top L\, u(t) = \sum_{\{v,w\} \in E} \bigl(u_v(t) - u_w(t)\bigr)^2,
$$
la seule forme quadratique que le graphe nous offre naturellement. Elle mesure la rugosité du champ — combien il est *tendu*. Sur la même expérience : $D(0) = 2$, $D(1) = 10$, puis $18, 26, 34, \dots$ Échec encore, mais un échec qui *parle*. Comparons nos deux configurations à photographie identique : la bosse au repos ($u(t) = u(t-1)$) et la bosse en mouvement (chapitre III). Même photo, même rugosité — et pourtant l'une reste sur place pendant que l'autre file. Ce que $D$ ne voit pas, c'est le **mouvement** ; et ce que $N$ et $D$ paient toutes les deux, c'est de n'avoir regardé qu'*une* photographie sur les deux que contient l'état.

Le lecteur qui a déjà vu un pendule reconnaîtra la situation. Au sommet de l'oscillation, tout est dans la *forme* (le pendule est haut, immobile) ; au passage du bas, tout est dans le *mouvement*. Aucune des deux grandeurs n'est conservée seule : elles s'échangent. Si notre univers possède un invariant, ce doit être une **somme** de deux termes — un terme de forme, et un terme de mouvement.

## 5. Construire le terme de mouvement

Qu'est-ce que « le mouvement », dans notre monde ? Nous l'avons dit et redit : c'est le décalage entre les deux souvenirs. Le candidat naturel pour l'agitation est donc
$$
K(t) \;=\; \tfrac{1}{2} \sum_v \bigl(u_v(t) - u_v(t-1)\bigr)^2 \;=\; \tfrac12\,\|u(t) - u(t-1)\|^2 ,
$$
la taille de la *différence* des photographies. (Le facteur $\tfrac12$ est cosmétique ; il allégera les calculs.) Et le terme de forme sera un multiple de la rugosité. Essayons donc, en toute innocence :
$$
E_?(t) \;=\; \tfrac12\,\|u(t) - u(t-1)\|^2 \;+\; \tfrac{c^2}{2}\, u(t)^\top L\, u(t).
$$
On lance le calcul de $E_?(t+1) - E_?(t)$… et il ne tombe pas à zéro. Il reste un petit résidu, d'ordre $c^4$ — minuscule si $c$ est petit, mais nous avons juré : *exactement* conservé, ou rien. D'où vient ce résidu ? D'une dissymétrie que nous aurions dû flairer : le terme cinétique enjambe les deux instants $t-1$ et $t$, tandis que notre terme de forme est perché sur le seul instant $t$. Toute notre dynamique respecte scrupuleusement la symétrie des instants ; notre candidat la violait. Corrigeons : faisons enjamber la rugosité, elle aussi, en la calculant *entre* les deux photographies :
$$
\boxed{\;E(t) \;=\; \tfrac{1}{2}\,\bigl\|u(t) - u(t-1)\bigr\|^2 \;+\; \tfrac{c^2}{2}\;u(t)^\top L\, u(t-1).\;}
$$

**Théorème.** $E(t+1) = E(t)$ pour toute solution de la règle, sur tout graphe. *Exactement.*

*Démonstration* (quatre lignes, et elles valent la peine). Notons $\Delta_\pm = u(t\pm1) - u(t)$. La règle s'écrit $\Delta_+ + \Delta_- = -c^2 L u(t)$, c'est-à-dire $u(t+1) - u(t-1)$ multiplié scalairement par n'importe quoi se manie bien. Calculons :
$$
E(t+1) - E(t) = \tfrac12\Bigl(\|u(t{+}1) - u(t)\|^2 - \|u(t) - u(t{-}1)\|^2\Bigr) + \tfrac{c^2}{2}\Bigl(u(t{+}1)^\top L u(t) - u(t)^\top L u(t{-}1)\Bigr).
$$
Le premier bloc se factorise ($a^2 - b^2$) :
$$
\tfrac12\,\bigl(u(t{+}1) - u(t{-}1)\bigr)^\top \bigl(u(t{+}1) - 2u(t) + u(t{-}1)\bigr) \;=\; -\tfrac{c^2}{2}\,\bigl(u(t{+}1) - u(t{-}1)\bigr)^\top L\,u(t),
$$
en utilisant la règle. Le second bloc, grâce à la **symétrie de $L$** (chapitre I : $u^\top L w = w^\top L u$), vaut $\tfrac{c^2}{2}\,\bigl(u(t{+}1) - u(t{-}1)\bigr)^\top L\, u(t)$. Les deux blocs sont opposés. Leur somme est nulle. $\blacksquare$

Prenons une seconde pour admirer la mécanique de la preuve : le terme cinétique produit un excédent, le terme de forme produit exactement le déficit opposé, et c'est la *symétrie du Laplacien* — une propriété que nous avions rangée au chapitre I « pour plus tard » — qui garantit l'équilibre. Rien n'est de trop.

Et vérifions sur pièces. La bosse mobile du chapitre III : $E = \tfrac52$ à tout instant, pendant qu'elle voyage. Le pic au repos du §3, celui qui faisait exploser tous nos suspects ($N: 1,3,5,\dots$ ; $D: 2,10,18,\dots$) : $E = 1, 1, 1, 1, \dots$ Imperturbable. Pendant que le pic se brise, que les ondes filent, que toutes les grandeurs naïves s'affolent, cette combinaison précise — et aucune autre — reste clouée à sa valeur initiale.

## 6. Savourer, puis nommer

Arrêtons-nous. Ce qui vient de se produire mérite qu'on le dise lentement.

> Nous avons trouvé quelque chose que notre univers **ne sait ni créer, ni détruire**.

Ce n'est pas un règlement que nous avons imposé : c'est un théorème que la règle — elle-même forcée par nos axiomes — porte en elle sans nous avoir demandé notre avis. Notre univers jouet, bâti sur presque rien, est *incapable de tricher* : quoi qu'il arrive, quelque configuration baroque que l'on prépare, une certaine quantité de « quelque chose » est fixée une fois pour toutes à l'instant initial, et le monde ne fera plus que la faire circuler.

Les physiciens ont un nom pour ce type de grandeur. Ils l'appellent l'**énergie**. Et les deux morceaux de notre formule portent leurs noms aussi : $\tfrac12\|u(t) - u(t-1)\|^2$ est l'énergie **cinétique** — celle du mouvement, le carré de notre « vitesse sans vecteurs » ; $\tfrac{c^2}{2}\,u^\top L u'$ est l'énergie **potentielle** — celle de la forme, stockée dans la tension des arêtes ($u^\top L u' = \sum_{\{v,w\}} (u_v - u_w)(u'_v - u'_w)$ : chaque arête tendue est un petit ressort bandé). Le pendule du §4 était la bonne image : notre univers passe son temps à convertir de la forme en mouvement et réciproquement, sous le contrôle d'un total inflexible.

> **Le déclic.** L'énergie n'est pas un ingrédient de la physique : c'est un *certificat*. Elle n'a pas été mise dans les axiomes — elle en a émergé comme la quantité exacte que la dynamique s'interdit de toucher. Un univers n'a pas *besoin* qu'on lui donne une énergie ; il suffit qu'il soit local, linéaire, homogène et réversible, et il s'en fabrique une tout seul.

## Aparté — d'où viennent les lois de conservation ?

Avant d'aller plus loin, une question de curiosité : pourquoi cette conservation *existe-t-elle* ? On peut suivre la preuve du §5 ligne à ligne et rester sur sa faim — le calcul montre que ça marche, pas *pourquoi* ça devait marcher. Relisons alors nos axiomes du chapitre III. L'exigence (c) contenait une clause discrète, presque anodine : les coefficients de la règle sont les mêmes *à tout instant* — la loi ne connaît pas la date. Un pas de temps effectué aujourd'hui ou dans mille ans est le même pas de temps. Or une grandeur conservée, c'est précisément une grandeur qui ne dépend pas de la date à laquelle on la mesure… Simple jeu de mots ? Vérifions sur notre autre trouvaille. Au §2, l'accroissement du total, $P = S(t) - S(t-1)$, s'est révélé conservé — et la raison calculatoire était $\mathbf 1^\top L = 0$, c'est-à-dire (chapitre I) que la règle est insensible à l'ajout d'une constante : $u \mapsto u + \alpha\mathbf 1$ transforme toute solution en solution. Là encore, une **indifférence** de la loi (au niveau zéro du champ) se tient juste derrière une **conservation**.

Deux conservations, et à chaque fois, tapie derrière, une symétrie de la loi : l'indifférence à la date pour l'énergie, l'indifférence à l'origine du champ pour $P$. Deux coïncidences, c'est déjà une piste. Il se trouve — et c'est l'un des plus beaux théorèmes de toute la physique, dû à Emmy Noether — que ce n'est pas une piste mais une loi : *à chaque symétrie de la dynamique correspond une quantité conservée, et réciproquement*. Nous ne le démontrerons pas aujourd'hui. Mais gardons la grille de lecture, car elle transforme la suite du livre en jeu de piste : chaque fois que notre univers présentera une indifférence — et le graphe en cache une de taille, l'indifférence au *lieu* — nous saurons qu'un trésor conservé l'accompagne quelque part. Celui-là s'appellera la quantité de mouvement, et c'est le chapitre VII qui ira le déterrer.

## 7. Deux honnêtetés

**Ce que la conservation garantit — et à quelle condition.** Il faut être précis sur ce que notre théorème achète. Une quantité conservée n'interdit l'explosion que si elle *contrôle la taille* du champ. Le raisonnement type est celui-ci : si $E$ est une somme de carrés (donc positive), alors chaque carré est majoré par $E$ ; une configuration ne peut grossir sans faire grossir l'un des carrés, donc sans faire grossir $E$ — ce qui est interdit. La conservation devient une **laisse**. Mais si $E$ peut prendre des valeurs négatives quelque part, la laisse casse : un terme peut croître vers $+\infty$ pendant qu'un autre plonge vers $-\infty$, à total constant. Une grandeur conservée mais non positive est un bilan comptable, pas un garde-fou.

Or notre $E$ est-elle une somme de carrés ? Le terme cinétique, oui. Mais le terme croisé $u(t)^\top L\,u(t-1)$ mélange deux photographies différentes, et rien ne l'empêche *a priori* d'être négatif. Pour trancher, changeons de variables — posons la **somme** et la **différence** des deux photographies, $s = u(t) + u(t-1)$ et $d = u(t) - u(t-1)$. Un petit calcul d'identité remarquable (le fidèle $ab = \frac{(a+b)^2 - (a-b)^2}{4}$, version matricielle) donne $u(t)^\top L\, u(t-1) = \tfrac14\bigl(s^\top L s - d^\top L d\bigr)$, et notre énergie se réécrit :
$$
E \;=\; \tfrac{1}{2}\, d^\top\!\Bigl(I - \tfrac{c^2}{4}L\Bigr) d \;+\; \tfrac{c^2}{8}\, s^\top L\, s .
$$
Tout devient lisible. Le second terme est une rugosité (chapitre I, §5) : toujours positif. Le premier est positif à une condition : que la matrice $I - \tfrac{c^2}{4}L$ le soit, c'est-à-dire que $\tfrac{c^2}{4}\,d^\top L d$ ne dépasse jamais $\|d\|^2$. Or il existe un nombre, attaché au graphe, qui mesure précisément *le pire facteur d'amplification* de $L$ : le plus grand $\lambda$ tel que $Lx = \lambda x$ ait une solution, noté $\lambda_{\max}$, pour lequel $x^\top L x = \lambda_{\max}\|x\|^2$. La condition devient limpide :
$$
c^2\, \lambda_{\max} \;\le\; 4 \quad\Longleftrightarrow\quad E \text{ est une somme de carrés} \quad\Longrightarrow\quad \text{aucune explosion possible.}
$$

Et si l'on viole le seuil ? La conservation tient toujours — le théorème du §5 est inconditionnel — mais la laisse est cassée, et l'univers en profite. Démonstration par l'exemple, sur le graphe le plus petit qui soit : deux nœuds, une arête ($\lambda_{\max} = 2$), et $c^2 = 3$, en infraction ($3 \times 2 > 4$). Partons d'un souffle : $u(0) = (0{,}01,\, -0{,}01)$, $u(-1) = 0$. On laisse tourner : au pas $5$, le champ vaut $\approx 8$ ; au pas $8$, $\approx 400$ ; au pas $11$, plus de $20\,000$ — croissance exponentielle, un facteur $2$ millions en douze pas. Et pendant tout ce temps, $E = 0{,}0001$, imperturbable : le terme cinétique explose vers $+\infty$, le terme croisé plonge vers $-\infty$, et leur somme reste exacte à la dixième décimale. L'univers ne *triche* pas — le bilan est scrupuleusement tenu — mais il *diverge* quand même. Moralité : il ne suffit pas qu'une grandeur soit conservée ; il faut qu'elle soit conservée **et** qu'elle borne.

Voilà qui est intrigant à double titre. D'abord, notre univers n'est digne de confiance que si sa vitesse de propagation $c$ respecte un plafond fixé par la *structure du graphe* : les mondes trop rapides pour leur géométrie sont instables. (Un univers qui impose une vitesse limite, notée $c$ de surcroît, à laquelle nul signal ne peut se soustraire sous peine de catastrophe… toute ressemblance avec une célèbre constante de la physique serait, bien entendu, purement fortuite. Soyons honnêtes : notre plafond est un seuil de *stabilité*, pas un principe de relativité, et l'analogie ne doit pas être poussée trop loin. Mais elle n'est pas creuse non plus : la localité impose déjà à toute information de progresser d'au plus une arête par pas de temps — notre monde possède un authentique cône causal — et la condition $c^2\lambda_{\max} \le 4$ dit en substance que la dynamique ne doit pas prétendre aller plus vite que ce que le tissu de l'univers peut transmettre. Un monde où l'on force l'allure au-delà de sa causalité ne viole pas ses lois : il explose. C'est une leçon que la physique discrète partage, au minimum, avec la nôtre.) Ensuite, ce plafond fait intervenir un objet d'apparence purement algébrique — la plus grande valeur propre de $L$ — surgi ici sans qu'on l'invite, dans une question de pure physique. Nous ne savons pas encore ce que *sont* les vecteurs propres de $L$, ni pourquoi le pire d'entre eux gouverne la stabilité du monde entier. C'est précisément ce que le chapitre suivant va élucider — et la réponse dépassera largement cette question de seuil.

**Le décalage temporel du potentiel.** Le lecteur pointilleux aura noté que notre énergie potentielle enjambe deux instants, là où la version continue ($\tfrac12\|\dot u\|^2 + \tfrac{c^2}{2}u^\top L u$) vit à un seul. Ce n'est pas une maladresse : c'est la signature des mondes à temps discret, où *aucune* grandeur d'un seul instant ne peut être exactement conservée (nos suspects 2 et 3 en ont témoigné). Quand le pas de temps devient infime, $u(t-1) \to u(t)$ et l'on retrouve la formule continue. Les spécialistes du calcul numérique connaissent bien ce phénomène : les bons schémas conservent exactement une énergie « ombre », légèrement décalée de l'énergie continue. La nôtre est de cette famille — sauf qu'ici, personne n'approxime personne : c'est *l'énergie exacte de notre univers*, qui se trouve être discret.

## 8. Où nous en sommes

Nous avons cherché un juge de paix, essuyé trois échecs — chacun instructif : la somme nous a offert en lot de consolation notre première loi de conservation (l'accroissement du total, que nous soupçonnons d'être une quantité de mouvement) ; la norme et la rugosité nous ont appris qu'aucune grandeur d'une seule photographie ne peut être conservée ; le pendule nous a soufflé qu'il fallait une somme forme + mouvement. La symétrisation entre les deux instants a fait le reste, et le théorème est tombé : notre univers conserve exactement une quantité, que nous avons méritée avant de la nommer énergie.

Nous pouvons désormais faire confiance à la dynamique. Il est temps de l'explorer en grand. Une évolution quelconque — plusieurs bosses, des collisions, du désordre — semble inextricable : chaque nœud tire sur chaque voisin, tout dépend de tout. Mais nous détenons deux indices convergents. La dynamique est *linéaire* : la somme de deux solutions est une solution — tout état est donc superposition d'états plus simples, si nous savons trouver les briques. Et voilà que $\lambda_{\max}$, une *valeur propre* du Laplacien, vient de surgir dans une question de pure physique. Deux doigts pointés vers la même porte :

> Existe-t-il des configurations qui évoluent **sans changer de forme** — des mouvements si simples que la dynamique se contente de les faire respirer sur place ? Et toute évolution, même la plus baroque, ne serait-elle qu'un accord joué sur ces notes-là ?

> **Chapitre suivant — V. Quels sont les objets élémentaires de cette dynamique ?**
> *Où l'univers révèle ses notes de musique.*

---

# Chapitre V — Quels sont les objets élémentaires de cette dynamique ?

> **Question.** Existe-t-il des formes qui survivent à leur propre évolution ?
>
> *Jusqu'ici, tout ce que nous avons lancé s'est brisé, étalé, ou transformé — sauf une bosse, sur un graphe très spécial. Nous cherchons les configurations que la dynamique respecte.*

## 1. Le problème : tout dépend de tout

Prenons un graphe quelconque et une configuration quelconque — trois bosses, un pic, du bruit. À chaque pas, chaque nœud tire sur tous ses voisins, qui tirent sur les leurs : au bout de dix pas, la moindre valeur dépend de milliers d'autres. Suivre l'évolution nœud par nœud est sans espoir, et surtout sans *lumière* : même en calculant tout, on ne comprendrait rien.

Face à un système inextricable, la stratégie du physicien est toujours la même : chercher les **mouvements les plus simples possibles**, puis tenter d'exprimer tout le reste comme un assemblage de ces mouvements-là. Et nous détenons, depuis le chapitre III, la clé qui rend cette stratégie légitime : notre règle est *linéaire*. Si $u(t)$ et $w(t)$ sont deux solutions, alors $u(t) + w(t)$ est une solution, et $\mu\, u(t)$ aussi. Les solutions se superposent sans se voir. Il suffirait donc de trouver une famille de solutions simples engendrant toutes les autres, et l'évolution la plus baroque deviendrait une somme d'évolutions triviales.

Reste à savoir ce que « simple » veut dire. C'est ici que la question du chapitre prend tout son sens.

## 2. Qu'est-ce qu'une forme qui survit ?

Faisons l'inventaire de ce que la dynamique a fait subir à nos objets jusqu'ici. La bosse du chapitre II s'est *dissoute*. Le pic du chapitre IV s'est *brisé* en ondes filantes. La bosse du chapitre III, elle, a survécu — mais sur un graphe d'une régularité parfaite, avec une vitesse d'exception ($c = 1$), et nous avons prévenu que ce miracle était fragile. La question devient donc : sur un graphe **quelconque**, existe-t-il des configurations que l'évolution ne défigure pas ?

Précisons « ne pas défigurer ». Le champ a le droit de changer — tout champ figé serait vite ennuyeux — mais nous demandons que sa *forme* demeure : que le profil à l'instant $t$ soit toujours **proportionnel** au profil initial. Toute l'évolution serait alors portée par un seul nombre, une amplitude globale :
$$
u(t) \;=\; a(t)\,\varphi,
$$
où $\varphi$ est un profil fixe (un nombre par nœud, choisi une fois pour toutes) et $a(t)$ une amplitude qui évolue. La forme reste, seule l'intensité respire.

Prenons le temps de bien voir ce que cette écriture impose, car elle est plus restrictive qu'il n'y paraît. Chaque nœud $v$ se voit attribuer son coefficient personnel $\varphi_v$, une fois pour toutes ; et à l'instant $t$, sa valeur est $a(t)\,\varphi_v$ — *le même* facteur $a(t)$ pour tout le monde. Tous les nœuds montent et descendent **en bloc**, chacun à l'échelle de son coefficient : celui qui vaut le double d'un autre vaudra le double de cet autre à tout jamais. Le rapport entre deux nœuds quelconques est gravé dans le marbre. Autrement dit — et c'est le point qu'il ne faut pas rater — **rien ne circule** : le nœud $3$ ne « reçoit » jamais ce que portait le nœud $1$, aucun motif ne se déplace de proche en proche. C'est une photographie dont on tourne le bouton de contraste : l'image peut s'intensifier, pâlir, s'inverser (si $a(t)$ change de signe, tous les nœuds basculent *simultanément*), mais c'est toujours la même image. Un chœur où chaque chanteur a sa nuance attitrée, et qui enfle et diminue d'un seul souffle. Voilà notre définition d'un objet élémentaire : **une forme que la dynamique se contente de faire respirer**.

De telles formes existent-elles ? Injectons l'hypothèse dans la règle :
$$
a(t+1)\,\varphi \;=\; 2a(t)\,\varphi - a(t-1)\,\varphi - c^2 a(t)\, L\varphi .
$$
Tout, dans cette équation, est proportionnel à $\varphi$ — sauf le dernier terme. Pour que l'égalité puisse tenir avec $a(t)$ scalaire, il n'y a pas le choix : il faut que $L\varphi$ soit lui-même proportionnel à $\varphi$,
$$
\boxed{\;L\varphi = \lambda\,\varphi\;}
$$
pour un certain nombre $\lambda$. Et alors l'équation vectorielle s'effondre en une équation sur la seule amplitude :
$$
a(t+1) \;=\; \bigl(2 - c^2\lambda\bigr)\,a(t) \;-\; a(t-1).
$$

Arrêtons-nous, car c'est un moment important du livre. La condition $L\varphi = \lambda\varphi$ définit ce que les mathématiciens appellent un **vecteur propre** de $L$, de **valeur propre** $\lambda$. Dans la plupart des cours, ces objets sont introduits comme un outil algébrique, et l'étudiant apprend à les calculer avant de savoir à quoi ils servent. Ici, le rapport est inversé : nous ne les avons pas choisis, nous les avons *trouvés* — ce sont exactement, et uniquement, **les formes que la dynamique transporte sans les défigurer**. Chercher les vecteurs propres du Laplacien, ce n'est pas faire de l'algèbre : c'est dresser le catalogue des objets élémentaires de l'univers.

## 3. Le catalogue existe, et il est complet

Deux questions immédiates : ces formes existent-elles toujours ? Et sont-elles assez nombreuses pour engendrer tout le reste ? C'est ici qu'un placement de chapitre I arrive à maturité. Nous y avions noté, « pour plus tard », que $L$ est une matrice **symétrique réelle**. Or l'algèbre linéaire réserve à ces matrices son plus beau théorème, le *théorème spectral* : toute matrice symétrique réelle de taille $N$ possède exactement $N$ vecteurs propres, à valeurs propres réelles, formant une **base orthonormée** de l'espace tout entier.

Traduisons chaque mot en physique. *Exactement $N$* : un graphe à $N$ nœuds possède $N$ formes élémentaires, ni plus ni moins — le catalogue est fini et complet. *Base* : **toute** configuration $u$ s'écrit, de façon unique, comme superposition
$$
u = \sum_{j} a_j\, \varphi_j
$$
des formes du catalogue — aucun état, si biscornu soit-il, n'échappe à la décomposition. *Orthonormée* : les formes sont mutuellement « perpendiculaires », chacune est aveugle aux autres, et le coefficient $a_j$ se lit par simple projection. Et nous savons même où vivent les valeurs propres : la positivité de $L$ (chapitre I, §5 : $u^\top L u \ge 0$) impose $\lambda \ge 0$, et nous connaissons déjà le bas du catalogue — $L\mathbf 1 = 0$ : la première forme élémentaire de tout univers est le champ constant, avec $\lambda = 0$.

## 4. Que fait chaque forme ? Elle sonne.

Reste à résoudre la dynamique d'une amplitude : $a(t+1) = (2 - c^2\lambda)\,a(t) - a(t-1)$. C'est une récurrence à coefficients constants ; cherchons des solutions oscillantes $a(t) = \cos(\omega t + \phi)$. L'identité $\cos(\omega(t{+}1)) + \cos(\omega(t{-}1)) = 2\cos\omega\,\cos(\omega t)$ montre que cela fonctionne exactement quand
$$
2\cos\omega = 2 - c^2\lambda, \qquad\text{c'est-à-dire}\qquad \sin^2\!\frac{\omega}{2} = \frac{c^2\lambda}{4}.
$$
Chaque forme du catalogue, laissée à elle-même, **oscille sur place** — elle ne voyage pas, elle ne se déforme pas, elle *vibre*, à une fréquence $\omega(\lambda)$ dictée par sa valeur propre : les formes lisses (petit $\lambda$, faible rugosité) vibrent lentement, les formes hérissées (grand $\lambda$) vibrent vite. Un lecteur musicien a déjà tout compris : les vecteurs propres sont les **harmoniques** de l'univers, et $\omega(\lambda)$ est la hauteur de chaque note. Une corde de guitare ne fait rien d'autre : ses modes propres sont la fondamentale et les harmoniques, chacun vibrant sur place à sa fréquence — et une corde pincée n'importe comment joue un *accord*, la superposition de ses modes. Notre univers est un instrument. Le graphe est sa lutherie : c'est la géométrie qui fixe le catalogue des notes.

La formule contient deux dividendes, qu'il ne faut pas laisser filer.

**Le seuil du chapitre IV s'explique enfin.** Pour que $\omega$ existe, il faut $\sin^2(\omega/2) = c^2\lambda/4 \le 1$, soit $c^2\lambda \le 4$. Si le graphe contient une forme trop rugueuse ($c^2\lambda_{\max} > 4$), l'équation n'a plus de solution oscillante : la récurrence bascule vers des solutions **exponentielles**, et c'est précisément ce mode-là qui explosait dans notre expérience des deux nœuds. Donnons-lui un visage, car il en a un : sur ce graphe, le catalogue ne contient que deux formes, le fond uniforme $(1,1)$ et la *bascule* $(1,-1)$ — un nœud en haut, l'autre en bas, la forme la plus hérissée possible ($\lambda = 2$, le maximum). C'est elle qui divergeait : à chaque pas, le champ restait une bascule parfaite — les deux nœuds rigoureusement opposés, la *forme* jamais défigurée — mais son amplitude était multipliée par un facteur constant supérieur à $1$. Une note qui garde son timbre et dont le volume double sans fin. La « limite de vitesse » du chapitre IV n'était donc pas une bizarrerie comptable : c'est la condition pour que *toutes les notes de l'instrument soient jouables*. Un univers trop rapide pour sa géométrie possède une note qui hurle.

**Le mode $\lambda = 0$ ne sonne pas, il dérive.** Pour le champ constant, la récurrence devient $a(t+1) = 2a(t) - a(t-1)$ : croissance *linéaire*, $a(t) = a(0) + t\,P$. Visualisons : ici le profil est $\mathbf 1 = (1, \dots, 1)$, le niveau uniforme, et son amplitude est simplement la hauteur de ce niveau. Dire qu'elle dérive linéairement, c'est dire que l'univers entier monte comme une marée — partout du même cran à chaque pas, sans qu'aucun nœud ne dépasse jamais ses voisins. Aucune tension, donc aucun rappel : le Laplacien, aveugle aux constantes depuis le chapitre I, laisse ce niveau filer en ligne droite, exactement comme une particule libre file sur son erre. Nous avons déjà rencontré cette dérive : c'est la croissance du total $S(t)$ du chapitre IV, et la pente conservée $P$ est notre première loi de conservation ! Elle habitait donc le mode zéro depuis le début : la « quantité de mouvement du total » est l'amplitude de la note silencieuse de l'univers. (Et ce n'est pas la dernière fois que le mode zéro nous fera ce genre de confidence.)

## 5. L'instrument le plus simple du monde

Tout ceci mérite d'être *vu*. Prenons le plus petit instrument non trivial : trois nœuds en ligne, $1 - 2 - 3$. Son Laplacien a pour catalogue complet ($N = 3$ notes, comme promis) :
$$
\varphi_0 = (1,1,1),\ \lambda = 0 \qquad \varphi_1 = (1,0,-1),\ \lambda = 1 \qquad \varphi_2 = (1,-2,1),\ \lambda = 3.
$$
(Vérification en une ligne pour $\varphi_1$ : le nœud central voit $2\cdot 0 - 1 - (-1) = 0$ ✓, le nœud $1$ voit $1 - 0 = 1$ ✓, le nœud $3$ voit $-1 - 0 = -1$ ✓ : $L\varphi_1 = 1\cdot\varphi_1$.) Les trois formes ont un sens limpide : le fond uniforme ; la *balançoire* (les extrémités en opposition, le centre immobile) ; le *pincement* (le centre contre les bords). Ce sont les trois seules façons d'exister sur ce graphe sans se défigurer.

Faisons-les sonner, avec $c = 1$, lâchées au repos. La balançoire obéit à $a(t+1) = a(t) - a(t-1)$, dont on vérifie à la main la merveille : $1, 1, 0, -1, -1, 0, 1, 1, \dots$ — **période 6, exactement**. Le pincement obéit à $a(t+1) = -a(t) - a(t-1)$ : $1, 1, -2, 1, 1, -2, \dots$ — **période 3, exactement**. (Simulation faite : les profils restent $(1,0,-1)$ et $(1,-2,1)$ au facteur près, à la précision machine, pour toujours.) Deux notes parfaitement périodiques, la plus rugueuse vibrant deux fois plus vite que la plus lisse, conformément à $\omega(\lambda)$. Et n'importe quel état initial de cet univers à trois nœuds — *n'importe lequel* — est un accord de ces trois notes, chacune évoluant dans son coin comme si les autres n'existaient pas.

C'est le gain conceptuel du chapitre, et il est immense : l'évolution « inextricable » du §1 était une illusion d'écriture. Dans la bonne base, notre univers n'est pas un enchevêtrement de $N$ nœuds qui se tirent dessus — c'est une collection de $N$ **oscillateurs indépendants**, qui ne se parlent jamais. Toute la complexité apparente venait de ce que nous regardions l'instrument nœud par nœud au lieu de l'écouter note par note. (L'énergie du chapitre IV, au passage, respecte la partition : elle se décompose en une somme d'énergies par mode, chacune conservée séparément — chaque note garde son intensité pour l'éternité.)

> **Le déclic.** Les vecteurs propres ne sont pas une technique de calcul : ce sont les seuls objets que la dynamique accepte de transporter sans les défigurer. Diagonaliser le Laplacien, c'est accorder l'instrument — trouver les notes dont toute évolution, même la plus chaotique, n'est qu'un accord. La physique d'un graphe, c'est le spectre de son Laplacien.

## 6. Où nous en sommes — et le paradoxe qui nous attend

Nous avons demandé quelles formes survivent, et la réponse est totale : les vecteurs propres du Laplacien, et eux seuls ; ils forment un catalogue complet de $N$ formes orthogonales ; chacune vibre sur place à la fréquence $\omega(\lambda)$ fixée par sa rugosité ; le seuil de stabilité du chapitre IV est la condition que toutes les notes soient jouables ; et toute évolution est un accord de ces oscillations indépendantes.

Mais le lecteur vigilant a dû sentir un malaise grandir au fil du chapitre. Reprenons-le à froid. Chaque objet élémentaire **vibre sur place**. Aucun ne voyage. Or nous avons *vu*, au chapitre III, une bosse traverser la chaîne, cran par cran, imperturbable. Si toute évolution n'est qu'une somme de vibrations immobiles… **d'où vient le mouvement ?**

Il n'y a qu'une issue possible : le voyage doit être une *conspiration*. Des modes immobiles, vibrant chacun à sa fréquence, dont les phases s'accordent pour que leurs crêtes se renforcent *ici* à l'instant $t$, et *un cran plus loin* à l'instant $t+1$ — une illusion d'optique parfaitement réelle, entretenue par l'interférence. Mais alors tout repose sur l'accord des fréquences : il suffirait que les notes se décalent un peu — que $\omega$ ne croisse pas *exactement* comme il faut avec $\lambda$ — pour que la conspiration se défasse en route, et que le voyageur s'effiloche. Nous tenons du même coup, avant même de faire le calcul, l'intuition de ce qui distinguait le graphe « miraculeux » du chapitre III : sur lui, et pour $c = 1$ précisément, l'accord devait être parfait. Reste à comprendre quand il l'est, quand il ne l'est pas — et à quelle vitesse, au juste, voyage une conspiration.

> **Chapitre suivant — VI. Pourquoi les objets s'étalent-ils ?**
> *Où l'on apprend à lire la vitesse d'un objet sur une seule courbe.*

---

# Chapitre VI — Pourquoi les objets s'étalent-ils ?

> **Question.** Si aucun objet élémentaire ne voyage, d'où vient le mouvement — et pourquoi finit-il presque toujours par s'effilocher ?
>
> *Nous savons que le voyage est une conspiration de vibrations immobiles. Nous allons démasquer les conjurés, mesurer la vitesse de leur complot, et comprendre pourquoi il se défait.*

## 1. Le bon terrain d'enquête

Pour étudier le mouvement, il nous faut un univers où le mouvement a ses chances : un graphe où *tous les lieux se valent*, sans bords où buter. Le plus simple est l'**anneau** : $N$ nœuds en cercle, $0, 1, \dots, N-1$, chacun relié à ses deux voisins, le dernier rebouclé sur le premier. C'est la chaîne du chapitre III, débarrassée de ses extrémités — l'incarnation parfaite de notre axiome d'homogénéité : décaler tout le monde d'un cran est une opération que le graphe ne remarque même pas.

Dressons le catalogue des formes élémentaires de cet instrument. Quelles sont les configurations dont la rugosité est *partout la même* — condition nécessaire pour être vecteur propre, puisque $L\varphi = \lambda\varphi$ exige que chaque nœud dévie de ses voisins dans la même proportion ? Sur un anneau, la réponse s'impose d'elle-même : les **ondulations régulières**,
$$
\varphi_n = \cos(kn) \qquad\text{et}\qquad \psi_n = \sin(kn),
$$
où le **nombre d'onde** $k$ mesure combien l'ondulation tourne par arête. (Pour se refermer proprement sur l'anneau, $k$ doit être un multiple de $2\pi/N$ — l'instrument a bien $N$ notes, comme l'exige le théorème spectral.) Vérifions pour $\cos$ : au nœud $n$,
$$
(L\varphi)_n = 2\cos(kn) - \cos(k(n{-}1)) - \cos(k(n{+}1)) = 2\bigl(1 - \cos k\bigr)\cos(kn),
$$
par la formule d'addition. C'est bien $L\varphi = \lambda\varphi$ avec
$$
\lambda(k) = 2 - 2\cos k = 4\sin^2\!\frac{k}{2},
$$
et le même calcul vaut mot pour mot pour $\sin$. D'où une remarque lourde de conséquences : **les notes de l'anneau viennent par paires**. Pour chaque $k$, le cosinus et le sinus — la même ondulation, décalée d'un quart de tour — portent *exactement la même valeur propre*, donc vibrent *exactement à la même fréquence* $\omega(k)$, celle du chapitre V : $\sin^2(\omega/2) = c^2\lambda/4 = c^2\sin^2(k/2)$.

Deux formes immobiles, parfaitement jumelles, qui chantent la même note. Voilà nos conjurés.

## 2. La conspiration, démasquée

Faisons-les chanter ensemble, mais pas *en phase* : décalons leurs horloges d'un quart de période. La superposition (licite : la dynamique est linéaire) s'écrit
$$
u_n(t) \;=\; \cos(\omega t)\cos(kn) \;+\; \sin(\omega t)\sin(kn) \;=\; \cos\bigl(kn - \omega t\bigr).
$$
Lisons le membre de droite : c'est l'ondulation $\cos(kn)$… dont le motif entier **glisse** de $\omega/k$ nœuds par pas de temps. Une **onde progressive**. Aucun des deux conjurés ne bouge — le cosinus respire sur place, le sinus respire sur place — mais leur duo déphasé compose un motif qui, lui, voyage. Au moment où le mode cosinus passe par son maximum ici, le mode sinus passe par le sien un quart de longueur d'onde plus loin ; un quart de période plus tard, les rôles ont tourné, et la crête totale s'est déplacée d'autant. Le mouvement est un *relais* : chaque forme immobile tend le témoin à sa jumelle décalée.

Le paradoxe du chapitre V est résolu, et la résolution est plus fine qu'espéré : le voyage n'exige pas une conspiration de tout le catalogue, mais seulement la complicité de **deux** modes — à condition qu'ils soient *dégénérés* (même fréquence). Et cette dégénérescence n'est pas un hasard : elle est le cadeau de la symétrie de l'anneau. Sur un graphe sans symétrie, les fréquences sont toutes différentes, aucun relais parfait n'est possible — première indication que **le mouvement est un privilège des univers réguliers**. Nous y reviendrons.

### Fabriquons un objet, et regardons-le partir

Une onde infinie qui glisse, c'est bien ; mais le lecteur est en droit d'exiger davantage : *peut-on fabriquer une bosse — une bosse de son choix — et la voir se déplacer ?* Répondons d'abord à la question de principe, puis faisons-le sur un exemple complet.

**Quelle liberté a-t-on sur la forme ?** Totale. C'est le théorème spectral du chapitre V qui la garantit : les ondulations $\cos(kn)$, $\sin(kn)$ forment une *base* — **tout** profil sur l'anneau, bosse pointue, plateau, deux bosses disjointes, vos initiales en morse, s'écrit d'une seule manière comme accord $u_n = \sum_k A_k \cos(kn - \phi_k)$. Un « objet » n'est donc soumis à aucun cahier des charges de forme, et la contiguïté n'est pas requise : deux bosses séparées sont un objet parfaitement licite (ou deux objets — la linéarité rend la distinction purement verbale : chacune voyage comme si l'autre n'existait pas, et si elles se croisent, elles se *traversent* et ressortent intactes). Ce que l'on ne choisit **pas**, en revanche, c'est le destin : une fois la forme posée, la relation de dispersion attribue d'office sa fréquence $\omega(k)$ à chaque composante. La forme est libre ; son avenir ne l'est pas.

**La recette du mouvement.** Pour animer le profil, on lance chaque composante comme onde progressive, toutes dans le même sens :
$$
u_n(t) \;=\; \sum_k A_k \cos\bigl(kn - \omega(k)\,t - \phi_k\bigr).
$$
À $t = 0$, c'est exactement votre profil ; ensuite, chaque onde glisse à sa vitesse $\omega(k)/k$, et leur somme *est* l'objet en voyage.

**L'exemple complet, vérifiable à la main.** Prenons le plus petit anneau intéressant : $N = 4$ nœuds, $c = 1$, et le profil $u(0) = (2, 1, 0, 1)$ — une bosse posée sur le nœud $0$. Sa décomposition tient en deux termes : la moyenne vaut $1$, et le reste $(1, 0, -1, 0)$ est *exactement* l'ondulation $\cos(kn)$ pour $k = \tfrac{\pi}{2}$. Donc
$$
u_n(0) = 1 + \cos\!\Bigl(\frac{\pi}{2}n\Bigr) : \qquad \text{un accord de deux notes seulement.}
$$
Animons : le fond ($k=0$) ne bouge pas, et l'ondulation devient progressive avec sa fréquence attitrée, $\sin(\omega/2) = \sin(\pi/4)$ d'où $\omega = \tfrac{\pi}{2}$ :
$$
u_n(t) = 1 + \cos\!\Bigl(\frac{\pi}{2}(n - t)\Bigr).
$$
Lisons la prédiction : $(2,1,0,1) \to (1,2,1,0) \to (0,1,2,1) \to \dots$ — la bosse fait le tour de l'anneau, un nœud par pas. Et maintenant, contre-vérifions avec la dynamique elle-même, sans aucune onde : la règle du chapitre III, $u_n(t{+}1) = u_{n-1}(t) + u_{n+1}(t) - u_n(t{-}1)$, avec le passé décalé $u(-1) = (1, 0, 1, 2)$. Nœud par nœud : $u_0(1) = 1 + 1 - 1 = 1$ ; $u_1(1) = 2 + 0 - 0 = 2$ ; $u_2(1) = 1 + 1 - 1 = 1$ ; $u_3(1) = 0 + 2 - 2 = 0$. Résultat : $(1, 2, 1, 0)$. **Les deux calculs coïncident exactement.** Ce sont deux descriptions du même événement : côté nœuds, un relais de voisin à voisin orchestré par la mémoire ; côté ondes, deux notes dont l'une glisse. La bosse n'est pas *faite* d'ondes comme un mur est fait de briques — elle *est* un accord, et son mouvement *est* le glissement coordonné de ses composantes.

(Au passage, ce petit exemple montre aussi pourquoi la rigidité est ici parfaite : avec une seule ondulation mobile, il n'y a personne avec qui être en désaccord de vitesse. Le premier vrai test de la cohésion viendra avec des accords plus riches — c'est tout l'objet de la suite du chapitre.)

## 3. La carte d'identité de l'univers

Récapitulons ce que le calcul nous a livré sans qu'on le lui demande : à chaque nombre d'onde $k$, une fréquence
$$
\boxed{\;\sin\frac{\omega}{2} \;=\; c\,\sin\frac{k}{2}\;}
$$
et une onde progressive $\cos(kn - \omega t)$ filant à la vitesse $v_\varphi = \omega/k$. Cette relation entre $k$ et $\omega$ — quelle note pour quelle ondulation — s'appelle la **relation de dispersion**, et le nom est un programme. Car regardons-la de près : la vitesse $\omega/k$ **dépend de $k$**. Les grandes ondulations lisses ($k$ petit, où $\omega \approx ck$) filent à la vitesse $c$ ; les ondulations serrées traînent derrière ($\omega$ croît moins vite que $ck$). Notre univers est comme un milieu où chaque couleur voyage à sa propre vitesse — un prisme.

Le lecteur voit peut-être déjà la catastrophe se profiler. Mais avant de la déclencher, réglons une vieille affaire.

**Le miracle du chapitre III, enfin élucidé.** Posons $c = 1$ dans la relation : $\sin(\omega/2) = \sin(k/2)$, donc $\omega = k$ **exactement, pour tout $k$**. Toutes les ondes, lisses ou serrées, voyagent à la même vitesse $\omega/k = 1$ : une arête par pas. Or n'importe quel profil — notre bosse $(1,2,1)$ comme un autre — est un accord d'ondes de différents $k$ ; si toutes ses composantes avancent du même pas, l'accord se translate *en bloc*, éternellement intact. Voilà le miracle : à $c = 1$ sur la chaîne, la relation de dispersion est une droite parfaite, et un monde à dispersion droite ne disperse rien. Notons la coïncidence qui n'en est pas une : $c = 1$ est aussi, sur ce graphe ($\lambda_{\max} = 4$), la valeur *limite* de stabilité du chapitre IV, et la vitesse du cône causal — une arête par pas. Le monde rigide du chapitre III est un monde qui roule exactement à la vitesse maximale que sa causalité autorise, sans une once de marge. Un cran plus vite, il explose ; un cran moins vite… voyons.

## 4. La vitesse d'un objet : le pas de deux des battements

Un objet localisé n'est pas une onde infinie : c'est un **paquet** — un accord d'ondes dont les $k$ se concentrent autour d'une valeur $k_0$. Pour comprendre à quelle vitesse voyage un paquet, le cas d'école suffit : superposons *deux* ondes de nombres d'onde voisins, $k_0 \pm \tfrac{\delta}{2}$, de fréquences $\omega_0 \pm \tfrac{\varepsilon}{2}$. La formule somme-produit fait le travail :
$$
\cos\bigl((k_0{+}\tfrac{\delta}{2})n - (\omega_0{+}\tfrac{\varepsilon}{2})t\bigr) + \cos\bigl((k_0{-}\tfrac{\delta}{2})n - (\omega_0{-}\tfrac{\varepsilon}{2})t\bigr) \;=\; 2\,\underbrace{\cos\!\Bigl(\frac{\delta n - \varepsilon t}{2}\Bigr)}_{\text{enveloppe lente}}\;\underbrace{\cos\bigl(k_0 n - \omega_0 t\bigr)}_{\text{porteuse rapide}} .
$$
Deux mouvements cohabitent, et ils sont *indépendants*. La porteuse — les vaguelettes fines — file à la vitesse de phase $\omega_0/k_0$. Mais l'objet, le paquet visible, c'est l'**enveloppe** — les battements lents — et elle glisse à la vitesse $\varepsilon/\delta$, le rapport des *écarts*. À la limite des $k$ proches, ce rapport devient une dérivée : la vitesse de l'objet est la **pente de la relation de dispersion** au point $k_0$,
$$
\boxed{\;v_g \;=\; \frac{d\omega}{dk}\Big|_{k_0} \;=\; c\,\frac{\cos(k_0/2)}{\cos(\omega_0/2)}\;}
$$
(la formule close s'obtient en dérivant $\sin(\omega/2) = c\sin(k/2)$). On l'appelle la **vitesse de groupe**, et c'est elle, la vraie vitesse des choses. L'expérience confirme avec une précision insolente : un paquet préparé autour de $k_0 = 1$ avec $c = 0{,}7$ doit filer, selon la formule, à $v_g = 0{,}6521$ ; la simulation mesure $0{,}6521$.

La courbe $\omega(k)$ mérite alors son titre de **carte d'identité cinématique de l'univers** : une seule courbe, lisible d'un regard, contient *toutes* les vitesses possibles. Sa pente à l'origine est la vitesse des grandes ondes ($v_g \to c$). Sa pente ne dépasse jamais $1$ — petit calcul : $v_g^2 = c^2(1-s)/(1 - c^2 s)$ avec $s = \sin^2(k/2)$, majoré par $1$ dès que $c \le 1$ — **aucun objet ne peut battre le cône causal**, une arête par pas, et seul le monde limite $c=1$ le sature. Et au bord de la carte, une surprise : en $k = \pi$ — l'ondulation *zigzag*, $+,-,+,-$, la plus hérissée de toutes — la courbe devient horizontale : $v_g = 0$. La simulation le confirme : un paquet de zigzag, lâché sur l'anneau avec toute sa phase pour l'élan, reste cloué sur place, à vibrer furieusement sans avancer d'un pouce. Notre univers possède des ondes qui courent et des ondes qui piétinent, et la courbe dit lesquelles.

## 5. Et maintenant, la catastrophe annoncée

Revenons au prisme. Dès que $c < 1$, la courbe $\omega(k)$ est *bombée* : sa pente $v_g$ décroît avec $k$. Or un paquet, pour être localisé, doit mélanger un intervalle de $k$ (nous verrons au chapitre IX que c'est un théorème, pas une maladresse). Ses composantes lentes et rapides se séparent donc en route : l'avant du paquet, porté par les petits $k$, prend de l'avance ; l'arrière traîne. L'objet **s'étale** — non parce qu'une force le dilate, non parce qu'il perd de l'énergie ($E$ est scrupuleusement conservée pendant tout le naufrage), mais parce qu'il est un accord dont les notes ne marchent pas au même pas. En chiffres : notre paquet étroit lancé à $c = 0{,}7$ voit sa largeur passer de $6{,}6$ nœuds à $110$ en deux cents pas. Au bout d'un temps suffisant, il est méconnaissable — étiré en un long dégradé où les grandes ondes mènent le train. C'était le destin que le chapitre III avait promis d'expliquer : la déformation « lente » du transport à $c \ne 1$ n'était rien d'autre que la dispersion à l'œuvre.

Le taux d'étalement, lui aussi, se lit sur la carte : c'est la *courbure* $d^2\omega/dk^2$ au point $k_0$ qui commande la vitesse à laquelle les pentes locales s'éventaillent. Un paquet vit d'autant plus longtemps qu'il campe sur une portion droite de la courbe — et le monde $c = 1$, dont la carte est droite *partout*, est le seul où les objets vivent éternellement.

> **Le déclic.** Un objet composite n'a pas *une* vitesse : il en a une par composante, et la relation de dispersion est le barème complet. Tout le destin cinématique d'un univers — qui court, qui piétine, qui survit, qui s'effiloche — tient dans la forme d'une unique courbe $\omega(k)$. Droite : les objets sont immortels. Bombée : tout finit par s'étaler. La dispersion n'est pas un accident, c'est la règle ; la rigidité du chapitre III était l'exception — un univers réglé au millimètre sur sa propre limite causale.

## 6. Où nous en sommes

Nous avons résolu le paradoxe du chapitre V : le mouvement est un relais entre modes jumeaux déphasés, rendu possible par la dégénérescence qu'offre la symétrie de l'anneau. Chaque duo $\pm$ compose une onde progressive, la relation de dispersion $\sin(\omega/2) = c\sin(k/2)$ attribue sa fréquence à chaque ondulation, la vitesse réelle des objets est la pente $v_g = d\omega/dk$, bornée par le cône causal, et l'étalement universel des paquets n'est que la conséquence d'une courbe bombée. Le miracle du chapitre III est élucidé : $c = 1$ redresse la courbe et sature la causalité.

Mais en résolvant une énigme, nous en avons armé une plus profonde. Tout ce chapitre repose sur un personnage entré par la petite porte : le nombre $k$. C'est lui qui étiquette les ondes, lui qui fixe la vitesse, lui dont dépend tout le destin d'un paquet — et à bien y regarder, c'est lui qui joue le rôle que la mécanique réserve à la *quantité de mouvement*. Or qu'est-ce que $k$ ? Un compteur de tours par arête, défini grâce à la régularité providentielle de l'anneau — presque des coordonnées de contrebande. Deux questions se posent alors, et la grille de Noether du chapitre IV nous souffle qu'elles n'en font qu'une. Ce $k$ est-il *conservé* — un objet libre garde-t-il son nombre d'onde comme il garderait son élan ? Et peut-on le définir sans anneau, sur un graphe quelconque, à partir de la seule symétrie qui l'a fait naître : l'indifférence au *lieu* ?

> **Chapitre suivant — VII. Qu'est-ce qu'une direction ?**
> *Où la quantité de mouvement naît d'un décalage.*

---

# Chapitre VII — Qu'est-ce qu'une direction ?

> **Question.** Un objet libre conserve-t-il quelque chose qui mémorise *où il va* — et peut-on définir cette chose sans jamais parler de coordonnées ?

Ce chapitre est plus algébrique que les précédents, et c'est voulu : nous allons voir le théorème de Noether *fonctionner*, pièce par pièce. Le plan, pour ne jamais se perdre :

1. Donner un sens mathématique précis à « l'univers est le même partout » : un opérateur $T$, et une équation, $TL = LT$.
2. En tirer mécaniquement une quantité conservée $P$ — la démonstration tient en cinq lignes et n'utilise que deux ingrédients.
3. Vérifier sur des exemples calculés à la main que $P$ mesure bien *le sens du mouvement*.
4. Comprendre ce que $P$ vaut sur les ondes, et retrouver $k$.
5. En déduire une réponse à la question du titre — et voir ce qu'elle prédit pour les graphes *sans* symétrie.

## 1. La symétrie, écrite comme une matrice

Plaçons-nous sur l'anneau à $N$ nœuds. « Tous les lieux se valent » signifie : si je décale toute la configuration d'un cran, les lois ne s'en aperçoivent pas. Donnons un nom à ce décalage.

> **Définition (opérateur de translation).** $T$ est l'opérateur qui pousse tout le champ d'un cran :
> $$(Tu)_n = u_{n-1} \qquad (\text{indices modulo } N).$$

$T$ est une matrice $N \times N$ parfaitement concrète : des $1$ juste sous la diagonale, un $1$ dans le coin pour reboucler. Trois propriétés, chacune vérifiable en une ligne :

**(i) $T$ est inversible**, d'inverse $T^{-1} = T^\top$ (décaler dans l'autre sens) : $(T^\top u)_n = u_{n+1}$. Décaler ne perd aucune information.

**(ii) $T$ préserve les longueurs** : $\|Tu\|^2 = \sum_n u_{n-1}^2 = \|u\|^2$ (on somme les mêmes nombres dans un autre ordre).

**(iii) $T$ commute avec $L$** :
$$
\boxed{\;TL = LT.\;}
$$
*Preuve.* Calculons les deux membres sur un champ $u$, au nœud $n$ :
$$
(TLu)_n = (Lu)_{n-1} = 2u_{n-1} - u_{n-2} - u_n, \qquad
(LTu)_n = 2(Tu)_n - (Tu)_{n-1} - (Tu)_{n+1} = 2u_{n-1} - u_{n-2} - u_n. \;\blacksquare
$$

Ne passons pas trop vite sur (iii) : c'est **la** traduction mathématique de l'homogénéité. Elle dit : *mesurer la rugosité puis décaler, ou décaler puis mesurer la rugosité, c'est pareil* — le Laplacien ne sait pas où il est. Sur un graphe quelconque, cette équation serait fausse : elle est vraie ici parce que l'anneau se superpose exactement à lui-même après décalage. Conséquence immédiate, qui justifie tout :

> **Proposition.** Si $u(t)$ est une solution de la dynamique, alors $Tu(t)$ est une solution.
>
> *Preuve.* Appliquons $T$ à la règle $u(t{+}1) = 2u(t) - u(t{-}1) - c^2Lu(t)$ :
> $$Tu(t{+}1) = 2\,Tu(t) - Tu(t{-}1) - c^2\,TLu(t) = 2\,Tu(t) - Tu(t{-}1) - c^2\,L\,\bigl(Tu(t)\bigr),$$
> où l'on a utilisé $TL = LT$ à la dernière étape. C'est exactement la règle, appliquée au champ décalé. $\blacksquare$

L'histoire d'un objet, jouée un cran plus loin, est une histoire tout aussi légale. Voilà notre symétrie. Noether promet un trésor : allons le chercher.

## 2. La quantité conservée : cinq lignes

Comment fabriquer une quantité conservée à partir de $T$ ? Guidons-nous sur le seul succès que nous ayons : l'énergie du chapitre IV, $E = \frac12\|u(t)-u(t{-}1)\|^2 + \frac{c^2}{2}u(t)^\top L\, u(t{-}1)$. Sa pièce maîtresse était une forme *enjambant les deux photographies*, $u(t)^\top M\, u(t{-}1)$, avec $M = L$. Essayons la même architecture, en remplaçant $L$ par un opérateur construit sur $T$. Lequel ? Il nous faut un objet qui *distingue les deux sens* — qui change de signe quand on retourne l'anneau. Le candidat s'impose : $T - T^\top$ (décaler à droite *moins* décaler à gauche).

> **Définition (quantité de mouvement).**
> $$\boxed{\;P(t) \;=\; u(t)^\top \bigl(T - T^\top\bigr)\, u(t-1) \;=\; \sum_n u_n(t)\,\bigl(u_{n-1}(t{-}1) - u_{n+1}(t{-}1)\bigr).\;}$$

> **Théorème.** $P(t+1) = P(t)$ pour toute solution. *Exactement.*

*Preuve.* Notons $A = T - T^\top$. Deux ingrédients, et seulement deux :
- **(S)** $L$ est symétrique et $A$ est antisymétrique ($A^\top = -A$) ;
- **(C)** $L$ et $A$ commutent ($LA = AL$, conséquence directe de $TL = LT$).

Ligne 1. $P(t{+}1) - P(t) = u(t{+}1)^\top A\, u(t) - u(t)^\top A\, u(t{-}1)$.

Ligne 2. Remplaçons $u(t{+}1)$ par la règle : $u(t{+}1)^\top A\,u(t) = u(t)^\top(2 - c^2L)A\,u(t) \;-\; u(t{-}1)^\top A\, u(t)$.

Ligne 3. Le premier morceau est nul. En effet, posons $M = (2 - c^2L)A$ : alors $M^\top = A^\top(2 - c^2L) = -A(2-c^2L) = -(2-c^2L)A = -M$, en utilisant **(S)** puis **(C)**. $M$ est antisymétrique, et pour toute matrice antisymétrique, $u^\top M u = 0$ (car $u^\top M u = (u^\top M u)^\top = -u^\top M u$).

Ligne 4. Le second morceau se retourne par antisymétrie : $-\,u(t{-}1)^\top A\, u(t) = +\,u(t)^\top A\, u(t{-}1)$.

Ligne 5. Bilan : $P(t{+}1) - P(t) = u(t)^\top A\,u(t{-}1) - u(t)^\top A\,u(t{-}1) = 0$. $\blacksquare$

Relisons la preuve pour voir *où la symétrie a travaillé* : uniquement à la ligne 3, dans l'étape **(C)**. Si le graphe n'était pas invariant par décalage, $LA \ne AL$, $M$ ne serait pas antisymétrique, et la conservation tomberait. C'est le théorème de Noether réduit à son squelette algébrique :

> **une symétrie de la loi** ($TL = LT$) **+ une structure de la loi** ($L$ symétrique, héritée du chapitre I) **⇒ une conservation**.

Rien d'autre. Pas de coordonnées, pas de vecteurs, pas de limite continue. (Et l'expérience confirme : champ initial *aléatoire* sur un anneau, $300$ pas, $P$ constante à la douzième décimale — tout comme $E$.)

## 3. Que mesure $P$ ? Trois calculs à la main

Une formule conservée ne vaut que si l'on comprend ce qu'elle *dit*. Reprenons l'objet du chapitre VI, sur l'anneau à $4$ nœuds : la bosse $u(0) = (2,1,0,1)$, et calculons $P = \sum_n u_n(0)\bigl(u_{n-1}(-1) - u_{n+1}(-1)\bigr)$ dans trois situations.

**Bosse lancée vers la droite** ($u(-1) = (1,0,1,2)$, la bosse était un cran à gauche) :
$$
P = \underbrace{2\,(u_3 - u_1)}_{n=0} + \underbrace{1\,(u_0 - u_2)}_{n=1} + \underbrace{0\,(\cdots)}_{n=2} + \underbrace{1\,(u_2 - u_0)}_{n=3}
= 2(2-0) + (1-1) + 0 + (1-1) = \mathbf{+4}.
$$

**Bosse lancée vers la gauche** ($u(-1) = (1,2,1,0)$) : le même calcul donne $2(0-2) + 0 + 0 + 0 = \mathbf{-4}$.

**Bosse au repos** ($u(-1) = u(0)$) : $2(1-1) + 1(2-0) + 0 + 1(0-2) = \mathbf{0}$.

Le verdict est net : $P$ est **positive vers la droite, négative vers la gauche, nulle au repos** — et sa valeur est verrouillée pour toute l'éternité du mouvement. C'est un élan. Notons aussi ce que ces petits calculs révèlent de la structure de la formule : le terme $u_{n-1}(t{-}1) - u_{n+1}(t{-}1)$ compare *hier à gauche* et *hier à droite* — il détecte de quel côté l'objet arrive ; et il est pondéré par $u_n(t)$ — là où l'objet se trouve. $P$ est un produit « présence $\times$ provenance », sommé sur l'univers. (Le lecteur qui connaît la mécanique des milieux continus reconnaîtra son vieil ami $\int \dot u\, \partial_x u\, dx$ : notre $A = T - T^\top$ est, au facteur $-2$ près, la dérivée spatiale centrée, et l'enjambement des deux instants tient lieu de $\dot u$.)

## 4. $P$ sur les ondes : le retour de $k$

Évaluons maintenant $P$ sur une onde progressive pure, $u_n(t) = \cos(kn - \omega t)$, notre objet élémentaire du chapitre VI. Le calcul (identités produit-somme, les termes oscillants s'annulant sur l'anneau) donne une formule fermée :
$$
\boxed{\;P_{\text{onde}} = N \sin(k)\,\sin(\omega).\;}
$$
(Vérifiée numériquement à $10^{-6}$ près.) Lisons-la, car chaque facteur parle. Elle est **impaire en $k$** : l'onde $-k$, qui court dans l'autre sens, porte l'élan opposé — et une onde stationnaire, superposition de $+k$ et $-k$, porte un élan exactement nul, conformément au « bosse au repos » du §3. Elle est nulle pour $k = 0$ (le fond uniforme ne va nulle part) et — plus subtil — pour $k = \pi$ : le zigzag, dont le chapitre VI a montré qu'il *piétine* ($v_g = 0$), a beau vibrer de toutes ses forces, son élan est nul. $P$ ne se laisse pas impressionner par l'agitation : il ne compte que le *transport*.

Aux grandes longueurs d'onde ($k$ petit, $\omega \approx ck$), la formule devient $P \approx N\,c\,k^2 \cdot \tfrac{1}{c} \cdot \tfrac{\omega}{k}$… tenons-nous en au fait essentiel : à énergie donnée, $P$ *croît avec $k$*. Le nombre d'onde $k$, entré au chapitre VI comme un simple compteur de tours par arête, se révèle être la **densité d'élan par unité d'énergie** de chaque composante. C'est pourquoi les physiciens l'appellent la **quasi-impulsion** : sur un réseau, $k$ joue le rôle que l'impulsion $p$ joue dans le continu. (Le préfixe *quasi* rappelle une particularité de bon aloi : $k$ vit sur un cercle — $k$ et $k + 2\pi$ décrivent la même ondulation, puisque seuls comptent les nœuds. L'élan d'un monde discret est une grandeur *périodique*. Retenons cette bizarrerie : elle aura des conséquences.)

## 5. Alors, qu'est-ce qu'une direction ?

Nous pouvons répondre à la question du titre, et la réponse renverse l'intuition géométrique.

Dans l'espace ordinaire, on croit l'ordre suivant : *d'abord* il y a des directions (des vecteurs), *ensuite* les objets en mouvement en choisissent une, *enfin* la conservation de l'élan est un théorème. Notre reconstruction inverse tout. Au départ, il n'y a **aucune** direction — un graphe n'a pas de vecteurs. Il y a en revanche des **symétries** : des transformations $T$ qui laissent le graphe invariant, et l'algèbre $TL = LT$ fabrique pour chacune une quantité conservée $P$. Une « direction », c'est le *signe et la grandeur de cet élan conservé* : aller à droite, c'est avoir $P > 0$. Le mouvement rectiligne uniforme du chapitre III reçoit ici sa vraie explication : l'objet ne « suit » pas une droite (il n'y en a pas) — il conserve son $P$, et conserver son $P$, *c'est* aller tout droit.

> **Le déclic.** Une direction n'est pas une propriété de l'espace : c'est une propriété du *groupe de symétrie* de l'univers. Il y a exactement autant de directions que de translations que le graphe supporte. L'anneau en supporte une (et son inverse) : son monde est unidimensionnel. Une grille en supporte deux indépendantes : monde bidimensionnel. La *dimension* elle-même, que nous n'avions jamais définie, vient de recevoir sa définition : c'est le nombre de translations indépendantes — le nombre de conservations d'élan que l'univers offre.

Et la contraposée est physique, vérifiable, et un peu vertigineuse : sur un graphe **sans symétrie de translation** — un réseau désordonné, un arbre irrégulier — il n'existe ni $T$, ni $P$, ni directions. Aucun objet ne peut y « aller tout droit », non par maladresse, mais parce que *tout droit n'y veut rien dire*. Le chapitre VI l'avait pressenti (pas de dégénérescence, pas de relais) ; nous savons maintenant le dire en une phrase : **le mouvement inertiel est la monnaie d'une symétrie, et les univers irréguliers sont insolvables**. C'est un phénomène bien réel de la physique des matériaux : dans un milieu suffisamment désordonné, les ondes cessent de se propager et restent piégées — le lecteur curieux cherchera *localisation d'Anderson*.

## 6. Où nous en sommes

Le butin du chapitre, en tableau — car il complète une structure entamée au chapitre IV :

| Symétrie de la loi | Équation | Quantité conservée |
|---|---|---|
| Indifférence à la date | mêmes coefficients à tout $t$ | énergie $E$ (chap. IV) |
| Indifférence au niveau du champ | $L\mathbf 1 = 0$ | dérive du total $S(t) - S(t{-}1)$ (chap. IV) |
| Indifférence au lieu | $TL = LT$ | quantité de mouvement $P$ (ce chapitre) |

Trois indifférences, trois trésors : la grille de Noether, annoncée en aparté, est devenue une machine qui tourne. Et nous tenons désormais les deux monnaies fondamentales de toute mécanique — $E$ et $P$ — sans avoir jamais importé un seul concept géométrique.

Mais ce tableau dessine en creux la prochaine étape. Toute notre physique est celle d'un monde *parfaitement homogène* — et un monde parfaitement homogène est un monde où il ne se passe rien : les objets y vont tout droit, éternellement, et c'est tout. Le monde intéressant commence quand *quelque chose, quelque part, est différent* : un lieu qui attire, un lieu qui repousse. Or nous savons maintenant exactement ce que « casser l'homogénéité » coûtera : $TL \ne LT$, la ligne 3 de notre preuve s'effondre, et $P$ cesse d'être conservée. Loin d'être une catastrophe, ce sera notre définition : le taux de variation de l'élan, $P(t{+}1) - P(t)$, mesurera *ce que le monde inflige à l'objet*. Les physiciens ont un nom pour cette grandeur. Il figure dans la plus célèbre équation de Newton.

> **Chapitre suivant — VIII. Qu'est-ce qu'une force ?**
> *Où l'on casse l'homogénéité, et où $\;F = \Delta P/\Delta t\;$ cesse d'être un axiome pour devenir une définition.*

---

# Chapitre VIII — Qu'est-ce qu'une force ?

> **Question.** Comment un lieu peut-il agir sur un objet — et que devient l'élan quand tous les lieux ne se valent plus ?

Le plan du chapitre :

1. Trouver la *seule* modification de la règle que nos axiomes autorisent : un potentiel $V$.
2. Calculer exactement ce que $V$ fait à l'élan : un théorème, $\Delta P = -\sum_n (V_{n+1} - V_n)\, u_n u_{n+1}$, qui *est* la deuxième loi de Newton.
3. Vérifier que l'énergie, elle, survit — et voir la table de Noether prédire juste.
4. Expérimenter : la chute libre d'un paquet sur une rampe.
5. Découvrir un cadeau inattendu : un potentiel *uniforme* fabrique de la **masse**.

## 1. La seule porte restée ouverte

Notre univers est ennuyeux à la perfection : tout y va tout droit, pour toujours. Pour qu'il se passe quelque chose, il faut qu'un lieu puisse *agir* — attirer, repousser, freiner. Mais nous ne bricolerons pas : demandons, comme toujours, quelle est la modification **la plus pauvre** de la règle compatible avec les axiomes que nous *gardons*.

Reprenons la dérivation du chapitre III. Nous y avions imposé : localité, linéarité, homogénéité (de lieu et de date), champ constant inerte, réversibilité — et la règle était unique. Cassons maintenant *un seul* axiome : l'homogénéité **de lieu** (les coefficients peuvent dépendre du nœud), en gardant tout le reste. La forme générale redevient, au nœud $v$ :
$$
u_v(t{+}1) = \alpha_v\, u_v(t) + \beta_v\, u_v(t{-}1) - \gamma_v\,(Lu(t))_v - \delta_v\,(Lu(t{-}1))_v .
$$
La réversibilité (relire la règle à l'envers doit redonner la même règle, nœud par nœud) impose comme au chapitre III : $\beta_v = -1$ et $\delta_v = 0$, pour chaque $v$. Restent $\alpha_v$ et $\gamma_v$ libres. Le coefficient $\gamma_v$ est une vitesse locale $c_v^2$ — intéressant, mais gardons $c$ uniforme pour isoler la nouveauté. Toute la liberté nouvelle tient alors dans $\alpha_v$, que nous écrivons $\alpha_v = 2 - V_v$ :
$$
\boxed{\;u_v(t{+}1) = 2\,u_v(t) - u_v(t{-}1) - c^2\,(Lu(t))_v - V_v\, u_v(t).\;}
$$
En notation matricielle : $u(t{+}1) = W u(t) - u(t{-}1)$, avec $W = 2 - c^2L - V$ et $V$ **diagonale** ($V_{vv} = V_v$). C'est la seule porte que nos axiomes laissaient ouverte : un nombre par nœud, agissant à l'instant présent (la réversibilité interdit le passé, comme elle l'interdisait à $L$), couplé à la valeur locale du champ.

Que fait physiquement $V_v > 0$ ? Il ajoute au nœud $v$ un **rappel vers zéro** : là où $V$ est grand, le champ est tiré vers le bas plus fort, comme si le nœud était monté sur un ressort plus raide. Le paysage $\{V_v\}$ est un relief de raideurs. Le mot des physiciens : un **potentiel**. Notons tout de suite ce que le champ constant devient : $L\mathbf 1 = 0$ mais $V\mathbf 1 \ne 0$ — un champ plat *n'est plus inerte* là où $V \ne 0$. C'est le prix assumé : un lieu qui agit est, par définition, un lieu qui ne laisse pas tout tranquille.

## 2. Ce que $V$ fait à l'élan : le théorème central

Le chapitre VII a préparé le terrain : la conservation de $P = u(t)^\top A\, u(t{-}1)$ (avec $A = T - T^\top$) reposait sur la ligne 3 de la preuve, elle-même sur la commutation $[L, A] = 0$. Or $V$, sauf s'il est constant, **ne commute pas** avec $A$ : décaler puis peser par $V$, ou peser puis décaler, ce n'est plus pareil. Voyons *exactement* ce qui fuit.

> **Théorème (deuxième loi de Newton).** Pour toute solution de la règle avec potentiel, sur l'anneau,
> $$\boxed{\;P(t{+}1) - P(t) \;=\; -\sum_n \bigl(V_{n+1} - V_n\bigr)\; u_n(t)\, u_{n+1}(t).\;}$$

*Preuve.* Reprenons la machinerie du chapitre VII avec $W = 2 - c^2L - V$ (symétrique) :
$$
P(t{+}1) - P(t) = u(t)^\top W\!A\, u(t) \underbrace{-\, u(t{-}1)^\top A\, u(t) - u(t)^\top A\,u(t{-}1)}_{=\,0 \text{ par antisymétrie de } A}.
$$
Il reste $u^\top W\!A\, u$, qui ne retient que la partie symétrique de $W\!A$, à savoir $\tfrac12(W\!A - AW) = \tfrac12[W, A]$. Or $[2, A] = 0$, $[L, A] = 0$ (chapitre VII), donc $[W, A] = -[V, A]$ : *seul le potentiel contribue*. Le calcul de $-\tfrac12 u^\top[V,A]u$ en coordonnées (deux lignes : chaque arête $\{n, n{+}1\}$ collecte deux termes égaux) donne la formule. $\blacksquare$

Ce théorème est, mot pour mot, $F = \Delta P/\Delta t$ — mais lisons le membre de droite, car il est plus fin que la formule de Newton qu'on apprend :

- $V_{n+1} - V_n$ est la **pente locale du potentiel** — le gradient discret, arête par arête ;
- $u_n u_{n+1}$ est la **présence de l'objet sur l'arête** — grande là où le champ est intense des deux côtés, nulle là où l'objet n'est pas ;
- le signe : l'élan diminue quand l'objet occupe une *montée* de $V$. **L'objet est poussé vers les potentiels faibles** — il dévale le relief.

La force n'est donc pas une flèche attachée à l'objet : c'est une somme, sur tout l'univers, de *pente $\times$ présence*. Un objet n'est freiné que par les pentes qu'il occupe. (C'est le théorème d'**Ehrenfest** en version discrète et exacte : la variation de l'élan moyen égale la moyenne, pondérée par la présence, du gradient du potentiel.) Deux cas limites pour calibrer l'intuition. **$V$ uniforme** : toutes les différences $V_{n+1} - V_n$ sont nulles, $\Delta P = 0$ — un potentiel plat, si haut soit-il, est *invisible pour le mouvement* ; seules les **différences** de potentiel agissent, jamais sa valeur absolue. **$V$ localisé** (une bosse de potentiel quelque part) : l'objet ne sent rien tant qu'il n'y est pas, décélère dans la montée, et — l'énergie étant conservée, voir §3 — soit passe, soit fait demi-tour. Un mur, une barrière, un puits : tout le vocabulaire de la mécanique vient d'apparaître dans une somme.

## 3. Et l'énergie ? La table de Noether à l'épreuve

Le chapitre VII s'était conclu sur une table : *indifférence à la date* $\to$ énergie ; *indifférence au lieu* $\to$ élan. Notre potentiel $V$ est figé dans le temps mais varie dans l'espace : la table **prédit** donc que $P$ meurt (fait, §2) mais que $E$ survit. Vérifions qu'elle a raison. Posons
$$
E_V(t) = \tfrac12\,\|u(t) - u(t{-}1)\|^2 + \tfrac12\, u(t)^\top\bigl(c^2 L + V\bigr)\, u(t{-}1).
$$
La preuve du chapitre IV n'utilisait qu'une seule propriété de l'opérateur enjambant : sa *symétrie*. Or $c^2L + V$ est symétrique ($V$ est diagonale). La démonstration se rejoue mot pour mot, et $E_V$ est **exactement conservée** — simulation à l'appui : champ aléatoire, potentiel aléatoire, $300$ pas, douze décimales immobiles pendant que $P$ dérive conformément au théorème du §2. La grille de Noether n'est plus une grille de lecture : c'est un instrument de *prédiction*, et il vient de réussir son premier test en conditions réelles. (Corollaire physique : un objet qui grimpe une pente perd de l'élan mais pas d'énergie — il convertit du mouvement en tension de ressort, récupérable intégralement à la descente. Le demi-tour du §4 sera élastique.)

## 4. L'expérience : la chute libre

Prenons une longue chaîne, un paquet d'ondes bien formé ($k_0 = 0{,}9$, $c = 0{,}7$), et une **rampe** : $V_n = g\,n$, pente constante $g = 6\times10^{-4}$ — la version graphe d'un champ de pesanteur uniforme. Lançons le paquet *vers le haut* de la rampe et relevons son centre tous les 200 pas :
$$
200 \to 312 \to 414 \to 507 \to 588 \to 658 \to 716 \to 761 \to 793 \to 804 \to \mathbf{808} \to 797 \to 781 \to \dots
$$
Lisons les *accroissements* : $112, 102, 93, 81, 70, 58, 45, 32, 11, 4$, puis négatifs. Une décélération **quasi uniforme** — c'est la cinématique du projectile de Galilée, parabole comprise : le paquet monte en ralentissant régulièrement (force constante $\Rightarrow$ perte d'élan constante, notre théorème au travail), s'arrête un instant vers $n = 808$, puis **retombe**. Aucune trajectoire n'a été programmée, aucun vecteur accélération n'existe nulle part : il n'y a que des nœuds qui tirent sur des voisins, et un relief de raideurs. La pomme de Newton vient de tomber dans un monde qui ne sait pas ce qu'est la hauteur.

## 5. Le cadeau inattendu : $V$ uniforme fabrique de la masse

Revenons au cas « trivial » du §2 : $V_n = V_0$ partout. L'élan est intact, soit — mais la *dynamique*, elle, n'est pas intacte du tout. Refaisons la relation de dispersion du chapitre VI avec le terme en plus : pour $u_n(t) = \cos(kn - \omega t)$, la règle exige maintenant
$$
\cos\omega \;=\; 1 - \frac{V_0}{2} - c^2\bigl(1 - \cos k\bigr),
\qquad\text{soit, aux petits } k, \omega \text{ :}\qquad
\boxed{\;\omega^2 \;\approx\; V_0 + c^2 k^2.\;}
$$
Comparons les deux mondes. Sans potentiel : $\omega \approx c\,k$ — la courbe part de zéro, en droite ; toutes les grandes ondes filent à la vitesse $c$ ; *rien ne peut être lent*. Avec $V_0$ : la courbe part de $\omega(0) = \sqrt{V_0} > 0$ — il y a un **gap**, une fréquence plancher — et la vitesse de groupe devient
$$
v_g = \frac{c^2 k}{\sqrt{V_0 + c^2k^2}} \;\xrightarrow[k \to 0]{}\; 0.
$$
Nos objets peuvent enfin **ralentir jusqu'à l'arrêt**. Un paquet de grand $k$ file presque à $c$ ; un paquet de petit $k$ se traîne ; à la limite, un objet de $k \to 0$ *reste sur place tout en vibrant à la fréquence $\sqrt{V_0}$* — une chose qui a de l'énergie sans avoir de mouvement. L'expérience confirme au millième : le paquet qui filait à $v_g = 0{,}662$ dans le monde sans potentiel ne fait plus que $0{,}513$ avec $V_0 = 0{,}3$, exactement la valeur prédite.

Le lecteur physicien a reconnu la formule au premier regard : $\omega^2 = V_0 + c^2k^2$, c'est $E^2 = m^2c^4 + p^2c^2$ — la relation énergie-impulsion **relativiste**, et notre équation modifiée est l'équation de *Klein-Gordon* discrète. La traduction est vertigineuse de simplicité : **la masse, c'est $\sqrt{V_0}$** — la fréquence à laquelle un objet vibre quand il ne va nulle part. Notre univers primitif ne contenait que des objets « de lumière », condamnés à filer à $c$ ; il suffit d'un rappel uniforme — le même ressort sous chaque nœud, aucun lieu privilégié, aucune direction cassée — pour peupler le monde d'objets *lourds*, capables de repos. La masse n'est pas une quantité de matière : c'est un **loyer en fréquence**, payé partout pareil, qui courbe le bas de la relation de dispersion. (Et ce bas de courbe parabolique, $\omega \approx \sqrt{V_0} + \tfrac{c^2}{2\sqrt{V_0}}k^2$, est très exactement le territoire de l'équation de Schrödinger — nous y reviendrons le moment venu.)

> **Le déclic.** La force n'est pas un ingrédient nouveau : c'est le *déficit de conservation* de l'élan, calculable exactement, égal à la pente du potentiel pondérée par la présence. Newton ($F = \Delta P/\Delta t$), Ehrenfest (moyenne du gradient), Galilée (décélération uniforme sur une rampe) et même la masse relativiste ($\omega^2 = V_0 + c^2k^2$) tiennent dans une seule modification de la règle — la seule que les axiomes toléraient.

## 6. Où nous en sommes

Nous avons cassé l'homogénéité de la façon la plus économe possible, et la moisson dépasse la mise : un potentiel diagonal, unique porte ouverte ; la deuxième loi de Newton comme *théorème* exact, avec sa lecture fine (pente $\times$ présence, seules les différences de $V$ agissent) ; l'énergie qui survit, comme la table de Noether l'avait prédit ; la chute libre reproduite en silicium ; et la masse comme gap de dispersion, cadeau du potentiel uniforme.

Notre mécanique est presque complète : inertie, énergie, élan, force, masse. Mais un mot, dans tout ce chapitre, a été employé avec une désinvolture croissante : « l'objet ». Nos objets sont des *paquets* — des accords d'ondes — et le chapitre VI nous a appris qu'ils s'étalent, que leur localisation est une denrée périssable. Jusqu'où peut-on comprimer un paquet ? Peut-on fabriquer un objet *ponctuel* — toute la présence sur un seul nœud, tout l'élan bien défini ? Le lecteur se doute que non, et le chapitre VII a semé l'indice : un objet localisé mélange beaucoup de $k$, un objet de $k$ pur est étalé partout. Il est temps de transformer ce pressentiment en théorème — et de découvrir que l'impossibilité porte un nom célèbre.

> **Chapitre suivant — IX. Pourquoi les particules ne sont-elles pas des points ?**
> *Où un théorème sur les accords devient un principe d'incertitude.*

---

# Chapitre IX — Pourquoi les particules ne sont-elles pas des points ?

> **Question.** Peut-on fabriquer un objet parfaitement localisé — toute la présence sur un nœud — qui possède en même temps un élan bien défini ?

Le plan :

1. Poser les deux mesures en jeu : la largeur $\Delta n$ d'un objet, la largeur $\Delta k$ de son accord.
2. Examiner les deux cas extrêmes — et découvrir qu'ils s'excluent.
3. Démontrer le compromis : $\Delta n \cdot \Delta k \gtrsim \pi$, avec les outils du chapitre VI.
4. En tirer la loi de mortalité des objets : le temps de vie croît comme le *carré* de la largeur.
5. Nommer le résultat — et dire honnêtement ce qu'il a, et n'a pas, de quantique.

## 1. Les deux fiches d'identité d'un objet

Depuis le chapitre VI, tout objet a deux descriptions équivalentes : côté nœuds (le profil $u_n$, *où* est la présence) et côté ondes (l'accord $\{A_k\}$, *quelles* composantes le fabriquent). À chaque description, sa largeur. Côté nœuds : $\Delta n$, l'étalement de la présence autour de son centre (l'écart-type de l'intensité $u_n^2$, disons). Côté ondes : $\Delta k$, l'étalement des nombres d'onde qui portent un poids significatif dans l'accord.

Or ces deux largeurs ne décrivent pas des vertus indépendantes. $\Delta n$ petit, c'est un objet *ponctuel* — une vraie particule, dirait l'intuition. $\Delta k$ petit, c'est un objet *d'élan pur* — une vitesse nette, une trajectoire propre (chapitre VII : l'élan d'une composante, c'est son $k$). La question du chapitre devient : peut-on avoir les deux ?

## 2. Les deux extrêmes, calculés

**L'objet d'élan parfait.** Prenons $\Delta k = 0$ : une seule onde, $u_n = \cos(k_0 n)$. Son élan est irréprochable. Sa localisation ? L'onde s'étend sur *tout* l'anneau, avec la même intensité partout : $\Delta n$ est maximal. Un objet qui sait parfaitement où il va n'est **nulle part en particulier**.

**L'objet de position parfaite.** Prenons $\Delta n = 0$ : toute la présence sur le seul nœud $0$, $u = \delta_0 = (1, 0, 0, \dots)$. Quel est son accord ? Sur notre anneau à $4$ nœuds, la décomposition se calcule en une ligne — projetons sur le catalogue $\{(1,1,1,1),\ \cos(\tfrac{\pi}{2}n),\ \sin(\tfrac{\pi}{2}n),\ \cos(\pi n)\}$ :
$$
\delta_0 = \tfrac14(1,1,1,1) + \tfrac12\cos\!\Bigl(\tfrac{\pi}{2}n\Bigr) + \tfrac14\cos(\pi n),
$$
(vérification directe : $\tfrac14 + \tfrac12 + \tfrac14 = 1$ au nœud $0$, et $0$ ailleurs ✓). Lisons : le pic contient **toutes les familles d'ondes du catalogue**, du fond uniforme au zigzag, avec des poids comparables. Et c'est général : sur un anneau à $N$ nœuds, le pic $\delta_0$ recrute les $N$ ondes *à poids égal*. $\Delta k$ est maximal. Un objet qui sait parfaitement où il est n'a **aucun élan défini** — il part dans tous les sens à la fois, et le chapitre IV nous l'avait déjà *montré* sans qu'on ait su le lire : le pic au repos qui se brisait en deux ondes filantes, c'était cette démocratie des $k$ en action.

Les extrêmes s'excluent. Reste à quantifier l'entre-deux.

## 3. Le compromis : un théorème déjà payé

Le mécanisme exact est déjà entre nos mains depuis le chapitre VI, §4 — la formule des battements. Superposons deux ondes de nombres d'onde $k_0 \pm \tfrac{\Delta k}{2}$ :
$$
\cos\!\Bigl(\bigl(k_0 + \tfrac{\Delta k}{2}\bigr)n\Bigr) + \cos\!\Bigl(\bigl(k_0 - \tfrac{\Delta k}{2}\bigr)n\Bigr) = 2\,\cos\!\Bigl(\tfrac{\Delta k}{2}\,n\Bigr)\,\cos(k_0 n).
$$
L'enveloppe $\cos(\tfrac{\Delta k}{2}n)$ dit tout : les deux ondes sont *en phase* au centre (elles s'additionnent, la présence est forte) et se *contrarient* dès que $\tfrac{\Delta k}{2}n$ approche $\tfrac{\pi}{2}$ — c'est-à-dire à la distance $n \approx \pi/\Delta k$ du centre. La localisation, dans un monde d'ondes, n'est **que cela** : une conspiration d'interférences, constructive ici, destructive partout ailleurs. Et le rayon de la zone constructive est fixé par l'écart des conspirateurs :
$$
\Delta n \;\approx\; \frac{\pi}{\Delta k}, \qquad\text{soit}\qquad \boxed{\;\Delta n \cdot \Delta k \;\gtrsim\; \pi.\;}
$$
Ajouter plus d'ondes (un accord riche, aux $k$ bien dosés) permet d'aplatir les rebonds de l'enveloppe et d'affiner le pic — mais jamais de battre la borne : pour *confiner* la présence dans une largeur $w$, il faut des composantes capables de se déphaser complètement sur la distance $w$, donc un éventail $\Delta k \gtrsim \pi/w$. C'est un théorème de comptage sur les interférences, pas une subtilité : **la position s'achète en monnaie d'élan, au taux fixe $\pi$**. (Le lecteur qui poussera vers l'analyse de Fourier trouvera la version rigoureuse, $\Delta n\,\Delta k \ge \tfrac12$ pour les écarts-types, avec la gaussienne comme unique profil qui touche la borne — c'est pour cela que nos paquets d'expérience étaient gaussiens.)

Une conséquence typiquement discrète mérite sa phrase. Le chapitre VII l'avait noté : $k$ vit sur un cercle, $\Delta k$ ne peut excéder $2\pi$. La borne donne alors $\Delta n \gtrsim \pi/2\pi$… de l'ordre d'**un nœud** : c'est le plancher. Rien, dans notre univers, ne peut être plus fin qu'une maille — non par interdit décrété, mais parce qu'en deçà d'un nœud, « plus fin » ne se fabrique avec aucun accord. Un monde discret porte sa propre limite de résolution.

## 4. La loi de mortalité des objets

Le compromis n'est pas une curiosité comptable : il gouverne la *durée de vie*. Rappel du chapitre VI : chaque composante $k$ voyage à sa vitesse $v_g(k)$, pente de la courbe de dispersion. Un objet de largeur $w$ transporte un éventail $\Delta k \approx \pi/w$, donc un éventail de **vitesses**
$$
\Delta v_g \;\approx\; \Bigl|\frac{dv_g}{dk}\Bigr|\,\Delta k \;=\; |\omega''(k_0)|\;\frac{\pi}{w},
$$
où $\omega''$ est la courbure de la carte de dispersion. Le paquet se disloque quand ses composantes extrêmes se sont séparées d'environ sa propre largeur : au bout d'un temps
$$
t^\* \;\approx\; \frac{w}{\Delta v_g} \;\approx\; \frac{w^2}{\pi\,|\omega''(k_0)|}.
$$
Retenons la dépendance : $\boxed{t^\* \propto w^2}$. **Deux fois plus localisé, quatre fois plus éphémère.** L'expérience obéit au chiffre près : sur la chaîne à $c = 0{,}7$, des paquets de largeurs $6$, $12$ et $24$ nœuds mettent respectivement $350$, $1\,400$ et $5\,100$ pas à s'élargir d'un facteur $\sqrt2$ — les rapports $4{,}0$ puis $3{,}6$, collés sur la prédiction. La formule dit aussi *où* vivre vieux : là où $\omega'' = 0$ — sur les portions droites de la carte. Le monde $c = 1$, courbe droite partout, offre l'immortalité ; partout ailleurs, chaque objet localisé porte sa date de péremption, inscrite dans sa largeur.

## 5. Le nom du théorème — et ce qu'il n'est pas

Écrivons notre borne dans le langage du chapitre VII, où $k$ est l'élan par unité d'intensité : $\Delta n \cdot \Delta k \gtrsim \pi$ devient *l'étalement en position multiplié par l'étalement en élan est borné inférieurement*. Le physicien du XXe siècle la reconnaît instantanément : c'est, à la constante $\hbar$ près ($p = \hbar k$), l'**inégalité de Heisenberg**, $\Delta x\,\Delta p \ge \hbar/2$ — le plus célèbre des « mystères quantiques ».

Et il faut ici une honnêteté complète, dans les deux sens. **Ce que nous avons vraiment obtenu :** le cœur mathématique de Heisenberg, intégralement — et il n'a *rien* de quantique. C'est un théorème sur les accords, vrai pour le son (une note brève n'a pas de hauteur nette : demandez aux percussionnistes), vrai pour la houle, vrai pour notre champ. Aucun $\hbar$, aucune probabilité, aucun observateur : le compromis existe dès que « être quelque part » signifie « être une superposition d'ondes ». Dans un cours usuel, l'inégalité tombe du formalisme quantique et paraît magique ; ici on voit qu'elle était *déjà là*, dans la trigonométrie des battements. **Ce qui manque encore, et que nous ne maquillerons pas :** en mécanique quantique, l'inégalité porte sur les statistiques de *mesures* faites sur une particule *unique*, détectée toujours entière en un seul point — c'est cette couche-là (l'interprétation probabiliste, le clic indivisible) qui est authentiquement quantique, et notre univers n'en possède pour l'instant aucun équivalent. Heisenberg-le-théorème est classique ; Heisenberg-la-lecture est quantique. Savoir découper ainsi le mystère est exactement le service qu'un modèle jouet peut rendre.

> **Le déclic.** Une particule ponctuelle est une impossibilité *grammaticale* dans un monde d'ondes : « être en un point » se dit « recruter tous les élans à la fois ». Le compromis position–élan n'est pas une limite de nos instruments ni une étrangeté quantique — c'est le prix de fabrication de la localisation par interférence, au taux inflexible $\Delta n\,\Delta k \gtrsim \pi$, avec pour corollaire la loi de mortalité $t^\* \propto w^2$.

## 6. Où nous en sommes

Nous avons répondu à la question du titre par un théorème : la localisation et l'élan se paient l'un l'autre, les points parfaits n'existent pas (plancher : la maille), et tout objet localisé est mortel, avec une espérance de vie en $w^2/|\omega''|$ que l'expérience confirme au chiffre près. Nous savons aussi, désormais, ce que ce résultat a de profond et ce qu'il n'a pas de quantique.

Mais ce chapitre laisse un goût d'inachevé, et il est temps de l'affronter. Toute notre mécanique — inertie, énergie, élan, force, masse — repose sur des objets qui, dans un univers générique, *se désagrègent*. La matière qui nous entoure, elle, ne se désagrège pas : un électron d'il y a treize milliards d'années est toujours un électron, identique au premier jour. Notre modèle a donc un chaînon manquant, et le diagnostic est posé depuis le chapitre VI : dans une dynamique **linéaire**, les composantes s'ignorent — chaque $k$ vit sa vie, rien ne les tient ensemble. Pour qu'un objet tienne, il faudrait que ses composantes se *parlent* : que la vague se raidisse là où elle est forte, juste assez pour compenser l'éventail des vitesses. Il faudrait — pour la première fois du livre — abandonner la linéarité. C'était notre hypothèse de parcimonie la plus ancienne, posée au chapitre I. Voyons ce qu'on gagne à la sacrifier.

> **Chapitre suivant — X. Comment fabriquer une vraie particule ?**
> *Où la non-linéarité recoud ce que la dispersion effiloche.*

---

# Chapitre X — Comment fabriquer une vraie particule ?

> **Question.** Peut-on construire un objet localisé qui ne s'étale **jamais** — une vraie particule, indestructible ?

Ce chapitre franchit un cap : nous allons sacrifier la linéarité, notre plus vieil axiome. Pour rester sur terre, tout sera accroché à un modèle mécanique qu'on peut construire avec du bois et de la ficelle. Le plan :

1. Le remède exigé par le diagnostic : que le champ agisse sur lui-même.
2. Le modèle jouet : une chaîne de **pendules** — un seul changement, $u \to \sin u$.
3. La découverte d'un fait nouveau : notre univers a plusieurs *vides*.
4. L'objet impossible à défaire : le **kink**, avec sa table de valeurs.
5. Les expériences : immortalité, collision, et — cadeau immense — la **relativité**.
6. Une conservation d'un genre nouveau : compter au lieu de mesurer.

## 1. Ce que « non-linéaire » veut dire, concrètement

Le chapitre IX a posé le diagnostic : dans une dynamique linéaire, les composantes d'un accord *s'ignorent* — chaque onde $k$ suit sa vitesse $v_g(k)$, personne ne retient personne, l'objet s'éventaille. Pour qu'un objet tienne, il faut que ses composantes se parlent : que le comportement du champ *dépende de son intensité*. Voilà la définition opérationnelle de la non-linéarité : **doubler le champ ne double plus le futur**. Le prix est connu d'avance, et il est lourd : la superposition meurt. Deux solutions additionnées ne feront plus une solution ; tout l'attirail des chapitres V–IX (modes, accords, dispersion) ne vaudra plus qu'*approximativement*, pour les champs faibles. On ne sacrifie pas un axiome fondateur sans savoir ce qu'on achète. Voyons l'achat.

## 2. Le modèle jouet : la chaîne de pendules

Repartons du chapitre VIII, cas du potentiel uniforme : chaque nœud portait un ressort de rappel identique, force $-g\,u_n$, et cela fabriquait la masse. Or un ressort linéaire est une idéalisation — la vraie mécanique en connaît un plus honnête : le **pendule**. Imaginons donc, pour chaque nœud $n$, un pendule d'angle $u_n$, monté sur un axe horizontal commun ; les pendules voisins sont reliés par un petit ressort de torsion (voilà le Laplacien : chaque pendule est rappelé vers *l'angle de ses voisins*) ; et la gravité rappelle chaque pendule vers le bas — force $-g\sin u_n$, la vraie formule du pendule, dont $-g\,u_n$ n'était que l'approximation aux petits angles. La règle devient :
$$
\boxed{\;u_n(t{+}1) = 2u_n(t) - u_n(t{-}1) - c^2 (Lu(t))_n - g\,\sin u_n(t).\;}
$$
Un seul caractère a changé depuis le chapitre VIII : $u \to \sin u$. Vérifions d'abord que nous n'avons rien perdu : pour les petites oscillations ($|u| \ll 1$), $\sin u \approx u$ et l'on retrouve *exactement* le monde massif du chapitre VIII — ondes, dispersion $\omega^2 \approx g + c^2k^2$, toute la mécanique linéaire est contenue dans la limite des champs faibles. La non-linéarité est une loupe qui ne déforme que les grands angles.

## 3. Le fait nouveau : plusieurs vides

Mais aux grands angles, quelque chose d'inédit apparaît. Demandons : quelles sont les configurations de repos parfait — champ immobile, énergie minimale ? Il faut $\sin u_n = 0$ avec tous les pendules alignés : $u_n = 0$… ou $2\pi$, ou $4\pi$, ou $-2\pi$. Un pendule pendu en bas après **un tour complet** est physiquement identique à un pendule qui n'a jamais tourné — même position, même énergie — mais son *compteur de tours* diffère. Notre univers possède désormais **une infinité de vides équivalents**, étiquetés par un entier : $u = 2\pi m$, $m \in \mathbb{Z}$. Le monde linéaire du chapitre VIII n'en avait qu'un ($u = 0$, la parabole $\tfrac12 g u^2$ n'a qu'un creux) ; le cercle du pendule en offre un par tour. Retenons ce fait : il paraît anodin, c'est lui qui va fabriquer la particule.

## 4. Le kink : l'objet qu'on ne peut pas défaire

Car voici l'idée. Fabriquons une configuration qui *relie deux vides différents* : loin à gauche, tous les pendules pendent à $u = 0$ ; loin à droite, tous pendent à $u = 2\pi$ (un tour complet) ; entre les deux, une zone de transition où les pendules s'échelonnent le long du tour. En chiffres, avec $g = 0{,}04$ (soit une largeur naturelle $\lambda = c/\sqrt g = 5$ nœuds), le profil d'équilibre est $u_n = 4\arctan(e^{n/\lambda})$ :

| $n$ | $-15$ | $-10$ | $-5$ | $-2$ | $0$ | $+2$ | $+5$ | $+10$ | $+15$ |
|---|---|---|---|---|---|---|---|---|---|
| fraction de tour $u_n/2\pi$ | $3\%$ | $9\%$ | $22\%$ | $38\%$ | $\mathbf{50\%}$ | $62\%$ | $78\%$ | $91\%$ | $97\%$ |

Lisons la table : à quinze nœuds du centre, les pendules pendent presque en bas (côté gauche : à peine soulevés ; côté droit : presque un tour entier) ; toute la **torsion** — le vrillage de la chaîne — est concentrée sur une dizaine de nœuds. Cet objet s'appelle un **kink** (une *vrille*). Il est localisé : son énergie (la torsion des ressorts + les pendules levés) est concentrée autour du centre, comme un paquet d'ondes. Mais il a sur le paquet un avantage écrasant, qui se voit à l'œil nu sur la table : **pour le défaire, il faudrait dévriller la chaîne** — c'est-à-dire faire repasser par-dessus la verticale une infinité de pendules, jusqu'au bout du monde. Aucune agitation locale, aucune dispersion, aucun frottement ne peut accomplir cela : les deux bouts de l'univers sont *vissés* dans des vides différents, et aucune opération locale ne change ce que valent les bouts. La localisation du kink n'est plus une conspiration d'interférences (chapitre IX) qu'un déphasage suffit à ruiner : c'est un **fait topologique**.

## 5. Les expériences

**Immortalité.** Posons le kink au repos et laissons tourner $4\,000$ pas : largeur initiale $4{,}530$, largeur finale $4{,}530$, centre immobile, énergie constante à $10^{-8}$ près. Comparons à la loi de mortalité du chapitre IX ($t^* \propto w^2$) : un paquet *linéaire* de cette largeur serait déjà dissous. Le kink, lui, tiendra un milliard de pas. Le mécanisme : la dispersion tire les composantes vers l'éventail, la non-linéarité les *raidit* là où le champ est fort — et le profil $4\arctan(e^{n/\lambda})$ est très exactement le point d'équilibre où les deux effets s'annulent nœud à nœud. Un **soliton** : une onde solitaire que sa propre non-linéarité recoud en permanence.

**Le kink lancé — et la stupeur relativiste.** Lançons-le maintenant à diverses vitesses, et mesurons trois choses : sa vitesse effective, sa largeur, son énergie. Les résultats, avec $E_0 = 8\sqrt g = 1{,}6$ l'énergie du kink au repos et $\gamma = 1/\sqrt{1 - v^2/c^2}$ :

| $v/c$ | vitesse mesurée | largeur mesurée | largeur $\;4{,}53/\gamma$ | énergie mesurée | énergie $\;E_0\,\gamma$ |
|---|---|---|---|---|---|
| $0$ | $0{,}0000$ | $4{,}530$ | $4{,}530$ | $1{,}5991$ | $1{,}6000$ |
| $0{,}3$ | $0{,}2994$ | $4{,}321$ | $4{,}321$ | $1{,}6762$ | $1{,}6773$ |
| $0{,}6$ | $0{,}5985$ | $3{,}622$ | $3{,}624$ | $1{,}9982$ | $2{,}0000$ |
| $0{,}8$ | $0{,}7965$ | $2{,}715$ | $2{,}718$ | $2{,}6622$ | $2{,}6667$ |

Prenons le temps de réaliser ce que dit ce tableau, colonne par colonne. La largeur du kink **se contracte** en $\sqrt{1 - v^2/c^2}$ — la contraction de Lorentz, à la troisième décimale. Son énergie **croît** comme $E_0\gamma$ — c'est $E = \gamma m c^2$, la formule d'Einstein, à la troisième décimale aussi. Personne n'a mis la relativité dans ce modèle : nous avons vissé des pendules sur une chaîne, et il en sort des particules qui se contractent en mouvement et dont l'énergie diverge à l'approche de $c$. La raison profonde tient en une phrase : notre équation ne connaît qu'*une seule* vitesse, $c$, celle du couplage entre voisins — et une théorie où une unique vitesse limite gouverne tout est, par construction, une théorie relativiste. La vitesse de la lumière du chapitre IV (le clin d'œil « toute ressemblance… ») vient de cesser d'être un clin d'œil : dans notre univers, *les objets massifs eux-mêmes* sont des structures d'ondes, et ils héritent de la cinématique de leurs ondes. La masse du kink, $E_0 = 8\sqrt g$, est de l'énergie de configuration — de la torsion stockée. $E = mc^2$ n'est pas une propriété exotique de notre monde : c'est ce qui arrive dès que la matière est *faite* du champ.

**La collision.** Dernier test, le plus dur : fabriquons un kink (vrille $0 \to 2\pi$) et un **antikink** (dévrille $2\pi \to 0$), lançons-les l'un contre l'autre à $0{,}4\,c$, et regardons. Positions des deux concentrations d'énergie au fil du temps : elles se rapprochent ($1699/2300$, puis $1813/2186$), fusionnent en une mêlée violente où toute description en « deux objets » perd son sens… puis **ressortent** : $1653/2346$, $1294/2705$, $895/3104$ — deux objets intacts, s'éloignant à $0{,}399\,c$ chacun, l'énergie totale conservée à $10^{-4}$ près *pendant toute la mêlée*. Nos particules se traversent et survivent à leurs propres collisions. (Honnêteté : cette élasticité quasi parfaite est une grâce particulière de l'équation des pendules — le *sine-Gordon* des physiciens, une équation dite intégrable. D'autres non-linéarités donnent des collisions qui rayonnent, capturent, ou détruisent. Mais l'existence même d'objets localisés indestructibles, elle, ne dépend que de la topologie.)

## 6. Compter au lieu de mesurer : la charge topologique

Donnons sa forme finale à l'argument d'indestructibilité. Définissons, pour toute configuration :
$$
\boxed{\;Q \;=\; \frac{u_{+\infty} - u_{-\infty}}{2\pi} \;=\; \text{(nombre de tours à droite)} - \text{(nombre de tours à gauche)}.\;}
$$
$Q$ est un **entier** : $+1$ pour le kink, $-1$ pour l'antikink, $0$ pour le vide et pour toute agitation ordinaire. Et $Q$ est conservé — la simulation de collision l'affiche : $Q = 0$ avant, pendant, après la mêlée. Mais notons bien la *nature* de cette conservation, car elle est d'une espèce nouvelle. Nos trésors précédents ($E$, $P$) étaient des sommes continues, conservées par des symétries via Noether, et dégradables en pratique (un paquet garde son $E$ en se dissolvant). $Q$, lui, est conservé parce qu'**un entier ne peut pas varier continûment** : pour passer de $1$ à $0$, il faudrait transiter par $Q = \tfrac12$, qui n'existe pas — il faudrait défaire un tour à l'infini, ce qu'aucun processus local ne peut faire. Aucune symétrie là-dedans : de la pure *forme*. Les physiciens disent : une loi de conservation **topologique**. Elle protège le kink comme le nœud d'une corde est protégé — non parce qu'une force le maintient, mais parce qu'aucun geste continu ne le dénoue.

> **Le déclic.** Une particule digne de ce nom n'est ni un point (chapitre IX l'interdit), ni un paquet (chapitre VI le tue) : c'est un **défaut topologique** — une configuration coincée entre deux vides, dont l'existence est protégée par un entier qu'aucun processus local ne peut changer. Sa masse est l'énergie de sa torsion, sa stabilité est un fait de forme, et sa cinématique — contraction, $E = \gamma mc^2$ — est celle de la relativité, offerte gratuitement par l'unicité de la vitesse de couplage. Il aura suffi, pour tout cela, de remplacer $u$ par $\sin u$.

## 7. Où nous en sommes

Le sacrifice de la linéarité a payé au-delà de toute espérance : un modèle mécanique en bois et ficelle (pendules + ressorts de torsion), un seul caractère changé dans la règle, et nous récoltons plusieurs vides, des kinks localisés et immortels, des collisions élastiques, une conservation d'un genre nouveau (compter des tours), et la relativité restreinte vérifiée à la troisième décimale — contraction de Lorentz et $E = \gamma mc^2$ — sans l'avoir jamais invitée. Notre univers contient désormais quelque chose qui mérite pleinement le nom de *particule*.

Tout ce que nous avons construit, cependant, vit encore sur une ligne — chaîne ou anneau. Or presque toutes nos grandes questions en attente sont des questions de *géométrie* : qu'est-ce qu'une dimension deux ? un univers en grille a-t-il des directions privilégiées, et guérissent-elles ? que devient la physique sur un graphe *désordonné*, où la symétrie n'existe qu'en moyenne ? et que se passe-t-il si le graphe lui-même *change* — s'étire, comme le nôtre ? Il est temps de quitter la ligne.

> **Chapitre suivant — XI. Changer de géométrie.**
> *Où l'univers cesse d'être une ligne, et où le hasard se révèle plus isotrope que le cristal.*

---

# Chapitre XI — Changer de géométrie

> **Question.** Toute notre physique a été construite sur une ligne. Que garde-t-elle, que perd-elle, que gagne-t-elle quand on change le graphe ?

Ce chapitre est un tour du propriétaire : quatre univers, quatre leçons. Le plan :

1. **La grille** : la dimension devient un théorème, mais les directions ne se valent plus.
2. **La guérison** : l'isotropie, que la grille n'a pas, émerge toute seule à grande échelle.
3. **Le désordre fort** : un univers-prison, où plus rien ne voyage.
4. **Le désordre faible** : l'élan reçoit une date de péremption.
5. Le bilan en forme de chiasme : *le hasard est plus isotrope que le cristal*.
6. **L'univers qui s'étire** : l'énergie fuit, mais une monnaie de secours survit.

## 1. La grille : deux élans valent une dimension

Prenons le graphe le plus simple après l'anneau : la **grille** — les nœuds $(x, y)$, chacun relié à ses quatre voisins. Le Laplacien s'écrit comme une somme de deux Laplaciens de lignes ($L = L_x + L_y$ : la rugosité horizontale plus la verticale), et surtout la grille possède **deux** translations indépendantes, $T_x$ et $T_y$, qui commutent avec $L$ et entre elles. Le théorème du chapitre VII ne demandait rien d'autre : sa preuve se rejoue à l'identique pour chaque axe, et livre **deux élans conservés**, $P_x$ et $P_y$. La définition semée au chapitre VII prend corps : la *dimension* d'un univers, c'est son nombre de translations indépendantes — ici, deux, comptées sur les doigts du groupe de symétrie, sans jamais avoir invoqué d'espace.

Les modes suivent la même logique de produit : les ondulations $\cos(k_x x + k_y y)$, étiquetées par un *couple* $(k_x, k_y)$ — l'élan a maintenant deux composantes. Et la relation de dispersion s'assemble toute seule à partir de celle du chapitre VI :
$$
\sin^2\frac{\omega}{2} \;=\; c^2\Bigl(\sin^2\frac{k_x}{2} + \sin^2\frac{k_y}{2}\Bigr).
$$

## 2. L'anisotropie — et sa guérison spontanée

Mais cette formule cache un défaut de naissance. Sur la ligne, une seule direction : rien à comparer. Sur la grille, on peut lancer un objet *le long d'un axe* ou *en diagonale* — et la question surgit : va-t-il à la même vitesse ? Calculons $|v_g|$ dans les deux directions, pour plusieurs normes de $|k|$ ($c = 0{,}5$) :

| $\lvert k\rvert$ | $\lvert v_g\rvert$ selon l'axe | $\lvert v_g\rvert$ en diagonale | rapport |
|---|---|---|---|
| $0{,}2$ | $0{,}4981$ | $0{,}4994$ | $1{,}003$ |
| $1{,}0$ | $0{,}4520$ | $0{,}4838$ | $1{,}070$ |
| $2{,}0$ | $0{,}2978$ | $0{,}4279$ | $1{,}437$ |
| $2{,}8$ | $0{,}0977$ | $0{,}3402$ | $3{,}483$ |

Lisons de bas en haut. Aux grands $|k|$ (ondulations serrées, qui *voient* la maille), la grille est brutalement **anisotrope** : la diagonale va jusqu'à trois fois et demie plus vite que l'axe — un front d'onde issu d'un point n'y est pas un cercle, mais un losange bombé. La grille a beau avoir ses deux translations exactes, elle a *perdu* une symétrie que la ligne ne pouvait pas trahir : la **rotation**. Quatre quarts de tour, et c'est tout — un monde cristallin, avec ses axes gravés.

Mais lisons maintenant de haut en bas : à $|k| = 0{,}2$, le rapport vaut $1{,}003$. Trois millièmes. La raison se voit sur la formule : aux petits $k$, $\sin^2(k_x/2) + \sin^2(k_y/2) \approx \tfrac14(k_x^2 + k_y^2) = \tfrac14|k|^2$ — qui ne dépend plus que de la **norme** de $k$, plus du tout de sa direction. Voilà un phénomène qui mérite qu'on s'arrête, car c'est l'un des plus profonds du livre : **une symétrie que le graphe ne possède pas devient vraie asymptotiquement**. Les grandes ondes, trop lisses pour distinguer les mailles, vivent dans un monde effectivement rond ; les fronts d'onde y sont des cercles à quelques millièmes près ; l'isotropie n'a pas été posée — elle a *émergé*, par myopie. C'est exactement ainsi que notre propre monde pourrait être discret sans que nous l'ayons jamais remarqué : il suffirait que toutes nos expériences soient des « grandes ondes » à l'échelle de la maille.

## 3. Le désordre fort : l'univers-prison

Changeons d'extrême. Au lieu d'un graphe trop régulier, prenons un monde *accidenté* : la chaîne du chapitre VIII, mais avec un potentiel **aléatoire** — chaque nœud tire un $V_n$ au hasard, uniforme dans $[0, W]$. Plus aucune symétrie, même approchée : chaque lieu est unique. Le chapitre VII a prononcé le verdict de principe (pas de $T$, pas de $P$, pas de « tout droit ») ; voyons le verdict *expérimental*. Posons un paquet au repos et regardons sa largeur au fil du temps :

| $t$ | $600$ | $1200$ | $1800$ |
|---|---|---|---|
| univers ordonné ($W = 0$) | $420$ | $840$ | $1140$ |
| désordre $W = 0{,}8$ | $14$ | $25$ | $14$ |
| désordre $W = 1{,}2$ | $9$ | $8$ | $9$ |

Dans l'univers lisse, le paquet fait ce qu'il sait faire : il rayonne, largeur $420$, $840$, $1140$ — croissance libre. Dans l'univers accidenté, la largeur est **clouée** : une douzaine de nœuds, pour toujours, et d'autant plus serrée que le désordre est fort. Ce n'est pas un ralentissement : c'est un *emprisonnement*. Le mécanisme, esquissé sans preuve : chaque accident du potentiel réfléchit une fraction de l'onde ; dans un désordre dense, les innombrables réflexions interfèrent, et — résultat célèbre et contre-intuitif — leur bilan n'est pas un brouillage mais une **extinction** : au-delà d'une certaine distance, les chemins se contrarient si systématiquement que l'onde ne passe plus du tout. C'est la *localisation d'Anderson* (Nobel 1977), et en dimension 1 elle est totale : le moindre désordre, à la longue, emprisonne tout. Un univers sans symétrie n'est pas un univers où l'on voyage mal — c'est un univers où, à terme, on ne voyage **pas**.

## 4. Le désordre faible : l'élan avec date de péremption

Entre le cristal parfait et la prison, il y a le cas physiquement le plus important : le désordre *faible* — un monde presque homogène, griffé de petites irrégularités. La symétrie n'y est plus exacte, mais elle survit **en moyenne** : aucun lieu n'est spécial *statistiquement*. Que devient alors la conservation de l'élan ? Ni maintenue, ni abolie : *dégradée en douceur*. Suivons $P(t)/P(0)$ pour un paquet lancé dans deux niveaux de griffure :

| $t$ | $500$ | $1000$ | $1500$ | $2000$ | $2500$ | $3000$ |
|---|---|---|---|---|---|---|
| $W = 0{,}02$ | $0{,}96$ | $0{,}92$ | $0{,}85$ | $0{,}82$ | $0{,}80$ | $0{,}67$ |
| $W = 0{,}08$ | $0{,}83$ | $0{,}45$ | $0{,}21$ | $0{,}00$ | — | — |

L'élan n'est plus une possession : c'est un **bail**. Sous griffure légère, il s'érode lentement — l'objet garde sa direction des milliers de pas, presque un mouvement inertiel ; sous griffure quadruple, la mémoire s'effondre en deux mille pas, et l'objet finit par diffuser dans tous les sens, sa direction oubliée. La durée du bail porte un nom en physique : le **libre parcours moyen** — la distance qu'un objet parcourt avant que le désordre ne lui ait fait perdre le fil. Et la règle générale se formule en une ligne, qui complète la grille de Noether :
$$
\text{symétrie exacte} \;\Rightarrow\; \text{conservation exacte} \qquad\qquad \text{symétrie statistique} \;\Rightarrow\; \text{conservation à terme.}
$$

## 5. Le chiasme : le hasard est plus isotrope que le cristal

Posons côte à côte nos deux mondes bidimensionnels imaginables, et le bilan a une forme étrange. La **grille** possède des translations *exactes* — élans conservés à la douzième décimale — mais elle a des axes : sa symétrie de rotation est brisée, et un observateur aux ondes courtes pourrait *mesurer* l'orientation de son univers. Le **semis aléatoire** (jetons les nœuds au hasard — les probabilistes disent *selon un processus de Poisson* — et relions les proches) ne possède *aucune* symétrie exacte : aucune réalisation ne se superpose à elle-même, ni décalée ni tournée. Mais sa *loi* les possède toutes : statistiquement, aucun lieu, aucune direction n'y est spéciale — et pour cause, le hasard n'a aucun axe à privilégier. Ses grandes ondes voient un milieu effectif parfaitement rond, sans le losange résiduel de la grille, au prix du bail du §4 sur leurs conservations.

D'où le chiasme, qu'il faut savourer : **le cristal a les conservations exactes mais trahit ses axes ; le hasard n'a que des conservations à terme mais une isotropie parfaite.** Ce n'est pas une curiosité de modèle jouet. C'est un argument qui pèse dans la physique la plus spéculative d'aujourd'hui : si notre espace-temps était discret, un maillage *régulier* laisserait des empreintes directionnelles (des axes cosmiques mesurables — on les cherche, on ne les trouve pas), tandis qu'un *saupoudrage aléatoire* n'en laisserait aucune. Les partisans des structures discrètes de l'espace-temps préfèrent, pour cette raison précise, le hasard au cristal. Si le monde est un graphe, il est probablement mal rangé — et c'est une vertu.

## 6. L'univers qui s'étire : l'énergie fuit, une monnaie survit

Dernière expérience, la plus cosmique. Tous nos graphes étaient figés ; or la table de Noether est formelle : l'énergie n'est garantie que si la loi ignore *la date*. Faisons-lui violence en douceur : prenons un mode pur sur l'anneau et affaiblissons **très lentement** le couplage — $c^2$ glisse de $0{,}49$ à $0{,}20$ en quarante mille pas, l'équivalent d'un univers dont les mailles se distendent. Suivons la fréquence du mode, son énergie, et leur rapport :

| $t$ | $8\,000$ | $16\,000$ | $24\,000$ | $32\,000$ | $40\,000$ |
|---|---|---|---|---|---|
| $\omega$ | $0{,}476$ | $0{,}443$ | $0{,}407$ | $0{,}368$ | $0{,}324$ |
| $E$ | $0{,}1112$ | $0{,}1040$ | $0{,}0961$ | $0{,}0873$ | $0{,}0773$ |
| $E/\omega$ | $0{,}2338$ | $0{,}2350$ | $0{,}2362$ | $0{,}2374$ | $0{,}2386$ |

Deux lignes s'effondrent, la troisième tient. La fréquence chute de $32\,\%$ — la note *grave* à mesure que l'univers se détend : c'est, trait pour trait, le **décalage vers le rouge** cosmologique. L'énergie chute de $30\,\%$, et elle n'est allée *nulle part* : la symétrie temporelle qui la scellait n'existe plus, voilà tout — dans notre propre Univers en expansion, l'énergie n'est pas non plus globalement conservée, et les photons du fond cosmologique rougissent depuis treize milliards d'années exactement ainsi. Mais la troisième ligne révèle la trouvaille : $E/\omega$ n'a bougé que de $2\,\%$ pendant que tout s'écroulait de $30$. C'est un **invariant adiabatique** : la monnaie de secours des univers qui changent *lentement* (lentement devant la période du mode — brutalisez le graphe, et elle casse aussi). L'énergie d'un mode n'est pas protégée, mais son énergie *comptée en quanta de fréquence* l'est presque. Le lecteur qui sait où l'histoire s'en va appréciera l'ironie : c'est précisément en méditant sur ce rapport $E/\omega$ — pourquoi diable est-il si robuste ? — que Planck et Ehrenfest ont posé les premières pierres de la théorie des quanta.

> **Le déclic.** La géométrie du graphe n'est pas un décor : c'est une *politique de conservation*. Symétrie exacte, trésor exact ; symétrie statistique, trésor à terme ; pas de symétrie, prison ; symétrie qui change dans le temps, fuite — avec une monnaie de secours pour les changements lents. Et deux surprises en travers : l'isotropie peut émerger d'un monde qui ne l'a pas, et le hasard est un meilleur gardien de la rondeur que l'ordre.

## 7. Où nous en sommes

Le tour du propriétaire est fait, et la table de Noether — née en aparté au chapitre IV — gouverne désormais tout le paysage : la grille et ses deux élans exacts mais ses axes trahis, l'isotropie émergente des grandes ondes, la prison d'Anderson, le bail du désordre faible, le redshift de l'univers qui s'étire et sa monnaie adiabatique $E/\omega$.

Notre reconstruction touche à sa fin — du moins sa partie mécanique. Récapitulons l'inventaire depuis le graphe nu : un opérateur forcé (le Laplacien), une dynamique forcée (le second ordre réversible), l'énergie, l'élan, la force, la masse, des particules topologiques relativistes, et maintenant la géométrie comme politique de conservation. Il reste les grandes questions que nous avons soigneusement mises en attente, et qui forment l'horizon des derniers chapitres : ce langage d'ondes qui *ressemble* tant à la mécanique quantique — qu'a-t-il de commun avec elle, et où passe exactement la frontière ? Que gagne-t-on à empaqueter nos deux photographies dans un seul nombre complexe ? Et si le temps lui-même n'était qu'une arête de plus ?

> **À suivre — Interlude : Pourquoi parle-t-on d'ondes ?**
> *Où l'on fait l'inventaire de ce qui, dans notre univers, est déjà quantique — et de ce qui ne le sera jamais gratuitement.*
