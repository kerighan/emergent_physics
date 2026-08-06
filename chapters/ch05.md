# Chapitre V — Quels sont les objets élémentaires de cette dynamique ?

> **Question.** Existe-t-il des formes qui survivent à leur propre évolution ?
>
> *Jusqu'ici, tout ce que nous avons lancé s'est brisé, étalé, ou transformé — sauf une bosse, sur un graphe très spécial. Nous cherchons les configurations que la dynamique respecte.*

## 1. Le problème : tout dépend de tout

Prenons un graphe quelconque et une configuration quelconque — trois bosses, un pic, du bruit. À chaque pas, chaque nœud tire sur tous ses voisins, qui tirent sur les leurs : au bout de dix pas, la moindre valeur dépend de milliers d'autres. Suivre l'évolution nœud par nœud est sans espoir, et surtout sans *lumière* : même en calculant tout, on ne comprendrait rien.

Face à un système inextricable, la stratégie du physicien est toujours la même : chercher les **mouvements les plus simples possibles**, puis tenter d'exprimer tout le reste comme un assemblage de ces mouvements-là. Et nous détenons, depuis le chapitre III, la clé qui rend cette stratégie légitime : notre règle est *linéaire*. Si $`u(t)`$ et $`w(t)`$ sont deux solutions, alors $`u(t) + w(t)`$ est une solution, et $`\mu\, u(t)`$ aussi. Les solutions se superposent sans se voir. Il suffirait donc de trouver une famille de solutions simples engendrant toutes les autres, et l'évolution la plus baroque deviendrait une somme d'évolutions triviales.

Reste à savoir ce que « simple » veut dire. C'est ici que la question du chapitre prend tout son sens.

## 2. Qu'est-ce qu'une forme qui survit ?

Faisons l'inventaire de ce que la dynamique a fait subir à nos objets jusqu'ici. La bosse du chapitre II s'est *dissoute*. Le pic du chapitre IV s'est *brisé* en ondes filantes. La bosse du chapitre III, elle, a survécu — mais sur un graphe d'une régularité parfaite, avec une vitesse d'exception ($`c = 1`$), et nous avons prévenu que ce miracle était fragile. La question devient donc : sur un graphe **quelconque**, existe-t-il des configurations que l'évolution ne défigure pas ?

Précisons « ne pas défigurer ». Le champ a le droit de changer — tout champ figé serait vite ennuyeux — mais nous demandons que sa *forme* demeure : que le profil à l'instant $`t`$ soit toujours **proportionnel** au profil initial. Toute l'évolution serait alors portée par un seul nombre, une amplitude globale :
```math
u(t) \;=\; a(t)\,\varphi,
```
où $`\varphi`$ est un profil fixe (un nombre par nœud, choisi une fois pour toutes) et $`a(t)`$ une amplitude qui évolue. La forme reste, seule l'intensité respire.

Prenons le temps de bien voir ce que cette écriture impose, car elle est plus restrictive qu'il n'y paraît. Chaque nœud $`v`$ se voit attribuer son coefficient personnel $`\varphi_v`$, une fois pour toutes ; et à l'instant $`t`$, sa valeur est $`a(t)\,\varphi_v`$ — *le même* facteur $`a(t)`$ pour tout le monde. Tous les nœuds montent et descendent **en bloc**, chacun à l'échelle de son coefficient : celui qui vaut le double d'un autre vaudra le double de cet autre à tout jamais. Le rapport entre deux nœuds quelconques est gravé dans le marbre. Autrement dit — et c'est le point qu'il ne faut pas rater — **rien ne circule** : le nœud $`3`$ ne « reçoit » jamais ce que portait le nœud $`1`$, aucun motif ne se déplace de proche en proche. C'est une photographie dont on tourne le bouton de contraste : l'image peut s'intensifier, pâlir, s'inverser (si $`a(t)`$ change de signe, tous les nœuds basculent *simultanément*), mais c'est toujours la même image. Un chœur où chaque chanteur a sa nuance attitrée, et qui enfle et diminue d'un seul souffle. Voilà notre définition d'un objet élémentaire : **une forme que la dynamique se contente de faire respirer**.

De telles formes existent-elles ? Injectons l'hypothèse dans la règle :
```math
a(t+1)\,\varphi \;=\; 2a(t)\,\varphi - a(t-1)\,\varphi - c^2 a(t)\, L\varphi .
```
Tout, dans cette équation, est proportionnel à $`\varphi`$ — sauf le dernier terme. Pour que l'égalité puisse tenir avec $`a(t)`$ scalaire, il n'y a pas le choix : il faut que $`L\varphi`$ soit lui-même proportionnel à $`\varphi`$,
```math
\boxed{\;L\varphi = \lambda\,\varphi\;}
```
pour un certain nombre $`\lambda`$. Et alors l'équation vectorielle s'effondre en une équation sur la seule amplitude :
```math
a(t+1) \;=\; \bigl(2 - c^2\lambda\bigr)\,a(t) \;-\; a(t-1).
```

Arrêtons-nous, car c'est un moment important du livre. La condition $`L\varphi = \lambda\varphi`$ définit ce que les mathématiciens appellent un **vecteur propre** de $`L`$, de **valeur propre** $`\lambda`$. Dans la plupart des cours, ces objets sont introduits comme un outil algébrique, et l'étudiant apprend à les calculer avant de savoir à quoi ils servent. Ici, le rapport est inversé : nous ne les avons pas choisis, nous les avons *trouvés* — ce sont exactement, et uniquement, **les formes que la dynamique transporte sans les défigurer**. Chercher les vecteurs propres du Laplacien, ce n'est pas faire de l'algèbre : c'est dresser le catalogue des objets élémentaires de l'univers.

## 3. Le catalogue existe, et il est complet

Deux questions immédiates : ces formes existent-elles toujours ? Et sont-elles assez nombreuses pour engendrer tout le reste ? C'est ici qu'un placement de chapitre I arrive à maturité. Nous y avions noté, « pour plus tard », que $`L`$ est une matrice **symétrique réelle**. Or l'algèbre linéaire réserve à ces matrices son plus beau théorème, le *théorème spectral* : toute matrice symétrique réelle de taille $`N`$ possède exactement $`N`$ vecteurs propres, à valeurs propres réelles, formant une **base orthonormée** de l'espace tout entier.

Traduisons chaque mot en physique. *Exactement $`N`$* : un graphe à $`N`$ nœuds possède $`N`$ formes élémentaires, ni plus ni moins — le catalogue est fini et complet. *Base* : **toute** configuration $`u`$ s'écrit, de façon unique, comme superposition
```math
u = \sum_{j} a_j\, \varphi_j
```
des formes du catalogue — aucun état, si biscornu soit-il, n'échappe à la décomposition. *Orthonormée* : les formes sont mutuellement « perpendiculaires », chacune est aveugle aux autres, et le coefficient $`a_j`$ se lit par simple projection. Et nous savons même où vivent les valeurs propres : la positivité de $`L`$ (chapitre I, §5 : $`u^\top L u \ge 0`$) impose $`\lambda \ge 0`$, et nous connaissons déjà le bas du catalogue — $`L\mathbf 1 = 0`$ : la première forme élémentaire de tout univers est le champ constant, avec $`\lambda = 0`$.

## 4. Que fait chaque forme ? Elle sonne.

Reste à résoudre la dynamique d'une amplitude : $`a(t+1) = (2 - c^2\lambda)\,a(t) - a(t-1)`$. C'est une récurrence à coefficients constants ; cherchons des solutions oscillantes $`a(t) = \cos(\omega t + \phi)`$. L'identité $`\cos(\omega(t{+}1)) + \cos(\omega(t{-}1)) = 2\cos\omega\,\cos(\omega t)`$ montre que cela fonctionne exactement quand
```math
2\cos\omega = 2 - c^2\lambda, \qquad\text{c'est-à-dire}\qquad \sin^2\!\frac{\omega}{2} = \frac{c^2\lambda}{4}.
```
Chaque forme du catalogue, laissée à elle-même, **oscille sur place** — elle ne voyage pas, elle ne se déforme pas, elle *vibre*, à une fréquence $`\omega(\lambda)`$ dictée par sa valeur propre : les formes lisses (petit $`\lambda`$, faible rugosité) vibrent lentement, les formes hérissées (grand $`\lambda`$) vibrent vite. Un lecteur musicien a déjà tout compris : les vecteurs propres sont les **harmoniques** de l'univers, et $`\omega(\lambda)`$ est la hauteur de chaque note. Une corde de guitare ne fait rien d'autre : ses modes propres sont la fondamentale et les harmoniques, chacun vibrant sur place à sa fréquence — et une corde pincée n'importe comment joue un *accord*, la superposition de ses modes. Notre univers est un instrument. Le graphe est sa lutherie : c'est la géométrie qui fixe le catalogue des notes.

La formule contient deux dividendes, qu'il ne faut pas laisser filer.

**Le seuil du chapitre IV s'explique enfin.** Pour que $`\omega`$ existe, il faut $`\sin^2(\omega/2) = c^2\lambda/4 \le 1`$, soit $`c^2\lambda \le 4`$. Si le graphe contient une forme trop rugueuse ($`c^2\lambda_{\max} > 4`$), l'équation n'a plus de solution oscillante : la récurrence bascule vers des solutions **exponentielles**, et c'est précisément ce mode-là qui explosait dans notre expérience des deux nœuds. Donnons-lui un visage, car il en a un : sur ce graphe, le catalogue ne contient que deux formes, le fond uniforme $`(1,1)`$ et la *bascule* $`(1,-1)`$ — un nœud en haut, l'autre en bas, la forme la plus hérissée possible ($`\lambda = 2`$, le maximum). C'est elle qui divergeait : à chaque pas, le champ restait une bascule parfaite — les deux nœuds rigoureusement opposés, la *forme* jamais défigurée — mais son amplitude était multipliée par un facteur constant supérieur à $`1`$. Une note qui garde son timbre et dont le volume double sans fin. La « limite de vitesse » du chapitre IV n'était donc pas une bizarrerie comptable : c'est la condition pour que *toutes les notes de l'instrument soient jouables*. Un univers trop rapide pour sa géométrie possède une note qui hurle.

**Le mode $`\lambda = 0`$ ne sonne pas, il dérive.** Pour le champ constant, la récurrence devient $`a(t+1) = 2a(t) - a(t-1)`$ : croissance *linéaire*, $`a(t) = a(0) + t\,P`$. Visualisons : ici le profil est $`\mathbf 1 = (1, \dots, 1)`$, le niveau uniforme, et son amplitude est simplement la hauteur de ce niveau. Dire qu'elle dérive linéairement, c'est dire que l'univers entier monte comme une marée — partout du même cran à chaque pas, sans qu'aucun nœud ne dépasse jamais ses voisins. Aucune tension, donc aucun rappel : le Laplacien, aveugle aux constantes depuis le chapitre I, laisse ce niveau filer en ligne droite, exactement comme une particule libre file sur son erre. Nous avons déjà rencontré cette dérive : c'est la croissance du total $`S(t)`$ du chapitre IV, et la pente conservée $`P`$ est notre première loi de conservation ! Elle habitait donc le mode zéro depuis le début : la « quantité de mouvement du total » est l'amplitude de la note silencieuse de l'univers. (Et ce n'est pas la dernière fois que le mode zéro nous fera ce genre de confidence.)

## 5. L'instrument le plus simple du monde

Tout ceci mérite d'être *vu*. Prenons le plus petit instrument non trivial : trois nœuds en ligne, $`1 - 2 - 3`$. Son Laplacien a pour catalogue complet ($`N = 3`$ notes, comme promis) :
```math
\varphi_0 = (1,1,1),\ \lambda = 0 \qquad \varphi_1 = (1,0,-1),\ \lambda = 1 \qquad \varphi_2 = (1,-2,1),\ \lambda = 3.
```
(Vérification en une ligne pour $`\varphi_1`$ : le nœud central voit $`2\cdot 0 - 1 - (-1) = 0`$ ✓, le nœud $`1`$ voit $`1 - 0 = 1`$ ✓, le nœud $`3`$ voit $`-1 - 0 = -1`$ ✓ : $`L\varphi_1 = 1\cdot\varphi_1`$.) Les trois formes ont un sens limpide : le fond uniforme ; la *balançoire* (les extrémités en opposition, le centre immobile) ; le *pincement* (le centre contre les bords). Ce sont les trois seules façons d'exister sur ce graphe sans se défigurer.

Faisons-les sonner, avec $`c = 1`$, lâchées au repos. La balançoire obéit à $`a(t+1) = a(t) - a(t-1)`$, dont on vérifie à la main la merveille : $`1, 1, 0, -1, -1, 0, 1, 1, \dots`$ — **période 6, exactement**. Le pincement obéit à $`a(t+1) = -a(t) - a(t-1)`$ : $`1, 1, -2, 1, 1, -2, \dots`$ — **période 3, exactement**. (Simulation faite : les profils restent $`(1,0,-1)`$ et $`(1,-2,1)`$ au facteur près, à la précision machine, pour toujours.) Deux notes parfaitement périodiques, la plus rugueuse vibrant deux fois plus vite que la plus lisse, conformément à $`\omega(\lambda)`$. Et n'importe quel état initial de cet univers à trois nœuds — *n'importe lequel* — est un accord de ces trois notes, chacune évoluant dans son coin comme si les autres n'existaient pas.

C'est le gain conceptuel du chapitre, et il est immense : l'évolution « inextricable » du §1 était une illusion d'écriture. Dans la bonne base, notre univers n'est pas un enchevêtrement de $`N`$ nœuds qui se tirent dessus — c'est une collection de $`N`$ **oscillateurs indépendants**, qui ne se parlent jamais. Toute la complexité apparente venait de ce que nous regardions l'instrument nœud par nœud au lieu de l'écouter note par note. (L'énergie du chapitre IV, au passage, respecte la partition : elle se décompose en une somme d'énergies par mode, chacune conservée séparément — chaque note garde son intensité pour l'éternité.)

> **Le déclic.** Les vecteurs propres ne sont pas une technique de calcul : ce sont les seuls objets que la dynamique accepte de transporter sans les défigurer. Diagonaliser le Laplacien, c'est accorder l'instrument — trouver les notes dont toute évolution, même la plus chaotique, n'est qu'un accord. La physique d'un graphe, c'est le spectre de son Laplacien.

## 6. Où nous en sommes — et le paradoxe qui nous attend

Nous avons demandé quelles formes survivent, et la réponse est totale : les vecteurs propres du Laplacien, et eux seuls ; ils forment un catalogue complet de $`N`$ formes orthogonales ; chacune vibre sur place à la fréquence $`\omega(\lambda)`$ fixée par sa rugosité ; le seuil de stabilité du chapitre IV est la condition que toutes les notes soient jouables ; et toute évolution est un accord de ces oscillations indépendantes.

Mais le lecteur vigilant a dû sentir un malaise grandir au fil du chapitre. Reprenons-le à froid. Chaque objet élémentaire **vibre sur place**. Aucun ne voyage. Or nous avons *vu*, au chapitre III, une bosse traverser la chaîne, cran par cran, imperturbable. Si toute évolution n'est qu'une somme de vibrations immobiles… **d'où vient le mouvement ?**

Il n'y a qu'une issue possible : le voyage doit être une *conspiration*. Des modes immobiles, vibrant chacun à sa fréquence, dont les phases s'accordent pour que leurs crêtes se renforcent *ici* à l'instant $`t`$, et *un cran plus loin* à l'instant $`t+1`$ — une illusion d'optique parfaitement réelle, entretenue par l'interférence. Mais alors tout repose sur l'accord des fréquences : il suffirait que les notes se décalent un peu — que $`\omega`$ ne croisse pas *exactement* comme il faut avec $`\lambda`$ — pour que la conspiration se défasse en route, et que le voyageur s'effiloche. Nous tenons du même coup, avant même de faire le calcul, l'intuition de ce qui distinguait le graphe « miraculeux » du chapitre III : sur lui, et pour $`c = 1`$ précisément, l'accord devait être parfait. Reste à comprendre quand il l'est, quand il ne l'est pas — et à quelle vitesse, au juste, voyage une conspiration.

> **Chapitre suivant — VI. Pourquoi les objets s'étalent-ils ?**
> *Où l'on apprend à lire la vitesse d'un objet sur une seule courbe.*

---
