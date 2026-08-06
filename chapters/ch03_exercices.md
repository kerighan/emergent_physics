# Chapitre III — Exercices : pourquoi faut-il une mémoire ?

On travaille avec un graphe fini, simple et non orienté, de Laplacien $`L`$.
L’état à la date $`t`$ est le couple de champs $`(u(t),u(t-1))`$.

> **Point de vigilance.** Il faut distinguer deux notions : pouvoir reconstruire
> le passé, et retrouver exactement la même règle locale après renversement du
> temps. L’exercice 3 précise cette distinction.

## 1. Deux photographies sont-elles vraiment nécessaires ?

1. Montrer qu’une règle du premier ordre $`u(t+1)=F(u(t))`$ attribue un futur
   unique à un état présent donné.
2. Construire deux histoires différentes qui ont le même champ $`u(0)`$ mais
   des champs $`u(-1)`$ différents.
3. Expliquer pourquoi une règle du second ordre peut donner deux futurs
   différents à partir du même champ présent, tout en donnant un futur unique
   une fois le couple $`(u(0),u(-1))`$ fixé.
4. Sur la chaîne, prendre $`u(0)=0`$ et comparer les deux choix $`u(-1)=1`$ et
   $`u(-1)=-1`$ pour la règle
   $`u(t+1)=2u(t)-u(t-1)-c^2Lu(t)`$.

## 2. Écrire toutes les règles locales linéaires

On postule la forme
$`u(t+1)=\alpha u(t)+\beta u(t-1)-\gamma Lu(t)-\delta Lu(t-1)`$.

1. Justifier chacun des quatre termes à partir de la localité, de la linéarité
   et de l’homogénéité.
2. Montrer qu’un champ constant dans l’espace et dans le temps impose
   $`\alpha+\beta=1`$.
3. Pourquoi cette condition ne donne-t-elle aucune information sur $`\gamma`$
   et $`\delta`$ ?
4. Que signifie le fait que $`\gamma`$ et $`\delta`$ puissent être négatifs ?
   Est-ce interdit par les hypothèses du chapitre ?

## 3. Audit de la réversibilité

Partir de la règle de l’exercice 2 et supposer $`\beta\neq0`$.

1. Regrouper les termes contenant $`u(t-1)`$ et montrer que
   $`(I+\delta L)u(t-1)=(\alpha I-\gamma L)u(t)-u(t+1)`$.
2. À quelle condition peut-on reconstruire le passé ? Cette condition dépend-elle
   du graphe et du spectre de $`L`$ ?
3. Écrire la relation obtenue après renversement du temps, en échangeant les
   rôles de $`t+1`$ et $`t-1`$.
4. Montrer que si l’on exige que cette relation soit **la même règle locale**,
   avec le même coefficient devant le Laplacien, alors $`\delta=0`$.
5. Examiner séparément la branche $`\beta=1`$. Que devient-elle après la
   condition $`\alpha+\beta=1`$ ?

## 4. Contre-exemple à l’unicité annoncée

Sur un graphe quelconque, considérer
$`u(t+1)=2u(t)-u(t-1)-\gamma Lu(t)-\delta Lu(t-1)`$.

1. Choisir un graphe à deux sommets, $`\gamma=1`$ et $`\delta=1/2`$.
   Écrire explicitement la matrice $`I+\delta L`$.
2. Prendre $`u(-1)=(1,0)`$ et $`u(0)=(0,0)`$. Calculer $`u(1)`$.
3. Calculer $`(I+\delta L)^{-1}`$ et reconstruire $`u(-1)`$ à partir de
   $`u(0)`$ et $`u(1)`$.
4. Vérifier que l’inverse existe ici, mais qu’il ne s’agit pas de la même règle
   locale que la règle directe.
5. Rédiger en trois lignes la correction à apporter à la phrase « la règle est
   forcée » du chapitre.

## 5. La règle retenue par le chapitre

On prend maintenant $`\delta=0`$, $`\gamma=c^2`$, et
$`u(t+1)=2u(t)-u(t-1)-c^2Lu(t)`$.

1. Vérifier que la formule est réversible.
2. Pour $`c=1`$ sur la chaîne, montrer que la règle devient
   $`u_n(t+1)=u_{n-1}(t)+u_{n+1}(t)-u_n(t-1)`$.
3. Pour une fonction quelconque $`f`$, vérifier que $`u_n(t)=f(n-t)`$ est une
   solution exacte.
4. Vérifier de même que $`u_n(t)=f(n+t)`$ est une solution exacte.
5. Que devient le profil si les deux photographies initiales sont exactement
   identiques ?

## 6. Pourquoi le miracle dépend de $`c=1`$

Sur la chaîne, prendre $`u_n(t)=f(n-t)`$ dans la règle générale avec $`c`$.

1. Calculer séparément $`u_n(t+1)`$, $`2u_n(t)-u_n(t-1)`$ et $`(Lu(t))_n`$.
2. Montrer que le résidu de l’équation vaut $`(1-c^2)`$ fois une différence
   seconde de $`f`$.
3. En déduire que tout profil translaté est solution pour $`c=1`$, mais pas en
   général pour $`c\ne1`$.
4. Trouver un profil non constant qui reste solution pour une valeur $`c\ne1`$.
   Que révèle cet exemple sur la phrase « la bosse se déforme lentement » ?

## 7. Réversibilité ne signifie pas stabilité

Sur un mode propre $`L\varphi=\lambda\varphi`$, chercher des solutions de la
forme $`u(t)=a(t)\varphi`$.

1. Montrer que $`a(t)`$ vérifie une récurrence scalaire du second ordre.
2. Pour $`\lambda=0`$, trouver les deux solutions élémentaires.
3. Pour $`\lambda>0`$, poser $`a(t)=r^t`$ et obtenir l’équation vérifiée par
   $`r`$.
4. Peut-on déduire de la réversibilité que $`|r|=1`$ ? Qu’est-ce qui manque
   encore pour garantir l’absence de croissance exponentielle ?

## 8. Synthèse critique

Rédiger une réponse structurée aux deux questions suivantes :

1. Qu’est-ce que la mémoire permet réellement : une vitesse, une réversibilité,
   une stabilité, ou seulement un état plus riche ?
2. Quelle version minimale et honnête de la conclusion du chapitre peut-on
   conserver après l’audit de $`\delta`$ ?

La réponse devra distinguer résultat démontré, choix supplémentaire et
interprétation physique.
