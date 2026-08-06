# Programme de reconstruction

Ce document sert de boussole au projet. Il ne constitue ni un chapitre du cours ni une promesse de tout reconstruire. Son rôle est de maintenir une direction claire : partir d'hypothèses locales, simples et explicites, puis comprendre quelles formes de physique elles rendent naturelles.

L'ambition n'est pas de prétendre que l'Univers réel a nécessairement été construit de cette manière. Nous cherchons quelque chose de plus modeste, mais déjà précieux : une intuition raisonnable de la raison pour laquelle certaines grandes structures de la physique reviennent si souvent.

Notre principe de parcimonie peut se formuler comme un principe de moindre information : parmi les lois compatibles avec les contraintes explicites, ne pas introduire arbitrairement une direction, un sommet, une échelle ou une corrélation privilégiés. C'est en ce sens que nous parlerons parfois de **prior maximalement non informatif** ou de **MaxEnt**. Il s'agit d'un principe d'inférence, pas nécessairement d'entropie thermodynamique.

À chaque étape, nous distinguerons donc soigneusement :

- ce qui découle effectivement des hypothèses ;
- ce qui n'apparaît que dans une limite ou une approximation ;
- ce qui ressemble à une théorie connue sans encore en posséder tout le contenu ;
- ce qui doit être ajouté comme nouvelle hypothèse.

## Le fil directeur

La progression visée est la suivante :

```text
graphe et localité
        ↓
calcul local et Laplacien
        ↓
dynamique réversible et énergie
        ↓
ondes, modes et propagation
        ↓
vitesse limite et masse effective
        ↓
objets non linéaires stables
        ↓
mouvement de leur centre
        ↓
mécanique newtonienne effective
        ↓
enveloppes complexes et équation de Schrödinger
        ↓
frontière entre analogie ondulatoire et véritable quantique
```

Cette chaîne est aussi un garde-fou éditorial. Un nouveau développement doit répondre à une question laissée ouverte par l'étape précédente. Sinon, il appartient probablement à un aparté, une annexe ou un autre volume.

## I. Le socle : une théorie classique des champs sur un graphe

Les premiers chapitres construisent progressivement :

- un champ, c'est-à-dire un nombre porté par chaque sommet ;
- un calcul local de comparaison, le Laplacien du graphe ;
- une dynamique possédant une mémoire ;
- une énergie conservée et des conditions de stabilité ;
- des modes propres, des paquets d'ondes et une quantité de mouvement ;
- des interactions et des objets non linéaires.

Ce socle n'est pas encore de la mécanique quantique, de la relativité ou de la mécanique newtonienne. C'est une théorie classique de champs discrets, à partir de laquelle certaines structures connues pourront éventuellement émerger.

## II. Première direction : une relativité émergente

La dynamique ondulatoire locale suggère naturellement :

- un domaine d'influence limité après un nombre fini de pas de temps ;
- une vitesse caractéristique de propagation ;
- une relation de dispersion entre fréquence et nombre d'onde ;
- une distinction entre excitations sans masse et excitations massives.

À grande longueur d'onde, une chaîne régulière peut conduire à une relation du type

```math
\omega^2(k) \simeq c^2k^2.
```

L'ajout d'un rappel local peut donner

```math
\omega^2(k) \simeq c^2k^2+m^2,
```

analogue à la relation de dispersion de Klein--Gordon.

L'objectif ne sera pas d'annoncer trop vite « nous avons obtenu la relativité ». Il faudra déterminer précisément :

1. dans quel régime continu une symétrie de Lorentz approximative apparaît ;
2. comment le graphe ou le réseau définit encore un référentiel privilégié à courte longueur d'onde ;
3. quelles prédictions dépendent de ce référentiel microscopique ;
4. ce que signifie réellement la masse dans ce modèle.

## III. Deuxième direction : faire émerger la seconde loi de Newton

L'objectif le plus concret est de comprendre comment une loi de la forme

```math
M\ddot X = F
```

peut devenir la description effective d'un objet sans avoir été postulée pour cet objet.

Une route plausible, qui devra être calculée et testée à la main, est la suivante.

### 1. La topologie fournit un objet persistant

Une excitation linéaire localisée se disperse généralement. Une structure non linéaire portant une charge topologique peut, au contraire, ne pas pouvoir disparaître par une petite déformation continue.

La topologie n'explique pas à elle seule le mouvement, mais elle peut expliquer pourquoi il existe quelque chose d'assez stable pour que l'on puisse suivre sa position.

### 2. La symétrie de translation fournit une coordonnée

Si une même solution localisée peut être centrée en différents endroits sans changer son énergie, elle appartient à une famille que l'on peut noter

```math
u^{(X)}.
```

Le paramètre collectif $X$ devient la position effective de l'objet. Déplacer lentement l'objet revient alors à laisser $X$ dépendre du temps.

### 3. La mise en mouvement fournit l'inertie

En remplaçant le champ complet par l'approximation

```math
u(t) \simeq u^{(X(t))},
```

son énergie cinétique doit prendre, au premier ordre utile, la forme

```math
T_{\mathrm{eff}} \simeq \frac12 M_{\mathrm{eff}}\dot X^2.
```

La masse effective mesure alors le coût énergétique d'une mise en mouvement. Elle n'est plus une étiquette ajoutée à une particule : elle provient du nombre de degrés de liberté du champ qu'il faut déformer simultanément pour déplacer l'objet.

### 4. L'inhomogénéité fournit la force

Si le milieu ou une interaction fait dépendre l'énergie de la position, l'objet ressent un potentiel effectif $U_{\mathrm{eff}}(X)$. La conservation de l'énergie, ou le principe variationnel correspondant, conduit alors à

```math
M_{\mathrm{eff}}\ddot X \simeq -\frac{\mathrm d U_{\mathrm{eff}}}{\mathrm dX}.
```

Dans ce scénario :

- la topologie explique la persistance de l'objet ;
- la symétrie explique l'existence de sa position collective ;
- l'énergie de déformation explique son inertie ;
- le gradient d'énergie explique la force ;
- la seconde loi de Newton apparaît comme une approximation lente de la dynamique du champ.

Il faudra aussi étudier les corrections : masse dépendant de la position, émission d'ondes, frottement effectif, accélérations trop fortes et déformation interne de l'objet.

### 5. Le prior le moins informatif possible

Ici, « MaxEnt » ne désigne pas d'abord une entropie thermodynamique. Il désigne une règle de construction : étant données les contraintes que nous avons réellement justifiées, choisir la description qui ajoute le moins de structure arbitraire.

Ce principe intervient déjà implicitement :

- sans orientation donnée, aucun voisin ne reçoit spontanément un poids privilégié ;
- sans sommet distingué, une même loi doit s'appliquer partout ;
- sans échelle supplémentaire, on choisit la dépendance la plus simple compatible avec les symétries et les contraintes ;
- sans information sur des corrélations supplémentaires, on ne les introduit pas gratuitement.

Pour la mécanique effective, une piste plus ambitieuse consistera à appliquer ce principe non seulement aux états, mais aux trajectoires. On cherchera une distribution sur les histoires du système qui soit la moins informative possible sous quelques contraintes locales clairement énoncées : continuité du mouvement, coût moyen des variations, énergie moyenne ou invariances imposées. C'est une approche de type **maximum de calibre**.

La question décisive sera alors : ces seules contraintes sélectionnent-elles naturellement une pondération quadratique des vitesses et une action effective de la forme

```math
S_{\mathrm{eff}}[X]
=
\int \left(\frac12 M_{\mathrm{eff}}\dot X^2-U_{\mathrm{eff}}(X)\right)\,\mathrm dt ?
```

Si oui, la trajectoire la plus probable ou stationnaire satisferait

```math
M_{\mathrm{eff}}\ddot X=-\nabla U_{\mathrm{eff}}.
```

Mais il faudra vérifier que Newton n'a pas été caché dans le choix des contraintes. Dire « prenons un coût quadratique des vitesses » sans le justifier reviendrait presque à introduire l'inertie à la main. Le but est précisément d'identifier quelles symétries, quelles informations conservées et quelle notion d'indépendance rendent ce choix inévitable, ou au moins privilégié.

## IV. Troisième direction : l'analogie quantique

Les modes propres, les amplitudes complexes et les inégalités de Fourier donnent déjà un langage qui ressemble à celui de la mécanique quantique. Mais les mêmes objets existent dans une théorie classique des ondes.

Une première étape raisonnable serait de montrer qu'une enveloppe lentement variable d'un champ massif satisfait approximativement une équation du type

```math
i\partial_t\psi = -\frac{1}{2m}\Delta\psi + V\psi.
```

Nous pourrions alors comprendre naturellement l'origine de plusieurs structures de la mécanique ondulatoire. Cela ne suffirait pas à obtenir le quantique. Il resterait notamment à expliquer ou à postuler :

- l'interprétation probabiliste et la règle de Born ;
- les observables non commutatives ;
- la composition de plusieurs systèmes ;
- l'intrication ;
- le rôle de la mesure.

Cette partie devra donc porter autant sur la frontière de l'analogie que sur l'analogie elle-même.

## Ordre de travail recommandé

1. Achever et consolider les fondations classiques actuelles.
2. Étudier la limite continue, la vitesse de propagation et la masse de type Klein--Gordon.
3. Construire des objets non linéaires stables et une coordonnée collective.
4. Tester explicitement l'émergence de $M\ddot X=-\nabla U$.
5. Étudier les corrections relativistes et la limite lente newtonienne.
6. Dériver, si possible, une équation d'enveloppe de type Schrödinger.
7. Faire l'inventaire exact de ce qui manque encore au véritable quantique.

## Critère de réussite

Le projet réussit lorsqu'un lecteur peut répondre non seulement à « quelle équation utilise-t-on ? », mais aussi à :

> Quelles contraintes simples rendent cette équation naturelle, et qu'aurait-il fallu changer pour obtenir un autre monde ?

Nous ne chercherons donc pas à faire apparaître coûte que coûte les lois connues. Nous chercherons à comprendre pourquoi certaines lois deviennent robustes sous des hypothèses simples de localité, de symétrie, de stabilité et d'information disponible.
