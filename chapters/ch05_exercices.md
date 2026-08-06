# Chapitre V — Exercices : des formes stationnaires au mouvement

On considère la dynamique

```math
u(t+1)=2u(t)-u(t-1)-c^2Lu(t)
```

sur un graphe fini, simple et non orienté, sauf lorsque la chaîne infinie est
explicitement mentionnée. L’état à la date $`t`$ est le couple
$`(u(t),u(t-1))`$.

Le fil directeur est le suivant :

```text
deux photographies
      ↓
décomposition en profils stationnaires
      ↓
une récurrence temporelle par profil
      ↓
superposition de tous les petits films
      ↓
mouvement apparent du profil total
```

## 1. Qu’additionne-t-on exactement ?

Une solution est un film entier $`t\mapsto u(t)`$ vérifiant la règle à tout
instant.

1. Soient $`u`$ et $`w`$ deux solutions et soient $`\alpha,\beta`$ deux
   coefficients. Poser $`z(t)=\alpha u(t)+\beta w(t)`$.
2. En remplaçant $`z`$ dans la règle, montrer sans sauter de ligne que $`z`$
   est encore une solution.
3. Montrer que faire évoluer séparément deux paires initiales, puis additionner
   les résultats, revient à additionner d’abord les paires et à faire évoluer
   leur somme.
4. Pourquoi cette addition ne décrit-elle pas nécessairement deux particules
   matérielles placées au même endroit ?
5. Que se produit-il en un sommet lorsque les deux contributions ont des
   signes opposés ? Relier ce phénomène à l’interférence.

## 2. Chercher les dessins qui restent fixes dans l’espace

On cherche une solution sous la forme

```math
u(t)=a(t)\varphi,
```

où le profil $`\varphi`$ ne dépend pas du temps.

1. Injecter cette expression dans la règle.
2. Montrer que, pour $`c\ne0`$ et une solution non nulle, $`L\varphi`$ doit
   être proportionnel à $`\varphi`$.
3. Écrire $`L\varphi=\lambda\varphi`$ et retrouver

```math
a(t+1)=(2-c^2\lambda)a(t)-a(t-1).
```

4. Expliquer précisément ce qui reste fixe et ce qui évolue dans
   $`u(t)=a(t)\varphi`$.
5. Pourquoi un tel mode n’est-il pas encore une particule mobile ?
6. Que se passe-t-il dans le cas particulier $`c=0`$ ? La condition de
   vecteur propre est-elle encore nécessaire ?

## 3. Décomposer deux photographies sur trois sommets

On considère la chaîne $`1-2-3`$, de Laplacien

```math
L=
\begin{pmatrix}
1&-1&0\\
-1&2&-1\\
0&-1&1
\end{pmatrix}.
```

1. Vérifier que les trois vecteurs

```math
\varphi_0=(1,1,1),
\qquad
\varphi_1=(1,0,-1),
\qquad
\varphi_2=(1,-2,1)
```

   sont propres, de valeurs propres respectives $`0,1,3`$.
2. Vérifier qu’ils sont deux à deux orthogonaux et calculer leurs normes au
   carré.
3. En utilisant

```math
\text{coefficient de }\varphi_j
=\frac{\langle x,\varphi_j\rangle}{\|\varphi_j\|^2},
```

   décomposer $`x=(1,1,0)`$ dans cette base.
4. Décomposer de même $`y=(0,1,1)`$.
5. Prendre $`u(-1)=y`$, $`u(0)=x`$ et $`c=1`$. Faire évoluer séparément les
   trois coefficients jusqu’à $`t=1`$.
6. Reconstruire $`u(1)`$ en additionnant les trois modes.
7. Vérifier le résultat par un calcul direct avec la matrice $`L`$.

## 4. Une récurrence temporelle n’a pas besoin de trigonométrie

Pour un mode propre, poser $`q=2-c^2\lambda`$. Son amplitude vérifie

```math
a(t+1)=q\,a(t)-a(t-1).
```

1. Montrer que deux valeurs consécutives $`a(-1)`$ et $`a(0)`$ déterminent
   toute la suite, vers le futur comme vers le passé.
2. Pour $`q=0`$, construire à la main les suites issues de
   $`(a(-1),a(0))=(0,1)`$ puis de $`(-1,0)`$.
3. Reconnaître après coup les suites

```math
\cos\!\left(\frac{\pi t}{2}\right)
\qquad\text{et}\qquad
\sin\!\left(\frac{\pi t}{2}\right).
```

4. Montrer directement, avec les formules d’addition, que ces deux écritures
   satisfont $`a(t+1)=-a(t-1)`$ aux temps entiers.
5. Expliquer pourquoi on pourrait supprimer les mots « sinus » et « cosinus »
   et conserver seulement les listes et la récurrence, sans perdre aucune
   prédiction.
6. Résoudre de même les cas $`q=2`$ et $`q=-2`$. Identifier les possibilités
   de croissance linéaire.
7. Pour $`|q|>2`$, chercher $`a(t)=r^t`$ et expliquer l’apparition d’une
   croissance exponentielle.

## 5. Construire un pic mobile avec quatre modes immobiles

On travaille sur l’anneau $`0-1-2-3-0`$ avec $`c=1`$. On donne

```math
\begin{aligned}
\varphi_0&=(1,1,1,1),&\lambda_0&=0,\\
\varphi_\pi&=(1,-1,1,-1),&\lambda_\pi&=4,\\
\varphi_{\cos}&=(1,0,-1,0),&\lambda_{\cos}&=2,\\
\varphi_{\sin}&=(0,1,0,-1),&\lambda_{\sin}&=2.
\end{aligned}
```

1. Écrire le Laplacien de l’anneau et vérifier les quatre relations propres.
2. Calculer les quatre normes au carré.
3. Décomposer explicitement $`e_3=(0,0,0,1)`$ et
   $`e_0=(1,0,0,0)`$ sur ces quatre modes. Écrire les quatre produits
   ligne-colonne pour $`e_0`$.
4. On impose $`u(-1)=e_3`$ et $`u(0)=e_0`$. Écrire les deux coefficients
   initiaux de chaque mode.
5. Pour chaque valeur propre $`0,2,4`$, écrire la récurrence temporelle
   correspondante.
6. Calculer les coefficients aux temps $`1,2,3,4`$, puis reconstruire les
   quatre photographies $`u(1),\ldots,u(4)`$.
7. Vérifier que le pic avance d’un sommet par pas alors qu’aucun des quatre
   profils propres ne change de place.
8. Identifier après coup les quatre suites de coefficients par une constante,
   $`(-1)^t`$, un cosinus et un sinus.
9. Quel mode se trouve au seuil critique ? Pourquoi les deux snapshots choisis
   n’excitent-ils pas sa branche en $`t(-1)^t`$ ?

## 6. La largeur trois n’avait rien de fondamental

Sur la chaîne infinie avec $`c=1`$, choisir un profil quelconque $`f`$ et poser

```math
u_n(-1)=f(n+1),
\qquad
u_n(0)=f(n).
```

1. Montrer par récurrence que

```math
u_n(t)=f(n-t).
```

2. Faire le calcul complet pour le profil de largeur cinq

```math
f=(-2\mapsto1,-1\mapsto2,0\mapsto3,1\mapsto2,2\mapsto1),
```

   nul ailleurs, jusqu’à $`t=3`$.
3. La preuve utilise-t-elle la symétrie, la positivité ou la largeur de $`f`$ ?
4. Construire de même un profil se déplaçant vers la gauche.
5. Peut-on transporter exactement un pic de largeur $`1`$ ? Un profil de
   largeur $`100`$ ? Un profil qui prend des valeurs négatives ?
6. Expliquer pourquoi la localité interdit à un profil arbitraire de se
   translater rigidement de deux sommets par pas avec cette règle.

## 7. D’où vient le nombre d’onde $`k`$ ?

Sur un anneau de $`N`$ sommets, on cherche des profils réguliers de la forme
$`\cos(kn)`$ et $`\sin(kn)`$.

1. Pourquoi la fermeture de l’anneau impose-t-elle $`kN=2\pi m`$ pour un
   entier $`m`$ ?
2. Retrouver les valeurs possibles $`k=2\pi m/N`$.
3. Montrer, avec les formules d’addition, que

```math
L\cos(kn)=(2-2\cos k)\cos(kn),
```

   et établir la même relation pour le sinus.
4. Retrouver les modes $`0,\pi,\cos,\sin`$ de l’exercice 5 lorsque $`N=4`$.
5. Pourquoi les modes cosinus et sinus de nombre d’onde $`\pi/2`$ ont-ils la
   même valeur propre ? La valeur propre suffit-elle à les distinguer ?
6. Interpréter $`k`$ comme l’avancement de phase par arête, sans supposer que
   l’espace entre deux sommets existe.

## 8. Le test spectral de la fabrique

On admet qu’un profil sur l’anneau se décompose en modes sinus et cosinus.

1. Développer $`\cos(k(n-t))`$ à l’aide d’une formule d’addition.
2. Montrer qu’une onde déplacée vers la droite est produite par deux profils
   spatiaux stationnaires dont les coefficients tournent avec la fréquence
   temporelle $`\omega=k`$.
3. Pour une translation de $`s`$ sommets par pas, montrer que la condition
   devient $`\omega(k)=sk`$ pour tous les modes présents dans le profil.
4. Combiner

```math
\sin^2\!\frac{\omega}{2}=\frac{c^2\lambda}{4}
\qquad\text{et}\qquad
\lambda(k)=4\sin^2\!\frac{k}{2}
```

   pour retrouver la relation de dispersion

```math
\sin^2\!\frac{\omega(k)}2
=c^2\sin^2\!\frac{k}2.
```

5. Vérifier que $`c=1`$ permet $`\omega(k)=k`$ pour tous les $`k`$.
6. Expliquer pourquoi une relation non linéaire entre $`\omega`$ et $`k`$
   déforme en général une bosse localisée.
7. Pourquoi une bosse étroite est-elle particulièrement exigeante du point de
   vue spectral ?

## 9. Audit de la parcimonie numérique

1. Supposer que $`c^2`$, $`u(-1)`$ et $`u(0)`$ ne contiennent que des
   fractions. Montrer par récurrence que toutes les photographies calculées
   n’utilisent encore que des fractions.
2. Dans l’exercice 5, remplacer toutes les expressions trigonométriques par
   leurs listes de valeurs aux temps entiers. Perd-on une information ?
3. Sur un graphe fini, expliquer deux manières de travailler sans supposer que
   chaque sommet porte un nombre réel arbitraire : itération directe et ajout
   des seules racines algébriques nécessaires.
4. À l’aide de la formule d’Euler, vérifier

```math
A\cos(kn)+B\sin(kn)
=\frac{A-iB}{2}e^{ikn}+\frac{A+iB}{2}e^{-ikn}.
```

5. Montrer que les parties en $`i`$ s’annulent dans la somme des termes $`k`$
   et $`-k`$.
6. Que gagne-t-on avec l’exponentielle complexe ? Qu’ajoute-t-elle aux
   prédictions physiques ?
7. Distinguer soigneusement les trois affirmations : « le graphe est discret »,
   « le temps est discret » et « les valeurs du champ appartiennent à tel
   domaine numérique ».

## 10. Synthèse : qu’est-ce qui se déplace ?

Rédiger une synthèse structurée répondant aux questions suivantes :

1. En quel sens un mode propre est-il stationnaire ?
2. Comment deux photographies déterminent-elles le mouvement temporel de
   chacun de ses coefficients ?
3. Comment une somme de profils stationnaires peut-elle produire un objet
   mobile ?
4. La bosse mobile est-elle un objet fondamental de la théorie linéaire, ou une
   organisation de modes ?
5. Pourquoi cette organisation peut-elle se défaire lorsque les fréquences ne
   restent pas accordées ?
6. Quelles conclusions sont exactes dans notre modèle, et lesquelles ne sont
   encore que des analogies avec des ondes ou des particules physiques ?

La réponse devra employer correctement les mots **profil**, **mode propre**,
**amplitude**, **photographie**, **superposition**, **interférence** et
**dispersion**.
