# Chapitre I — Exercices : Le seul calcul qu'un nœud puisse faire

> **Objectif** : Maîtriser la construction du Laplacien, ses propriétés fondamentales, et son interprétation comme mesure locale de courbure discrète. Tous les exercices sont conçus pour être résolus **à la main**, avec au plus un exercice optionnel nécessitant un calcul numérique simple.

---

## series 1 : Construction et calcul direct

### Exercice 1.1 ★ (Départ)
**Graphe à deux nœuds**

Soit un graphe $G$ avec deux nœuds $A$ et $B$ connectés par une arête ($A \sim B$).

1. Écrire la matrice d'adjacence $A$ et la matrice des degrés $D$.
2. Calculer le Laplacien $L = D - A$.
3. Soit un champ $u = (u_A, u_B) = (3, 5)$. Calculer $(\mathcal{L}u)_A$ et $(\mathcal{L}u)_B$ directement à partir de la formule locale $\sum_{w\sim v} (u_v - u_w)$.
4. Vérifier que le résultat correspond à $L \cdot u$.

---

### Exercice 1.2 ★
**Chaîne à trois nœuds**

Soit une chaîne linéaire $A \— B \— C$ (3 nœuds en ligne, $A$ et $C$ ont degré 1, $B$ a degré 2).

1. Écrire $D$ et $A$ pour ce graphe.
2. Calculer $L = D - A$.
3. Pour le champ $u = (1, 0, -1)$ (valeurs sur $A, B, C$), calculer $(\mathcal{L}u)_v$ pour chaque nœud.
4. Que vaut $(\mathcal{L}u)_A + (\mathcal{L}u)_B + (\mathcal{L}u)_C$ ? Commenter.

---

### Exercice 1.3 ★★
**Invariance par translation**

Sur le même graphe en chaîne $A \— B \— C$, considérer les deux champs :
- $u = (2, 2, 2)$ (champ constant)
- $v = (2, 5, 2)$ (pic en $B$)

1. Calculer $(\mathcal{L}u)_v$ pour chaque nœud. Que constate-t-on ?
2. Calculer $(\mathcal{L}v)_v$ pour chaque nœud. Interpréter le signe et la valeur.
3. Proposer un champ $w$ tel que $(\mathcal{L}w)_B = 0$ mais $(\mathcal{L}w)_A \neq 0$.

---

## series 2 : Propriétés structurelles

### Exercice 1.4 ★★
**Preuve de l'invariance des champs constants**

Soit un graphe quelconque $G = (V, E)$. Montrer rigoureusement que pour tout champ constant $u_v = c$ (pour tout $v \in V$), on a $(\mathcal{L}u)_v = 0$ pour tout $v$.

**Indice** : Utiliser la formule locale $(\mathcal{L}u)_v = \sum_{w\sim v} (u_v - u_w)$ et simplifier.

---

### Exercice 1.5 ★★
**Énergie de Dirichlet sur un triangle**

Soit un graphe triangle (3 nœuds tous connectés entre eux : $A \sim B \sim C \sim A$).

1. Calculer le Laplacien $L$ (matrice 3×3).
2. Pour le champ $u = (1, 0, 0)$, calculer l'énergie de Dirichlet $u^T L u$.
3. Calculer aussi $\sum_{\{v,w\} \in E} (u_v - u_w)^2$ et vérifier l'égalité avec $u^T L u$.
4. Que vaut l'énergie pour un champ constant ?

---

### Exercice 1.6 ★★★
**Démonstration de la formule de l'énergie**

Montrer que pour **n'importe quel graphe** et **n'importe quel champ** $u$, on a :

$$u^T L u = \sum_{\{v,w\} \in E} (u_v - u_w)^2.$$

**Indice** :
- Partir de $u^T L u = \sum_v u_v (\mathcal{L}u)_v = \sum_v u_v \sum_{w\sim v} (u_v - u_w)$.
- Réorganiser la double somme en sommant d'abord sur les arêtes.
- Remarquer que chaque arête $\{v, w\}$ apparaît deux fois dans la somme originale.

---

## series 3 : Interprétation géométrique

### Exercice 1.7 ★★
**Champ affine sur une chaîne**

Sur une chaîne infinie $\mathbb{Z}$ (chaque nœud $n$ a pour voisins $n-1$ et $n+1$), soit le champ affine $u_n = 2n + 3$.

1. Calculer $(\mathcal{L}u)_n$ pour un $n$ intérieur (pas de bord).
2. Que vaut ce résultat ? Que mesure donc le Laplacien sur une chaîne : la pente ou la courbure ?
3. *Variante* : Soit $u_n = n^2$. Calculer $(\mathcal{L}u)_n$. Que constate-t-on ?

---

### Exercice 1.8 ★★
**Comparaison pic vs pente**

Sur une chaîne de 5 nœuds $1 \— 2 \— 3 \— 4 \— 5$ :

1. Construire un champ $u$ qui a un **pic** en 3 (valeur maximale) et des valeurs décroissantes de part et d'autre. Calculer $(\mathcal{L}u)_3$.
2. Construire un champ $v$ qui est **linéaire** (pente constante) sur toute la chaîne. Calculer $(\mathcal{L}v)_v$ pour chaque nœud intérieur.
3. Comparer les résultats : que détecte le Laplacien dans chaque cas ?

---

### Exercice 1.9 ★★★
**Symétrie du Laplacien**

Montrer que la matrice $L = D - A$ est symétrique pour **tout graphe non orienté**.

**Indice** : Rappeler que pour un graphe non orienté, $A_{vw} = A_{wv}$ et que $D$ est diagonale.

---

## series 4 : Approfondissement (optionnel Python)

### Exercice 1.10 ★★★ (Optionnel - peut utiliser Python)
**Laplacien d'un graphe étoile**

Soit un graphe étoile : un nœud central $C$ connecté à 4 nœuds périphériques $P_1, P_2, P_3, P_4$ (pas d'arêtes entre les $P_i$).

1. Écrire la matrice $L$ (5×5).
2. Soit le champ $u$ défini par $u_C = 1$ et $u_{P_i} = 0$ pour tout $i$. Calculer $(\mathcal{L}u)_v$ pour chaque nœud.
3. *Optionnel* : Avec Python (ou à la main), calculer les valeurs propres de $L$. Que remarque-t-on ?

---

## Solutions attendues et conseils

- **Pour les calculs directs** (Ex 1.1-1.3, 1.5, 1.7-1.8) : Toujours vérifier la cohérence entre la formule locale et la formule matricielle. Une erreur courante est d'oublier que le degré apparaît dans la formule diagonale.
- **Pour les preuves** (Ex 1.4, 1.6, 1.9) : Partir des définitions et manipuler les sommes avec soin. L'astuce est souvent de changer l'ordre de sommation.
- **Pour l'interprétation** : Se rappeler que le Laplacien mesure **l'écart à la moyenne locale**. Un résultat nul signifie que le point est « en équilibre » avec son voisinage.

---

## Résumé des concepts clés à maîtriser après ces exercices

✅ Construction du Laplacien à partir de $D$ et $A$  
✅ Formule locale $(\mathcal{L}u)_v = \sum_{w\sim v} (u_v - u_w)$  
✅ Invariance des champs constants ($L\mathbf{1} = 0$)  
✅ Symétrie et positivité de $L$  
✅ Énergie de Dirichlet et son interprétation  
✅ Laplacien comme détecteur de courbure discrète  
✅ Calcul manuel sur des petits graphes
