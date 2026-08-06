# Prologue — Peut-on reconstruire la physique ?

## Si l'on effaçait toute la géométrie

Supposons que nous ayons le droit de reconstruire l'Univers depuis zéro.

Interdiction d'utiliser les lois de Newton, celles d'Einstein, ou celles de la mécanique quantique. Interdiction, même, de supposer que l'espace ressemble à celui que nous connaissons. Nous allons être plus radicaux encore : nous effaçons **presque toute la géométrie**.

Plus de coordonnées. Plus de distances. Plus d'angles. Plus de droites. Plus de vecteurs. Plus de vitesse. Plus de masse. Plus d'énergie.

Il ne reste qu'une immense collection de points, reliés entre eux. Et chaque point ne sait répondre qu'à une seule question :

> **« Quels sont mes voisins ? »**

C'est tout. Aucun point ne connaît sa position, car aucune position ne lui a été donnée. Aucune longueur n'est attachée aux arêtes ; aucun angle ne permet de dire que deux chemins tournent de la même façon. Il n'y a d'abord que ce tissu de relations : *qui touche qui*.

Le mot **d'abord** est important. À partir des seules connexions, on pourra déjà compter le nombre minimal d'arêtes entre deux sommets : une première notion de distance émergera ainsi. Mais elle sera *construite à partir du graphe*, et non importée d'un espace extérieur. C'est toute la méthode du livre en miniature : ne rien interdire à l'émergence, mais ne rien supposer avant de l'avoir fabriqué.

À première vue, la situation paraît désespérée. Comment parler de mouvement lorsqu'il n'existe plus de direction ? Comment définir une vitesse lorsqu'il n'existe plus de distance ? Comment parler d'une force lorsqu'il n'existe plus de trajectoire ? Toute la physique semble s'être évaporée avec la géométrie.

Pourtant une question demeure, et c'est elle qui guide ce livre :

> Était-ce réellement la géométrie qui portait la physique ? Ou bien les lois physiques sont-elles plus profondes que les coordonnées dont nous nous servons d'habitude pour les décrire ?

## Une reconstruction, pas une présentation

Dans la plupart des cours, les concepts arrivent dans un ordre historique ou pratique : on définit l'énergie, puis la quantité de mouvement, puis les forces, puis les ondes, puis les particules. Chaque objet est présenté parce qu'il *existe* et qu'il faudra bien s'en servir.

Nous ferons exactement l'inverse.

Nous partirons d'un monde où **aucun** de ces concepts n'existe. À chaque étape, nous nous heurterons à une difficulté concrète. Nous chercherons alors la structure mathématique **la plus simple** capable de la résoudre. Si elle fonctionne, nous continuons ; sinon, nous l'abandonnons et nous comprenons pourquoi.

La règle est stricte : nous ne chercherons jamais à retrouver un concept familier *seulement parce que nous savons qu'il existe*. Nous chercherons d'abord à résoudre le problème qui se pose. Si, chemin faisant, apparaissent une inertie, une énergie, une masse, ou même des particules, nous devrons pouvoir montrer précisément quelles hypothèses les ont rendues possibles — et lesquelles auraient permis autre chose.

C'est une contrainte inconfortable. C'est aussi ce qui rendra chaque découverte convaincante : quand un concept surgira, nous saurons s'il est réellement *forcé*, seulement naturel, ou choisi parmi plusieurs possibilités. Cette distinction fera partie du résultat.

## Les règles du jeu

Notre univers obéira à très peu de contraintes, mais elles seront intransigeantes.

**Localité.** Un point n'interagit qu'avec ses voisins. Aucune information ne peut apparaître spontanément à distance ; toute influence doit se propager de proche en proche.

**Homogénéité de la loi.** Les mêmes recettes s'appliquent partout. Cela ne signifie pas que tous les sommets se ressemblent : l'un peut avoir deux voisins et l'autre cinq. Cela signifie que la règle ne contient pas une liste secrète de sommets privilégiés. Si deux points disposent des mêmes informations locales, la loi les traite de la même manière.

**Parcimonie.** À chaque bifurcation, lorsque plusieurs constructions sont possibles, nous commençons par la plus pauvre — celle qui suppose le moins. La parcimonie n'est pas une preuve d'unicité : elle fixe un ordre d'exploration. Nous devrons toujours annoncer les autres portes que nous fermons.

## Comment lire les affirmations du livre

Trois statuts reviendront souvent.

- Une **définition** fixe le sens d'un mot dans notre modèle : par exemple, ce que nous accepterons d'appeler un « objet ».
- Un **théorème** découle des hypothèses annoncées et peut être vérifié ligne par ligne.
- Une **interprétation physique** rapproche un résultat du vocabulaire de la mécanique. Elle peut être éclairante sans être une identité avec notre Univers.

Le lecteur est invité à demander, à chaque apparition d'un mot familier : *qu'avons-nous démontré exactement ?* Cette question n'interrompt pas le voyage ; elle en est le moteur.

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

La structure que nous venons de décrire — des points, et pour chaque point la seule donnée de ses voisins — porte un nom en mathématiques : c'est un **graphe**. Un ensemble de sommets $`V`$, et un ensemble d'arêtes $`E`$ qui disent quels sommets sont voisins. Rien de plus : pas de longueur d'arête, pas de position des sommets, pas d'orientation privilégiée.

Nous avons introduit l'idée avant le mot, et c'est délibéré. Ce livre n'est pas un cours sur la théorie des graphes ; c'est une tentative de faire naître la physique à partir du strict minimum. Le graphe n'est que le décor le plus pauvre que nous ayons su imaginer. Toute la question est de savoir ce qu'on peut y bâtir.

## Un dernier avertissement

Ce livre ne cherche pas à reconstruire *exactement* notre Univers. Il pose une question plus fondamentale :

> Quelle est la plus petite quantité de structure nécessaire pour que des lois physiques puissent émerger ?

Peut-être verrons-nous apparaître une mécanique proche de celle de Newton. Peut-être des ondes surgiront-elles d'elles-mêmes. Peut-être certaines idées rappelleront-elles la mécanique quantique. Mais nous ne partirons jamais de ces théories. Nous partirons d'un réseau de relations, et de rien d'autre. Et nous verrons jusqu'où cette seule idée peut nous mener.
