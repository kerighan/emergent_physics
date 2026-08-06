# Chapitre IV — Exercices : construire et comprendre l’énergie

On considère la dynamique

```math
u(t+1)=2u(t)-u(t-1)-c^2Lu(t),
```

sur un graphe fini, simple et non orienté. L’état à la date $`t`$ est le
couple $`(u(t),u(t-1))`$.

Le but n’est pas seulement de vérifier une formule conservée. Il faut distinguer :

- une quantité **conservée** ;
- une forme quadratique **positive** ;
- une énergie **coercive**, qui contrôle effectivement la taille de l’état.

## 1. Une première conservation qui ne contrôle rien

On pose $`S(t)=\mathbf 1^T u(t)=\sum_v u_v(t)`$.

1. Montrer que $`\mathbf 1^TL=0`$.
2. En déduire $`S(t+1)-2S(t)+S(t-1)=0`$.
3. Montrer que $`P=S(t)-S(t-1)`$ est conservé.
4. Résoudre la récurrence vérifiée par $`S(t)`$.
5. Donner un exemple où $`P`$ est conservé tandis que $`|S(t)|`$ tend vers
   l’infini. Pourquoi $`P`$ ne peut-il pas jouer le rôle d’un garde-fou ?

## 2. Pourquoi une seule photographie ne suffit pas

Sur la chaîne infinie, avec $`c=1`$, prendre
$`u(-1)=u(0)=\delta_0`$.

1. Calculer $`u(1)`$ et $`u(2)`$.
2. Calculer aux trois dates la norme $`N(t)=\|u(t)\|^2`$.
3. Calculer la rugosité $`D(t)=u(t)^TLu(t)`$.
4. Vérifier que ni $`N`$ ni $`D`$ n’est conservée.
5. Expliquer conceptuellement pourquoi deux histoires ayant la même
   photographie présente peuvent avoir des énergies cinétiques différentes.

## 3. Le faux candidat continu

On définit

```math
E_0(t)=\frac12\|u(t)-u(t-1)\|^2+
       \frac{c^2}{2}u(t)^TLu(t).
```

1. Calculer $`E_0(t+1)-E_0(t)`$ en utilisant la dynamique.
2. Montrer que le résultat n’est pas identiquement nul.
3. Repérer la dissymétrie temporelle entre les deux termes de $`E_0`$.
4. Pourquoi la ressemblance de $`E_0`$ avec l’énergie de l’équation d’onde
   continue ne suffit-elle pas à garantir sa conservation en temps discret ?

## 4. Découvrir l’énergie exacte

Poser $`d_t=u(t)-u(t-1)`$. On cherche une quantité de la forme

```math
E(t)=\frac12\|d_t\|^2+\frac{c^2}{2}B(u(t),u(t-1)),
```

où $`B`$ est bilinéaire et construite à partir de $`L`$.

1. Expliquer pourquoi le choix naturel est $`B(x,y)=x^TLy`$.
2. Montrer que la symétrie de $`L`$ donne $`B(x,y)=B(y,x)`$.
3. En comparant $`E(t+1)`$ et $`E(t)`$, retrouver

```math
E(t)=\frac12\|u(t)-u(t-1)\|^2+
     \frac{c^2}{2}u(t)^TLu(t-1).
```

4. Quel rôle précis joue le décalage d’un pas entre les deux champs du terme
   potentiel ?

## 5. Preuve de conservation, sans saut de calcul

On note

```math
d_+=u(t+1)-u(t), \qquad d_-=u(t)-u(t-1).
```

1. Montrer l’identité

```math
\|d_+\|^2-\|d_-\|^2
=(u(t+1)-u(t-1))^T(u(t+1)-2u(t)+u(t-1)).
```

2. Utiliser la dynamique pour transformer le second facteur.
3. Grâce à la symétrie de $`L`$, montrer que

```math
u(t+1)^TLu(t)-u(t)^TLu(t-1)
=(u(t+1)-u(t-1))^TLu(t).
```

4. Conclure que $`E(t+1)=E(t)`$.
5. Identifier exactement l’étape qui échouerait pour un opérateur spatial non
   symétrique.

## 6. Vérification complète sur deux sommets

Prendre

```math
L=\begin{pmatrix}1&-1\\-1&1\end{pmatrix},
\qquad c=1,
\qquad u(-1)=\begin{pmatrix}1\\0\end{pmatrix},
\qquad u(0)=\begin{pmatrix}0\\1\end{pmatrix}.
```

1. Calculer $`u(1)`$ et $`u(2)`$.
2. Calculer séparément le terme cinétique et le terme potentiel aux dates
   $`t=0,1,2`$.
3. Vérifier que chacun varie, mais que leur somme reste constante.
4. Le terme potentiel est-il toujours positif ? Pourquoi cela ne contredit-il
   pas la conservation de l’énergie totale ?

## 7. Lire le terme potentiel arête par arête

Pour deux champs $`x`$ et $`y`$, montrer

```math
x^TLy=\sum_{\{v,w\}\in E}(x_v-x_w)(y_v-y_w).
```

1. Retrouver d’abord cette identité sur une seule arête.
2. L’appliquer à $`x=u(t)`$ et $`y=u(t-1)`$.
3. Interpréter un terme positif, nul ou négatif sur une arête.
4. Pourquoi $`u(t)^TLu(t-1)`$ n’est-il pas, à lui seul, une énergie
   potentielle positive ?
5. En quoi reste-t-il néanmoins le bon terme pour l’énergie exacte du schéma
   discret ?

## 8. Positivité : changer de variables

Poser

```math
s=u(t)+u(t-1), \qquad d=u(t)-u(t-1).
```

1. Exprimer $`u(t)`$ et $`u(t-1)`$ en fonction de $`s`$ et $`d`$.
2. Montrer

```math
u(t)^TLu(t-1)=\frac14(s^TLs-d^TLd).
```

3. En déduire

```math
E=\frac12d^T\left(I-\frac{c^2}{4}L\right)d
  +\frac{c^2}{8}s^TLs.
```

4. En utilisant le théorème spectral, montrer que $`E\ge0`$ si
   $`c^2\lambda_{\max}\le4`$.
5. Pourquoi l’inégalité stricte $`c^2\lambda_{\max}<4`$ donne-t-elle un
   contrôle plus fort que l’égalité ?

## 9. Conservation, positivité et stabilité ne sont pas synonymes

On travaille sur un graphe connexe.

1. Pour le mode constant $`u(t)=a(t)\mathbf1`$, montrer que
   $`a(t)=A+Bt`$ est solution. L’énergie est-elle conservée ? Le champ est-il
   borné lorsque $`B\ne0`$ ?
2. Soit $`L\varphi=\lambda_{\max}\varphi`$ et supposons
   $`c^2\lambda_{\max}=4`$. Vérifier que
   $`u(t)=t(-1)^t\varphi`$ est solution.
3. Calculer son énergie. Comment une solution non bornée peut-elle avoir une
   énergie positive et conservée ?
4. Formuler des hypothèses suffisantes pour borner le champ : traitement du
   mode constant et inégalité stricte sur les autres modes.
5. Corriger avec précision l’implication du chapitre
   « $`c^2\lambda_{\max}\le4`$ donc aucune explosion possible ».

## 10. Ce que le mot « énergie » signifie ici

Rédiger une synthèse d’une quinzaine de lignes répondant aux questions :

1. Pourquoi appelle-t-on $`E`$ une énergie plutôt qu’un simple invariant
   quadratique ?
2. Quelles propriétés sont démontrées exactement ?
3. Quelles interprétations relèvent encore de l’analogie avec la mécanique ?
4. L’homogénéité temporelle suffit-elle, à elle seule, à démontrer un théorème
   de Noether discret dans le cadre présenté ?

La réponse devra distinguer théorème, condition de stabilité et interprétation
physique.
