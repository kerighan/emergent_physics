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
