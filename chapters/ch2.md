# Chapitre II — Peut-on déplacer un objet ?

> **Question.** Comment définir un mouvement là où il n'y a ni coordonnées, ni directions ?
>
> *Nous ne savons même pas encore ce qu'est un objet.*

## 1. Qu'appellerons-nous un objet ?

Nous disposons d'un champ $`u`$ et d'un opérateur $`L`$. Nulle part il n'y a de « chose » qui se déplace. Il faut donc commencer par décider ce qu'un objet *pourrait être* dans ce monde.

La proposition la plus honnête est la suivante : un objet est une **configuration localisée du champ** — une région où $`u`$ est grand, entourée d'un fond où $`u`$ est nul. Concrètement, sur la chaîne $`\mathbb{Z}`$, une bosse :
```math
u_{-1} = 1,\quad u_0 = 2,\quad u_1 = 1, \qquad u_n = 0 \text{ ailleurs.}
```

Et nous dirons que l'objet **se déplace** si, aux instants suivants, on retrouve *la même bosse*, simplement posée ailleurs. Pas une bosse déformée, pas une trace diluée : la même forme, translatée. C'est exigeant, mais c'est bien ce que fait une balle qu'on lance — elle ne se dissout pas en vol.

Reste à faire évoluer le champ. Introduisons le temps de la manière la plus économe possible : une suite d'instants discrets $`t = 0, 1, 2, \dots`$, et une règle qui fabrique $`u(t+1)`$ à partir de ce qui est disponible.

## 2. Une première règle : se rapprocher de ses voisins

Nous devons choisir une évolution. Commençons par celle qui prolonge le plus directement le chapitre I : chaque point corrige sa valeur dans le sens opposé à son écart local.

```math
u(t+1)=u(t)-\varepsilon Lu(t),\qquad \varepsilon>0.
```

Au sommet $`v`$,

```math
u_v(t+1)=\bigl(1-\varepsilon\deg(v)\bigr)u_v(t)
          +\varepsilon\sum_{w\sim v}u_w(t).
```

Cette seconde écriture permet de voir la règle sans matrice. Si $`0\le\varepsilon\deg(v)\le1`$, la nouvelle valeur est une moyenne pondérée de l'ancienne valeur et de celles des voisins. Les valeurs se mélangent localement ; aucun sommet ne consulte le reste du graphe.

Cette règle n'est pas la seule dynamique du premier ordre imaginable. C'est la première à essayer si l'on exige un **nivellement isotrope**, des poids non négatifs et aucune orientation cachée. L'expérience va donc établir un résultat précis : ce mécanisme de nivellement diffuse au lieu de transporter.

Sur la chaîne, chaque sommet a deux voisins. Avec $`\varepsilon=1/2`$,

```math
u_n(t+1)=\frac{u_{n-1}(t)+u_{n+1}(t)}2.
```

Le sommet oublie même sa propre valeur : il prend exactement la moyenne de ses deux voisins.

## 3. L'expérience : on lâche la bosse

Prenons $`\varepsilon=1/2`$ et calculons à la main. Par exemple, au centre de la bosse,

```math
u_0(1)=\frac{u_{-1}(0)+u_1(0)}2=\frac{1+1}{2}=1.
```

Juste à droite,

```math
u_1(1)=\frac{u_0(0)+u_2(0)}2=\frac{2+0}{2}=1.
```

Et un cran plus loin, une valeur apparaît déjà : $`u_2(1)=(1+0)/2=0{,}5`$. Les autres valeurs s'obtiennent de la même façon.

**À $`t=0`$ :**
```math
\dots,\ 0,\ 0,\ 1,\ 2,\ 1,\ 0,\ 0,\ \dots
```

**À $`t=1`$ :** chaque point prend la moyenne de ses voisins :
```math
\dots,\ 0,\ 0.5,\ 1,\ 1,\ 1,\ 0.5,\ 0,\ \dots
```

**À $`t=2`$ :**
```math
\dots,\ 0.25,\ 0.5,\ 0.75,\ 1,\ 0.75,\ 0.5,\ 0.25,\ \dots
```

Le verdict est sans appel, et il est double.

**Premier constat : la bosse ne va nulle part.** Elle est restée exactement centrée en $`0`$. Par symétrie, c'était couru d'avance : la configuration initiale est symétrique autour de $`0`$, la règle est symétrique, donc le champ reste symétrique pour toujours. Rien, dans cette dynamique, ne peut choisir la droite plutôt que la gauche.

**Second constat : elle se dissout.** Son maximum fond ($`2 \to 1 \to 1 \to \dots`$), sa largeur croît. Le total, lui, ne bouge pas. En effet, pour un champ à support fini,

```math
\sum_n u_n(t+1)=\frac12\sum_n u_{n-1}(t)+\frac12\sum_n u_{n+1}(t)=\sum_n u_n(t),
```

car décaler l'indice d'une somme ne change pas sa valeur. Ici, le total vaut donc $`4`$ à chaque instant. L'objet ne disparaît pas : il **s'étale**, jusqu'à devenir un profil de plus en plus large et de moins en moins reconnaissable.

Il faut distinguer deux vitesses. L'**influence** se propage : après $`t`$ pas, elle peut avoir atteint des sommets situés à $`t`$ arêtes. Mais le profil, lui, n'est pas transporté intact. Une frontière qui s'étend n'est pas encore un objet qui voyage.

Ce comportement porte un nom : la **diffusion**. Notre règle est exactement l'équation de la chaleur discrète, $`u(t+1) - u(t) = -\varepsilon L u(t)`$, l'analogue de $`\partial_t u = \Delta u`$. Nous avons construit un excellent modèle… de goutte d'encre dans l'eau. Pas de balle.

## 4. Peut-on tricher en poussant la bosse ?

Un lecteur combatif objectera : la bosse était immobile au départ, rien d'étonnant à ce qu'elle le reste. Donnons-lui un élan ! Rendons la condition initiale asymétrique — plus de poids à droite :
```math
u_{-1} = 1,\quad u_0 = 2,\quad u_1 = 3,\qquad u_n = 0 \text{ ailleurs.}
```
Un pas de calcul ($`t=1`$) : $`\;\dots,\ 0.5,\ 1,\ 2.5,\ 1,\ 1.5,\ \dots`$ — le centre de gravité, lui, n'a pas bougé. Ce n'est pas un accident. Calculons le **barycentre** $`X(t) = \sum_n n\, u_n(t) \,/\, \sum_n u_n(t)`$. Le dénominateur est conservé (§3). Pour le numérateur :
```math
\sum_n n\, u_n(t+1) = \sum_n n\,\frac{u_{n-1}(t) + u_{n+1}(t)}{2}
= \sum_m \frac{(m+1) + (m-1)}{2}\, u_m(t) = \sum_m m\, u_m(t).
```
Le barycentre est **rigoureusement immobile** pour tout profil dont les sommes précédentes convergent et dont la somme totale est non nulle. On peut sculpter la bosse comme on veut : cette dynamique ne lui donnera aucun déplacement net. Elle déplace pourtant des valeurs de proche en proche et élargit le support ; ce qu'elle ne fait pas, c'est transporter le profil comme un bloc.

Nous avons ici utilisé les indices $`n`$ comme un instrument de mesure extérieur. Les nœuds ne lisent jamais ces coordonnées : leur règle n'utilise que leurs voisins. Le barycentre est donc un bon diagnostic sur une chaîne, mais sa définition ne se transpose pas automatiquement à un graphe quelconque.

## 5. L'autopsie : que manque-t-il à l'état ?

Le calcul précédent condamne notre diffusion. Mais quelle leçon générale pouvons-nous en tirer sans aller trop loin ?

Une photographie peut être asymétrique : elle peut avoir davantage de champ d'un côté que de l'autre. Elle contient donc de l'information spatiale. En revanche, elle ne dit pas **comment elle a été atteinte**. Deux films peuvent passer par le même profil $`u(t)`$ : dans l'un, la bosse arrive de gauche ; dans l'autre, elle arrive de droite. Une règle déterministe qui ne reçoit que $`u(t)`$ doit attribuer le même futur à ces deux histoires.

Cela ne prouve pas que toute dynamique du premier ordre est incapable de translation. Sur une chaîne déjà orientée, la règle

```math
u_n(t+1)=u_{n-1}(t)
```

déplace parfaitement n'importe quel profil vers la droite. Mais elle utilise une information interdite dans notre graphe nu : elle sait lequel des deux voisins est « celui de gauche ». On pourrait aussi enrichir chaque nœud de plusieurs composantes internes et y stocker un sens de déplacement. Là encore, on aurait ajouté une structure.

Dans notre modèle actuel, l'inventaire est plus pauvre :

- le graphe est non orienté ;
- tous les voisins sont traités de la même façon ;
- chaque sommet ne porte qu'un scalaire ;
- la mise à jour ne lit qu'une photographie.

Sous ces restrictions, rien ne permet d'associer deux futurs opposés au même profil présent. La diffusion choisie au §2 va plus loin : elle efface progressivement les différences qui dessinaient l'objet.

> **Le déclic.** Nous n'avons pas démontré que « premier ordre » signifie toujours « pas de mouvement ». Nous avons montré que notre état actuel ne distingue pas deux histoires passant par la même photographie. Pour représenter une vitesse sans orienter le graphe ni ajouter une variable interne arbitraire, la solution la plus économique est de conserver une seconde photographie.

La mécanique classique fait une distinction analogue : connaître la position d'une particule ne suffit pas à prédire sa trajectoire ; il faut aussi sa vitesse. Ici, nous ne pouvons pas ajouter directement un vecteur vitesse, puisque nous n'avons pas encore de vecteurs spatiaux. En revanche, le couple $`(u(t),u(t-1))`$ contient une différence temporelle calculable en chaque nœud. Nous allons tester si ce souvenir suffit.

## 6. Une remarque avant de continuer : le hasard n'aurait pas fait mieux

On aurait pu tenter une autre voie naïve : lâcher un jeton sur un nœud, et le faire sauter à chaque instant vers un voisin choisi au hasard — une **marche aléatoire**. C'est le même échec, vu de profil. Sur la chaîne, la position après $`t`$ pas est $`X_t = \xi_1 + \dots + \xi_t`$ avec des pas indépendants $`\xi_i = \pm 1`$ ; d'où
```math
\mathbb{E}[X_t] = 0, \qquad \mathbb{E}[X_t^2] = t, \qquad \text{distance typique} \sim \sqrt{t}.
```
Un mobile digne de ce nom parcourt une distance proportionnelle à $`t`$ — le régime **balistique**. La marche aléatoire fait $`\sqrt t`$ — le régime **diffusif** : pour aller deux fois plus loin, il lui faut *quatre* fois plus de temps. Et la raison profonde est identique : à chaque pas, le jeton ignore d'où il vient ; son prochain saut ne dépend que de sa position présente. Diffusion déterministe du champ, marche aléatoire du jeton : deux visages du même défaut, **l'absence de mémoire**. (Ce n'est pas un hasard si la densité de probabilité de la marche obéit précisément à notre équation de diffusion.)

## 7. Où nous en sommes

Nous voulions déplacer un objet. Avec la règle de nivellement la plus directe, nous avons obtenu de la diffusion : le support s'élargit, le maximum baisse et le barycentre reste fixe. Nous avons ensuite isolé le manque d'information pertinent : une photographie seule ne distingue pas deux histoires qui la traversent avec des mouvements opposés. Une règle orientée pourrait contourner le problème, mais elle introduirait précisément la direction que nous voulons faire émerger.

Le remède que nous allons tester est désormais naturel : permettre à la mise à jour de consulter **deux instants**. Si un point connaît $`u(t)`$ *et* $`u(t-1)`$, alors le décalage entre les deux photographies encode « d'où vient » la configuration — une vitesse, sans le mot, sans vecteur, sans coordonnée. Une pure différence entre deux souvenirs.

Reste à écrire cette nouvelle règle. Nous ajouterons une exigence nouvelle : la même loi locale devra permettre de calculer le passé comme le futur. Sous cette forme forte de réversibilité, la règle sera *presque entièrement déterminée*. Et la première bosse que nous lancerons avec elle avancera d'un cran par pas de temps, sans se déformer, pour toujours.

> **Chapitre suivant — III. Pourquoi faut-il une mémoire ?**
> *Où l'on découvre qu'un souvenir suffit à fabriquer l'inertie.*
