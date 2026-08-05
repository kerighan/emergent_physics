# Chapitre II — Peut-on déplacer un objet ?

> **Question.** Comment définir un mouvement là où il n'y a ni coordonnées, ni directions ?
>
> *Nous ne savons même pas encore ce qu'est un objet.*

## 1. Qu'appellerons-nous un objet ?

Nous disposons d'un champ $`u`$ et d'un opérateur $`L`$. Nulle part il n'y a de « chose » qui se déplace. Il faut donc commencer par décider ce qu'un objet *pourrait être* dans ce monde.

La proposition la plus honnête est la suivante : un objet est une **configuration localisée du champ** — une région où $`u`$ est grand, entourée d'un fond où $`u`$ est nul. Concrètement, sur la chaîne $`\mathbb{Z}`$, une bosse :
$$
u_{-1} = 1,\quad u_0 = 2,\quad u_1 = 1, \qquad u_n = 0 \text{ ailleurs.}
$$

Et nous dirons que l'objet **se déplace** si, aux instants suivants, on retrouve *la même bosse*, simplement posée ailleurs. Pas une bosse déformée, pas une trace diluée : la même forme, translatée. C'est exigeant, mais c'est bien ce que fait une balle qu'on lance — elle ne se dissout pas en vol.

Reste à faire évoluer le champ. Introduisons le temps de la manière la plus économe possible : une suite d'instants discrets $`t = 0, 1, 2, \dots`$, et une règle qui fabrique $`u(t+1)`$ à partir de ce qui est disponible.

## 2. La règle la plus pauvre possible

Que peut utiliser un point $`v`$ pour décider de sa prochaine valeur ? Fidèles à la parcimonie, donnons-lui le strict minimum : **l'état présent, et rien d'autre**. Sa valeur $`u_v(t)`$, celles de ses voisins — c'est-à-dire, comme le chapitre I nous l'a appris, sa valeur et son Laplacien. La règle locale, linéaire et homogène la plus générale est alors
$$
u_v(t+1) \;=\; u_v(t) \;-\; \varepsilon\, (Lu(t))_v ,
$$
où $`\varepsilon > 0`$ est un petit pas. (Le coefficient devant $`u_v(t)`$ doit valoir $`1`$ : sinon un champ constant, censé être inerte, se mettrait à croître ou à fondre sur place.)

Lisons cette règle en français avant de la lancer :

> « À chaque instant, chaque point se rapproche un peu de la moyenne de ses voisins. »

Un point au-dessus de la moyenne locale ($`Lu > 0`$) redescend ; un point en dessous remonte. C'est la dynamique du nivellement. Elle semble raisonnable, presque inoffensive. Voyons ce qu'elle fait de notre bosse.

## 3. L'expérience : on lâche la bosse

Prenons $`\varepsilon = \tfrac{1}{2}`$ pour la lisibilité (sur la chaîne, la règle devient : *chaque point prend la moyenne de ses deux voisins*, puisque $`u_n(t+1) = u_n - \tfrac12(2u_n - u_{n-1} - u_{n+1}) = \tfrac{u_{n-1}+u_{n+1}}{2}`$). Calculons à la main.

**À $`t=0`$ :**
$$
\dots,\ 0,\ 0,\ 1,\ 2,\ 1,\ 0,\ 0,\ \dots
$$

**À $`t=1`$ :** chaque point prend la moyenne de ses voisins :
$$
\dots,\ 0,\ 0.5,\ 1,\ 1,\ 1,\ 0.5,\ 0,\ \dots
$$

**À $`t=2`$ :**
$$
\dots,\ 0.25,\ 0.5,\ 0.75,\ 1,\ 0.75,\ 0.5,\ 0.25,\ \dots
$$

Le verdict est sans appel, et il est double.

**Premier constat : la bosse ne va nulle part.** Elle est restée exactement centrée en $`0`$. Par symétrie, c'était couru d'avance : la configuration initiale est symétrique autour de $`0`$, la règle est symétrique, donc le champ reste symétrique pour toujours. Rien, dans cette dynamique, ne peut choisir la droite plutôt que la gauche.

**Second constat : elle se dissout.** Son maximum fond ($`2 \to 1 \to 1 \to \dots`$), sa largeur croît. Le total, lui, ne bouge pas — la somme $`\sum_n u_n(t)`$ vaut $`4`$ à chaque instant, car chaque point ne fait que redistribuer. L'objet ne disparaît pas : il **s'étale**, jusqu'à devenir un brouillard uniforme et indiscernable.

Ce comportement porte un nom : la **diffusion**. Notre règle est exactement l'équation de la chaleur discrète, $`u(t+1) - u(t) = -\varepsilon L u(t)`$, l'analogue de $`\partial_t u = \Delta u`$. Nous avons construit un excellent modèle… de goutte d'encre dans l'eau. Pas de balle.

## 4. Peut-on tricher en poussant la bosse ?

Un lecteur combatif objectera : la bosse était immobile au départ, rien d'étonnant à ce qu'elle le reste. Donnons-lui un élan ! Rendons la condition initiale asymétrique — plus de poids à droite :
$$
u_{-1} = 1,\quad u_0 = 2,\quad u_1 = 3,\qquad u_n = 0 \text{ ailleurs.}
$$
Un pas de calcul ($`t=1`$) : $`\;\dots,\ 0.5,\ 1,\ 2.5,\ 1,\ 1.5,\ \dots`$ — le centre de gravité, lui, n'a pas bougé. Ce n'est pas un accident. Calculons le **barycentre** $`X(t) = \sum_n n\, u_n(t) \,/\, \sum_n u_n(t)`$. Le dénominateur est conservé (§3). Pour le numérateur :
$$
\sum_n n\, u_n(t+1) = \sum_n n\,\frac{u_{n-1}(t) + u_{n+1}(t)}{2}
= \sum_m \frac{(m+1) + (m-1)}{2}\, u_m(t) = \sum_m m\, u_m(t).
$$
Le barycentre est **rigoureusement immobile**, quel que soit le profil initial. On peut sculpter la bosse comme on veut : son centre ne se déplacera jamais d'un pouce. La dynamique de nivellement est constitutionnellement incapable de transporter quoi que ce soit.

## 5. L'autopsie : où l'information de direction pourrait-elle vivre ?

Il faut comprendre cet échec en profondeur, car c'est lui qui va dicter la suite. Posons la question au niveau d'un seul pas de temps, $`t \to t+1`$, là où tout se joue.

Pour que la bosse avance vers la droite, il faudrait qu'au moment de la mise à jour, quelque chose distingue la droite de la gauche. Passons l'inventaire de ce que « sait » le système à l'instant $`t`$ :

- le graphe lui-même : parfaitement symétrique, aucune direction privilégiée ;
- la règle : la même partout, aveugle à l'identité des voisins (chapitre I, exigence (b)) ;
- l'état $`u(t)`$ : une photographie du champ.

Et c'est tout. Or une photographie ne contient pas de vitesse. Deux films — l'un où la balle va vers la droite, l'autre vers la gauche — peuvent passer par *la même image* à l'instant $`t`$. Si la loi d'évolution ne dépend que de cette image, elle doit produire **le même futur dans les deux cas**. La direction du mouvement n'est tout simplement **stockée nulle part**.

> **Le déclic.** L'échec n'est pas dû à un mauvais choix de coefficients, et aucun raffinement de la règle $`u(t+1) = f(u(t))`$ n'y changera rien. C'est un théorème d'impossibilité structurel : *toute* dynamique qui ne lit que l'instant présent est sans mémoire, et un système sans mémoire ne peut pas savoir d'où il vient — donc pas où il va. Le problème n'est pas la formule. C'est la **quantité d'information que nous avons accordée à l'état**.

La mécanique nous fait ici un clin d'œil qu'il faut savourer : c'est exactement pour cela que l'état d'une particule de Newton n'est pas sa position, mais le couple *(position, vitesse)*. Nous venons de redécouvrir, par l'échec, pourquoi ce doublement est inévitable. Mais dans notre monde sans coordonnées, « ajouter la vitesse » n'a aucun sens littéral — il n'y a pas de vecteurs. La seule chose que nous puissions ajouter, c'est du **passé**.

## 6. Une remarque avant de continuer : le hasard n'aurait pas fait mieux

On aurait pu tenter une autre voie naïve : lâcher un jeton sur un nœud, et le faire sauter à chaque instant vers un voisin choisi au hasard — une **marche aléatoire**. C'est le même échec, vu de profil. Sur la chaîne, la position après $`t`$ pas est $`X_t = \xi_1 + \dots + \xi_t`$ avec des pas indépendants $`\xi_i = \pm 1`$ ; d'où
$$
\mathbb{E}[X_t] = 0, \qquad \mathbb{E}[X_t^2] = t, \qquad \text{distance typique} \sim \sqrt{t}.
$$
Un mobile digne de ce nom parcourt une distance proportionnelle à $`t`$ — le régime **balistique**. La marche aléatoire fait $`\sqrt t`$ — le régime **diffusif** : pour aller deux fois plus loin, il lui faut *quatre* fois plus de temps. Et la raison profonde est identique : à chaque pas, le jeton ignore d'où il vient ; son prochain saut ne dépend que de sa position présente. Diffusion déterministe du champ, marche aléatoire du jeton : deux visages du même défaut, **l'absence de mémoire**. (Ce n'est pas un hasard si la densité de probabilité de la marche obéit précisément à notre équation de diffusion.)

## 7. Où nous en sommes

Nous voulions déplacer un objet. Nous avons essayé la dynamique la plus simple possible — chaque point se rapproche de la moyenne de ses voisins — et nous avons obtenu un monde où tout s'étale et où rien ne voyage : le barycentre de toute configuration est cloué sur place, à jamais. L'autopsie a livré la cause exacte : un état réduit à l'instant présent ne contient aucune information de direction. Aucune règle du premier ordre, si astucieuse soit-elle, ne fera jamais de mécanique.

Le remède est désormais sans mystère, et c'est l'état qui nous l'a soufflé : il faut que la mise à jour puisse consulter **deux instants**. Si un point connaît $`u(t)`$ *et* $`u(t-1)`$, alors le décalage entre les deux photographies encode « d'où vient » la configuration — une vitesse, sans le mot, sans vecteur, sans coordonnée. Une pure différence entre deux souvenirs.

Reste à écrire cette nouvelle règle. Et là, une surprise nous attend : en imposant nos exigences habituelles, plus une seule — que le futur et le passé jouent des rôles symétriques, comme dans toute la mécanique fondamentale —, la règle sera *presque entièrement forcée*. Et la première bosse que nous lancerons avec elle avancera d'un cran par pas de temps, sans se déformer, pour toujours.

> **Chapitre suivant — III. Pourquoi faut-il une mémoire ?**
> *Où l'on découvre qu'un souvenir suffit à fabriquer l'inertie.*