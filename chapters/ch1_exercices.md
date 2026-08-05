# Chapitre I — Exercices : le seul calcul qu’un nœud puisse faire

Ces exercices distinguent les faits algébriques, les interprétations et les hypothèses. On travaille avec un graphe fini, simple et non orienté, sauf indication contraire.

## 1. Construire le Laplacien

Soit la chaîne à quatre sommets $`A-B-C-D`$.

1. Écrire les matrices d’adjacence $`A`$, des degrés $`D`$, puis $`L=D-A`$.
2. Pour $`u=(2,-1,0,3)^T`$, calculer $`Lu`$ par produit matriciel et par la formule locale $`(Lu)_v=\sum_{w\sim v}(u_v-u_w)`$.
3. Vérifier que la somme des composantes de $`Lu`$ est nulle.

## 2. Ce qui est réellement imposé

À un sommet $`v`$, on cherche $`(Lu)_v=a_v u_v+\sum_{w\sim v} b_{vw}u_w`$.

1. Traduire « aucun voisin n’est privilégié » en une condition sur $`b_{vw}`$.
2. Traduire « tout champ constant est annulé » et en déduire la relation entre $`a_v`$, le degré de $`v`$ et le coefficient commun $`b`$.
3. Expliquer précisément ce qui est unique : l’opérateur est-il unique, ou seulement unique à un facteur multiplicatif près ?
4. Quelle hypothèse faudrait-il abandonner pour obtenir le Laplacien normalisé $`I-D^{-1}A`$ ?

## 3. Pic, pente et bords

Sur la chaîne précédente, considérer $`u=(0,1,2,1)`$.

1. Calculer $`Lu`$. Le sommet $`C`$ est-il détecté comme un pic ?
2. Calculer $`Lu`$ pour $`u=(0,1,2,3)`$. Comparer les sommets intérieurs et les extrémités.
3. Pourquoi une pente affine est-elle annulée par le Laplacien sur la chaîne infinie, mais pas nécessairement aux extrémités d’une chaîne finie ?

## 4. Positivité et énergie de Dirichlet

Pour un graphe quelconque, montrer $`u^T L u=\sum_{\{v,w\}\in E}(u_v-u_w)^2`$.

1. En déduire que $`L`$ est positif.
2. Si le graphe est connexe, montrer que l’énergie est nulle si et seulement si $`u`$ est constant.
3. Que devient cette conclusion si le graphe n’est pas connexe ?

## 5. Ce que le Laplacien ne permet pas de conclure

Justifier chaque réponse par un exemple ou un calcul.

1. $`(Lu)_v=0`$ signifie-t-il que $`u`$ est constant sur tout le graphe ?
2. $`(Lu)_v>0`$ signifie-t-il que $`v`$ est un maximum global ?
3. La positivité de $`u^T L u`$ suffit-elle à définir une dynamique temporelle ?

## 6. Synthèse

Rédiger une démonstration d’une dizaine de lignes répondant à la question :

> Sous quelles hypothèses le Laplacien $`L=D-A`$ est-il imposé par les informations locales disponibles à un sommet ?

Séparer les hypothèses de localité, linéarité, indistinguabilité des voisins et annulation des champs constants.
