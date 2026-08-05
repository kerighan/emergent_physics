
# Chapitre VIII — Qu'est-ce qu'une force ?

> **Question.** Comment un lieu peut-il agir sur un objet — et que devient l'élan quand tous les lieux ne se valent plus ?

Le plan du chapitre :

1. Trouver la *seule* modification de la règle que nos axiomes autorisent : un potentiel $`V`$.
2. Calculer exactement ce que $`V`$ fait à l'élan : un théorème, $`\Delta P = -\sum_n (V_{n+1} - V_n)\, u_n u_{n+1}`$, qui *est* la deuxième loi de Newton.
3. Vérifier que l'énergie, elle, survit — et voir la table de Noether prédire juste.
4. Expérimenter : la chute libre d'un paquet sur une rampe.
5. Découvrir un cadeau inattendu : un potentiel *uniforme* fabrique de la **masse**.

## 1. La seule porte restée ouverte

Notre univers est ennuyeux à la perfection : tout y va tout droit, pour toujours. Pour qu'il se passe quelque chose, il faut qu'un lieu puisse *agir* — attirer, repousser, freiner. Mais nous ne bricolerons pas : demandons, comme toujours, quelle est la modification **la plus pauvre** de la règle compatible avec les axiomes que nous *gardons*.

Reprenons la dérivation du chapitre III. Nous y avions imposé : localité, linéarité, homogénéité (de lieu et de date), champ constant inerte, réversibilité — et la règle était unique. Cassons maintenant *un seul* axiome : l'homogénéité **de lieu** (les coefficients peuvent dépendre du nœud), en gardant tout le reste. La forme générale redevient, au nœud $`v`$ :
$$
u_v(t{+}1) = \alpha_v\, u_v(t) + \beta_v\, u_v(t{-}1) - \gamma_v\,(Lu(t))_v - \delta_v\,(Lu(t{-}1))_v .
$$
La réversibilité (relire la règle à l'envers doit redonner la même règle, nœud par nœud) impose comme au chapitre III : $`\beta_v = -1`$ et $`\delta_v = 0`$, pour chaque $`v`$. Restent $`\alpha_v`$ et $`\gamma_v`$ libres. Le coefficient $`\gamma_v`$ est une vitesse locale $`c_v^2`$ — intéressant, mais gardons $`c`$ uniforme pour isoler la nouveauté. Toute la liberté nouvelle tient alors dans $`\alpha_v`$, que nous écrivons $`\alpha_v = 2 - V_v`$ :
$$
\boxed{\;u_v(t{+}1) = 2\,u_v(t) - u_v(t{-}1) - c^2\,(Lu(t))_v - V_v\, u_v(t).\;}
$$
En notation matricielle : $`u(t{+}1) = W u(t) - u(t{-}1)`$, avec $`W = 2 - c^2L - V`$ et $`V`$ **diagonale** ($`V_{vv} = V_v`$). C'est la seule porte que nos axiomes laissaient ouverte : un nombre par nœud, agissant à l'instant présent (la réversibilité interdit le passé, comme elle l'interdisait à $`L`$), couplé à la valeur locale du champ.

Que fait physiquement $`V_v > 0`$ ? Il ajoute au nœud $`v`$ un **rappel vers zéro** : là où $`V`$ est grand, le champ est tiré vers le bas plus fort, comme si le nœud était monté sur un ressort plus raide. Le paysage $`\{V_v\}`$ est un relief de raideurs. Le mot des physiciens : un **potentiel**. Notons tout de suite ce que le champ constant devient : $`L\mathbf 1 = 0`$ mais $`V\mathbf 1 \ne 0`$ — un champ plat *n'est plus inerte* là où $`V \ne 0`$. C'est le prix assumé : un lieu qui agit est, par définition, un lieu qui ne laisse pas tout tranquille.

## 2. Ce que $`V`$ fait à l'élan : le théorème central

Le chapitre VII a préparé le terrain : la conservation de $`P = u(t)^\top A\, u(t{-}1)`$ (avec $`A = T - T^\top`$) reposait sur la ligne 3 de la preuve, elle-même sur la commutation $`[L, A] = 0`$. Or $`V`$, sauf s'il est constant, **ne commute pas** avec $`A`$ : décaler puis peser par $`V`$, ou peser puis décaler, ce n'est plus pareil. Voyons *exactement* ce qui fuit.

> **Théorème (deuxième loi de Newton).** Pour toute solution de la règle avec potentiel, sur l'anneau,
> $$\boxed{\;P(t{+}1) - P(t) \;=\; -\sum_n \bigl(V_{n+1} - V_n\bigr)\; u_n(t)\, u_{n+1}(t).\;}$$

*Preuve.* Reprenons la machinerie du chapitre VII avec $`W = 2 - c^2L - V`$ (symétrique) :
$$
P(t{+}1) - P(t) = u(t)^\top W\!A\, u(t) \underbrace{-\, u(t{-}1)^\top A\, u(t) - u(t)^\top A\,u(t{-}1)}_{=\,0 \text{ par antisymétrie de } A}.
$$
Il reste $`u^\top W\!A\, u`$, qui ne retient que la partie symétrique de $`W\!A`$, à savoir $`\tfrac12(W\!A - AW) = \tfrac12[W, A]`$. Or $`[2, A] = 0`$, $`[L, A] = 0`$ (chapitre VII), donc $`[W, A] = -[V, A]`$ : *seul le potentiel contribue*. Le calcul de $`-\tfrac12 u^\top[V,A]u`$ en coordonnées (deux lignes : chaque arête $`\{n, n{+}1\}`$ collecte deux termes égaux) donne la formule. $`\blacksquare`$

Ce théorème est, mot pour mot, $`F = \Delta P/\Delta t`$ — mais lisons le membre de droite, car il est plus fin que la formule de Newton qu'on apprend :

- $`V_{n+1} - V_n`$ est la **pente locale du potentiel** — le gradient discret, arête par arête ;
- $`u_n u_{n+1}`$ est la **présence de l'objet sur l'arête** — grande là où le champ est intense des deux côtés, nulle là où l'objet n'est pas ;
- le signe : l'élan diminue quand l'objet occupe une *montée* de $`V`$. **L'objet est poussé vers les potentiels faibles** — il dévale le relief.

La force n'est donc pas une flèche attachée à l'objet : c'est une somme, sur tout l'univers, de *pente $`\times`$ présence*. Un objet n'est freiné que par les pentes qu'il occupe. (C'est le théorème d'**Ehrenfest** en version discrète et exacte : la variation de l'élan moyen égale la moyenne, pondérée par la présence, du gradient du potentiel.) Deux cas limites pour calibrer l'intuition. **$`V`$ uniforme** : toutes les différences $`V_{n+1} - V_n`$ sont nulles, $`\Delta P = 0`$ — un potentiel plat, si haut soit-il, est *invisible pour le mouvement* ; seules les **différences** de potentiel agissent, jamais sa valeur absolue. **$`V`$ localisé** (une bosse de potentiel quelque part) : l'objet ne sent rien tant qu'il n'y est pas, décélère dans la montée, et — l'énergie étant conservée, voir §3 — soit passe, soit fait demi-tour. Un mur, une barrière, un puits : tout le vocabulaire de la mécanique vient d'apparaître dans une somme.

## 3. Et l'énergie ? La table de Noether à l'épreuve

Le chapitre VII s'était conclu sur une table : *indifférence à la date* $`\to`$ énergie ; *indifférence au lieu* $`\to`$ élan. Notre potentiel $`V`$ est figé dans le temps mais varie dans l'espace : la table **prédit** donc que $`P`$ meurt (fait, §2) mais que $`E`$ survit. Vérifions qu'elle a raison. Posons
$$
E_V(t) = \tfrac12\,\|u(t) - u(t{-}1)\|^2 + \tfrac12\, u(t)^\top\bigl(c^2 L + V\bigr)\, u(t{-}1).
$$
La preuve du chapitre IV n'utilisait qu'une seule propriété de l'opérateur enjambant : sa *symétrie*. Or $`c^2L + V`$ est symétrique ($`V`$ est diagonale). La démonstration se rejoue mot pour mot, et $`E_V`$ est **exactement conservée** — simulation à l'appui : champ aléatoire, potentiel aléatoire, $`300`$ pas, douze décimales immobiles pendant que $`P`$ dérive conformément au théorème du §2. La grille de Noether n'est plus une grille de lecture : c'est un instrument de *prédiction*, et il vient de réussir son premier test en conditions réelles. (Corollaire physique : un objet qui grimpe une pente perd de l'élan mais pas d'énergie — il convertit du mouvement en tension de ressort, récupérable intégralement à la descente. Le demi-tour du §4 sera élastique.)

## 4. L'expérience : la chute libre

Prenons une longue chaîne, un paquet d'ondes bien formé ($`k_0 = 0{,}9`$, $`c = 0{,}7`$), et une **rampe** : $`V_n = g\,n`$, pente constante $`g = 6\times10^{-4}`$ — la version graphe d'un champ de pesanteur uniforme. Lançons le paquet *vers le haut* de la rampe et relevons son centre tous les 200 pas :
$$
200 \to 312 \to 414 \to 507 \to 588 \to 658 \to 716 \to 761 \to 793 \to 804 \to \mathbf{808} \to 797 \to 781 \to \dots
$$
Lisons les *accroissements* : $`112, 102, 93, 81, 70, 58, 45, 32, 11, 4`$, puis négatifs. Une décélération **quasi uniforme** — c'est la cinématique du projectile de Galilée, parabole comprise : le paquet monte en ralentissant régulièrement (force constante $`\Rightarrow`$ perte d'élan constante, notre théorème au travail), s'arrête un instant vers $`n = 808`$, puis **retombe**. Aucune trajectoire n'a été programmée, aucun vecteur accélération n'existe nulle part : il n'y a que des nœuds qui tirent sur des voisins, et un relief de raideurs. La pomme de Newton vient de tomber dans un monde qui ne sait pas ce qu'est la hauteur.

## 5. Le cadeau inattendu : $`V`$ uniforme fabrique de la masse

Revenons au cas « trivial » du §2 : $`V_n = V_0`$ partout. L'élan est intact, soit — mais la *dynamique*, elle, n'est pas intacte du tout. Refaisons la relation de dispersion du chapitre VI avec le terme en plus : pour $`u_n(t) = \cos(kn - \omega t)`$, la règle exige maintenant
$$
\cos\omega \;=\; 1 - \frac{V_0}{2} - c^2\bigl(1 - \cos k\bigr),
\qquad\text{soit, aux petits } k, \omega \text{ :}\qquad
\boxed{\;\omega^2 \;\approx\; V_0 + c^2 k^2.\;}
$$
Comparons les deux mondes. Sans potentiel : $`\omega \approx c\,k`$ — la courbe part de zéro, en droite ; toutes les grandes ondes filent à la vitesse $`c`$ ; *rien ne peut être lent*. Avec $`V_0`$ : la courbe part de $`\omega(0) = \sqrt{V_0} > 0`$ — il y a un **gap**, une fréquence plancher — et la vitesse de groupe devient
$$
v_g = \frac{c^2 k}{\sqrt{V_0 + c^2k^2}} \;\xrightarrow[k \to 0]{}\; 0.
$$
Nos objets peuvent enfin **ralentir jusqu'à l'arrêt**. Un paquet de grand $`k`$ file presque à $`c`$ ; un paquet de petit $`k`$ se traîne ; à la limite, un objet de $`k \to 0`$ *reste sur place tout en vibrant à la fréquence $`\sqrt{V_0}`$* — une chose qui a de l'énergie sans avoir de mouvement. L'expérience confirme au millième : le paquet qui filait à $`v_g = 0{,}662`$ dans le monde sans potentiel ne fait plus que $`0{,}513`$ avec $`V_0 = 0{,}3`$, exactement la valeur prédite.

Le lecteur physicien a reconnu la formule au premier regard : $`\omega^2 = V_0 + c^2k^2`$, c'est $`E^2 = m^2c^4 + p^2c^2`$ — la relation énergie-impulsion **relativiste**, et notre équation modifiée est l'équation de *Klein-Gordon* discrète. La traduction est vertigineuse de simplicité : **la masse, c'est $`\sqrt{V_0}`$** — la fréquence à laquelle un objet vibre quand il ne va nulle part. Notre univers primitif ne contenait que des objets « de lumière », condamnés à filer à $`c`$ ; il suffit d'un rappel uniforme — le même ressort sous chaque nœud, aucun lieu privilégié, aucune direction cassée — pour peupler le monde d'objets *lourds*, capables de repos. La masse n'est pas une quantité de matière : c'est un **loyer en fréquence**, payé partout pareil, qui courbe le bas de la relation de dispersion. (Et ce bas de courbe parabolique, $`\omega \approx \sqrt{V_0} + \tfrac{c^2}{2\sqrt{V_0}}k^2`$, est très exactement le territoire de l'équation de Schrödinger — nous y reviendrons le moment venu.)

> **Le déclic.** La force n'est pas un ingrédient nouveau : c'est le *déficit de conservation* de l'élan, calculable exactement, égal à la pente du potentiel pondérée par la présence. Newton ($`F = \Delta P/\Delta t`$), Ehrenfest (moyenne du gradient), Galilée (décélération uniforme sur une rampe) et même la masse relativiste ($`\omega^2 = V_0 + c^2k^2`$) tiennent dans une seule modification de la règle — la seule que les axiomes toléraient.

## 6. Où nous en sommes

Nous avons cassé l'homogénéité de la façon la plus économe possible, et la moisson dépasse la mise : un potentiel diagonal, unique porte ouverte ; la deuxième loi de Newton comme *théorème* exact, avec sa lecture fine (pente $`\times`$ présence, seules les différences de $`V`$ agissent) ; l'énergie qui survit, comme la table de Noether l'avait prédit ; la chute libre reproduite en silicium ; et la masse comme gap de dispersion, cadeau du potentiel uniforme.

Notre mécanique est presque complète : inertie, énergie, élan, force, masse. Mais un mot, dans tout ce chapitre, a été employé avec une désinvolture croissante : « l'objet ». Nos objets sont des *paquets* — des accords d'ondes — et le chapitre VI nous a appris qu'ils s'étalent, que leur localisation est une denrée périssable. Jusqu'où peut-on comprimer un paquet ? Peut-on fabriquer un objet *ponctuel* — toute la présence sur un seul nœud, tout l'élan bien défini ? Le lecteur se doute que non, et le chapitre VII a semé l'indice : un objet localisé mélange beaucoup de $`k`$, un objet de $`k`$ pur est étalé partout. Il est temps de transformer ce pressentiment en théorème — et de découvrir que l'impossibilité porte un nom célèbre.

> **Chapitre suivant — IX. Pourquoi les particules ne sont-elles pas des points ?**
> *Où un théorème sur les accords devient un principe d'incertitude.*

---
