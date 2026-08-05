
# Chapitre IX — Pourquoi les particules ne sont-elles pas des points ?

> **Question.** Peut-on fabriquer un objet parfaitement localisé — toute la présence sur un nœud — qui possède en même temps un élan bien défini ?

Le plan :

1. Poser les deux mesures en jeu : la largeur $`\Delta n`$ d'un objet, la largeur $`\Delta k`$ de son accord.
2. Examiner les deux cas extrêmes — et découvrir qu'ils s'excluent.
3. Démontrer le compromis : $`\Delta n \cdot \Delta k \gtrsim \pi`$, avec les outils du chapitre VI.
4. En tirer la loi de mortalité des objets : le temps de vie croît comme le *carré* de la largeur.
5. Nommer le résultat — et dire honnêtement ce qu'il a, et n'a pas, de quantique.

## 1. Les deux fiches d'identité d'un objet

Depuis le chapitre VI, tout objet a deux descriptions équivalentes : côté nœuds (le profil $`u_n`$, *où* est la présence) et côté ondes (l'accord $`\{A_k\}`$, *quelles* composantes le fabriquent). À chaque description, sa largeur. Côté nœuds : $`\Delta n`$, l'étalement de la présence autour de son centre (l'écart-type de l'intensité $`u_n^2`$, disons). Côté ondes : $`\Delta k`$, l'étalement des nombres d'onde qui portent un poids significatif dans l'accord.

Or ces deux largeurs ne décrivent pas des vertus indépendantes. $`\Delta n`$ petit, c'est un objet *ponctuel* — une vraie particule, dirait l'intuition. $`\Delta k`$ petit, c'est un objet *d'élan pur* — une vitesse nette, une trajectoire propre (chapitre VII : l'élan d'une composante, c'est son $`k`$). La question du chapitre devient : peut-on avoir les deux ?

## 2. Les deux extrêmes, calculés

**L'objet d'élan parfait.** Prenons $`\Delta k = 0`$ : une seule onde, $`u_n = \cos(k_0 n)`$. Son élan est irréprochable. Sa localisation ? L'onde s'étend sur *tout* l'anneau, avec la même intensité partout : $`\Delta n`$ est maximal. Un objet qui sait parfaitement où il va n'est **nulle part en particulier**.

**L'objet de position parfaite.** Prenons $`\Delta n = 0`$ : toute la présence sur le seul nœud $`0`$, $`u = \delta_0 = (1, 0, 0, \dots)`$. Quel est son accord ? Sur notre anneau à $`4`$ nœuds, la décomposition se calcule en une ligne — projetons sur le catalogue $`\{(1,1,1,1),\ \cos(\tfrac{\pi}{2}n),\ \sin(\tfrac{\pi}{2}n),\ \cos(\pi n)\}`$ :
$$
\delta_0 = \tfrac14(1,1,1,1) + \tfrac12\cos\!\Bigl(\tfrac{\pi}{2}n\Bigr) + \tfrac14\cos(\pi n),
$$
(vérification directe : $`\tfrac14 + \tfrac12 + \tfrac14 = 1`$ au nœud $`0`$, et $`0`$ ailleurs ✓). Lisons : le pic contient **toutes les familles d'ondes du catalogue**, du fond uniforme au zigzag, avec des poids comparables. Et c'est général : sur un anneau à $`N`$ nœuds, le pic $`\delta_0`$ recrute les $`N`$ ondes *à poids égal*. $`\Delta k`$ est maximal. Un objet qui sait parfaitement où il est n'a **aucun élan défini** — il part dans tous les sens à la fois, et le chapitre IV nous l'avait déjà *montré* sans qu'on ait su le lire : le pic au repos qui se brisait en deux ondes filantes, c'était cette démocratie des $`k`$ en action.

Les extrêmes s'excluent. Reste à quantifier l'entre-deux.

## 3. Le compromis : un théorème déjà payé

Le mécanisme exact est déjà entre nos mains depuis le chapitre VI, §4 — la formule des battements. Superposons deux ondes de nombres d'onde $`k_0 \pm \tfrac{\Delta k}{2}`$ :
$$
\cos\!\Bigl(\bigl(k_0 + \tfrac{\Delta k}{2}\bigr)n\Bigr) + \cos\!\Bigl(\bigl(k_0 - \tfrac{\Delta k}{2}\bigr)n\Bigr) = 2\,\cos\!\Bigl(\tfrac{\Delta k}{2}\,n\Bigr)\,\cos(k_0 n).
$$
L'enveloppe $`\cos(\tfrac{\Delta k}{2}n)`$ dit tout : les deux ondes sont *en phase* au centre (elles s'additionnent, la présence est forte) et se *contrarient* dès que $`\tfrac{\Delta k}{2}n`$ approche $`\tfrac{\pi}{2}`$ — c'est-à-dire à la distance $`n \approx \pi/\Delta k`$ du centre. La localisation, dans un monde d'ondes, n'est **que cela** : une conspiration d'interférences, constructive ici, destructive partout ailleurs. Et le rayon de la zone constructive est fixé par l'écart des conspirateurs :
$$
\Delta n \;\approx\; \frac{\pi}{\Delta k}, \qquad\text{soit}\qquad \boxed{\;\Delta n \cdot \Delta k \;\gtrsim\; \pi.\;}
$$
Ajouter plus d'ondes (un accord riche, aux $`k`$ bien dosés) permet d'aplatir les rebonds de l'enveloppe et d'affiner le pic — mais jamais de battre la borne : pour *confiner* la présence dans une largeur $`w`$, il faut des composantes capables de se déphaser complètement sur la distance $`w`$, donc un éventail $`\Delta k \gtrsim \pi/w`$. C'est un théorème de comptage sur les interférences, pas une subtilité : **la position s'achète en monnaie d'élan, au taux fixe $`\pi`$**. (Le lecteur qui poussera vers l'analyse de Fourier trouvera la version rigoureuse, $`\Delta n\,\Delta k \ge \tfrac12`$ pour les écarts-types, avec la gaussienne comme unique profil qui touche la borne — c'est pour cela que nos paquets d'expérience étaient gaussiens.)

Une conséquence typiquement discrète mérite sa phrase. Le chapitre VII l'avait noté : $`k`$ vit sur un cercle, $`\Delta k`$ ne peut excéder $`2\pi`$. La borne donne alors $`\Delta n \gtrsim \pi/2\pi`$… de l'ordre d'**un nœud** : c'est le plancher. Rien, dans notre univers, ne peut être plus fin qu'une maille — non par interdit décrété, mais parce qu'en deçà d'un nœud, « plus fin » ne se fabrique avec aucun accord. Un monde discret porte sa propre limite de résolution.

## 4. La loi de mortalité des objets

Le compromis n'est pas une curiosité comptable : il gouverne la *durée de vie*. Rappel du chapitre VI : chaque composante $`k`$ voyage à sa vitesse $`v_g(k)`$, pente de la courbe de dispersion. Un objet de largeur $`w`$ transporte un éventail $`\Delta k \approx \pi/w`$, donc un éventail de **vitesses**
$$
\Delta v_g \;\approx\; \Bigl|\frac{dv_g}{dk}\Bigr|\,\Delta k \;=\; |\omega''(k_0)|\;\frac{\pi}{w},
$$
où $`\omega''`$ est la courbure de la carte de dispersion. Le paquet se disloque quand ses composantes extrêmes se sont séparées d'environ sa propre largeur : au bout d'un temps
$$
t^\* \;\approx\; \frac{w}{\Delta v_g} \;\approx\; \frac{w^2}{\pi\,|\omega''(k_0)|}.
$$
Retenons la dépendance : $`\boxed{t^\* \propto w^2}`$. **Deux fois plus localisé, quatre fois plus éphémère.** L'expérience obéit au chiffre près : sur la chaîne à $`c = 0{,}7`$, des paquets de largeurs $`6`$, $`12`$ et $`24`$ nœuds mettent respectivement $`350`$, $`1\,400`$ et $`5\,100`$ pas à s'élargir d'un facteur $`\sqrt2`$ — les rapports $`4{,}0`$ puis $`3{,}6`$, collés sur la prédiction. La formule dit aussi *où* vivre vieux : là où $`\omega'' = 0`$ — sur les portions droites de la carte. Le monde $`c = 1`$, courbe droite partout, offre l'immortalité ; partout ailleurs, chaque objet localisé porte sa date de péremption, inscrite dans sa largeur.

## 5. Le nom du théorème — et ce qu'il n'est pas

Écrivons notre borne dans le langage du chapitre VII, où $`k`$ est l'élan par unité d'intensité : $`\Delta n \cdot \Delta k \gtrsim \pi`$ devient *l'étalement en position multiplié par l'étalement en élan est borné inférieurement*. Le physicien du XXe siècle la reconnaît instantanément : c'est, à la constante $`\hbar`$ près ($`p = \hbar k`$), l'**inégalité de Heisenberg**, $`\Delta x\,\Delta p \ge \hbar/2`$ — le plus célèbre des « mystères quantiques ».

Et il faut ici une honnêteté complète, dans les deux sens. **Ce que nous avons vraiment obtenu :** le cœur mathématique de Heisenberg, intégralement — et il n'a *rien* de quantique. C'est un théorème sur les accords, vrai pour le son (une note brève n'a pas de hauteur nette : demandez aux percussionnistes), vrai pour la houle, vrai pour notre champ. Aucun $`\hbar`$, aucune probabilité, aucun observateur : le compromis existe dès que « être quelque part » signifie « être une superposition d'ondes ». Dans un cours usuel, l'inégalité tombe du formalisme quantique et paraît magique ; ici on voit qu'elle était *déjà là*, dans la trigonométrie des battements. **Ce qui manque encore, et que nous ne maquillerons pas :** en mécanique quantique, l'inégalité porte sur les statistiques de *mesures* faites sur une particule *unique*, détectée toujours entière en un seul point — c'est cette couche-là (l'interprétation probabiliste, le clic indivisible) qui est authentiquement quantique, et notre univers n'en possède pour l'instant aucun équivalent. Heisenberg-le-théorème est classique ; Heisenberg-la-lecture est quantique. Savoir découper ainsi le mystère est exactement le service qu'un modèle jouet peut rendre.

> **Le déclic.** Une particule ponctuelle est une impossibilité *grammaticale* dans un monde d'ondes : « être en un point » se dit « recruter tous les élans à la fois ». Le compromis position–élan n'est pas une limite de nos instruments ni une étrangeté quantique — c'est le prix de fabrication de la localisation par interférence, au taux inflexible $`\Delta n\,\Delta k \gtrsim \pi`$, avec pour corollaire la loi de mortalité $`t^\* \propto w^2`$.

## 6. Où nous en sommes

Nous avons répondu à la question du titre par un théorème : la localisation et l'élan se paient l'un l'autre, les points parfaits n'existent pas (plancher : la maille), et tout objet localisé est mortel, avec une espérance de vie en $`w^2/|\omega''|`$ que l'expérience confirme au chiffre près. Nous savons aussi, désormais, ce que ce résultat a de profond et ce qu'il n'a pas de quantique.

Mais ce chapitre laisse un goût d'inachevé, et il est temps de l'affronter. Toute notre mécanique — inertie, énergie, élan, force, masse — repose sur des objets qui, dans un univers générique, *se désagrègent*. La matière qui nous entoure, elle, ne se désagrège pas : un électron d'il y a treize milliards d'années est toujours un électron, identique au premier jour. Notre modèle a donc un chaînon manquant, et le diagnostic est posé depuis le chapitre VI : dans une dynamique **linéaire**, les composantes s'ignorent — chaque $`k`$ vit sa vie, rien ne les tient ensemble. Pour qu'un objet tienne, il faudrait que ses composantes se *parlent* : que la vague se raidisse là où elle est forte, juste assez pour compenser l'éventail des vitesses. Il faudrait — pour la première fois du livre — abandonner la linéarité. C'était notre hypothèse de parcimonie la plus ancienne, posée au chapitre I. Voyons ce qu'on gagne à la sacrifier.

> **Chapitre suivant — X. Comment fabriquer une vraie particule ?**
> *Où la non-linéarité recoud ce que la dispersion effiloche.*

---
