# Chapitre II — Exercices : Peut-on déplacer un objet ?

> **Objectif** : Comprendre pourquoi la dynamique de diffusion $u(t+1) = u(t) - \varepsilon L u(t)$ ne permet pas de déplacer un objet, et pourquoi il faut introduire de la mémoire. Tous les exercices sont conçus pour être résolus **à la main**, sauf mention contraire.

---

## series 1 : Calcul direct de la dynamique de diffusion

### Exercice 2.1 ★ (Départ)
**Premier pas de diffusion sur une chaîne**

Sur la chaîne $\mathbb{Z}$, avec $\varepsilon = \frac{1}{2}$, la règle devient $u_n(t+1) = \frac{u_{n-1}(t) + u_{n+1}(t)}{2}$.

Soit la bosse symétrique initiale :
$u_{-1}(0) = 1, u_0(0) = 2, u_1(0) = 1$, et $u_n(0) = 0$ ailleurs.

1. Calculer $u_n(1)$ pour $n = -2, -1, 0, 1, 2$.
2. Vérifier que $\sum_n u_n(1) = \sum_n u_n(0)$.
3. Où se situe le maximum à $t=1$ ? Commenter.

---

### Exercice 2.2 ★
**Conservation de la somme**

Montrer que pour **n'importe quel graphe** et **n'importe quel champ**, la dynamique
$$u_v(t+1) = u_v(t) - \varepsilon (\mathcal{L}u(t))_v$$
conserve la somme totale $S(t) = \sum_v u_v(t)$. 

**Indice** : Utiliser le fait que $\sum_v (\mathcal{L}u)_v = 0$ (somme des lignes de $L$ est nulle).

---

### Exercice 2.3 ★★
**Deux pas de diffusion**

Reprendre la bosse de l'exercice 2.1.

1. Calculer $u_n(2)$ pour $n = -2, -1, 0, 1, 2$.
2. Tracer l'évolution du maximum et de la largeur de la bosse.
3. Que devient la bosse au bout de plusieurs pas ? (Répondre qualitativement)

---

## series 2 : Le barycentre, révélateur de l'échec

### Exercice 2.4 ★★
**Calcul du barycentre sur un exemple**

Sur la chaîne, avec la bosse asymétrique :
$u_{-1}(0) = 1, u_0(0) = 2, u_1(0) = 3$, et $u_n(0) = 0$ ailleurs.

1. Calculer le barycentre $X(0) = \frac{\sum_n n u_n(0)}{\sum_n u_n(0)}$.
2. Calculer $u_n(1)$ pour $n = -1, 0, 1, 2, 3$.
3. Calculer $X(1)$ et vérifier qu'il est égal à $X(0)$.

---

### Exercice 2.5 ★★★
**Preuve générale : le barycentre est immobile**

Montrer que pour la dynamique $u_n(t+1) = \frac{u_{n-1}(t) + u_{n+1}(t)}{2}$ sur la chaîne $\mathbb{Z}$,
le barycentre $X(t) = \frac{\sum_n n u_n(t)}{\sum_n u_n(t)}$ est constant au cours du temps.

**Indice** : Montrer que $\sum_n n u_n(t+1) = \sum_n n u_n(t)$ en utilisant la formule de $u_n(t+1)$.

---

### Exercice 2.6 ★★
**Barycentre sur un graphe quelconque**

Soit un graphe quelconque et la dynamique $u(t+1) = u(t) - \varepsilon L u(t)$.

Montrer que pour **n'importe quelle fonction $f: V \to \mathbb{R}$**, on a :
$$\sum_v f(v) u_v(t+1) = \sum_v f(v) u_v(t) - \varepsilon \sum_{\{v,w\} \in E} (f(v) - f(w))(u_v(t) - u_w(t)).$$

**Cas particulier** : Si $f$ est une fonction **harmonique** (i.e., $(Lf)_v = 0$ pour tout $v$), que devient cette égalité ?

---

## series 3 : Comprendre l'échec

### Exercice 2.7 ★★
**Symétrie et impossibilité du mouvement**

Considérons une bosse symétrique sur la chaîne : $u_{-k}(0) = u_k(0)$ pour tout $k$.

1. Montrer que pour tout $t$, on a $u_{-k}(t) = u_k(t)$ (la symétrie est préservée).
2. En déduire que le barycentre reste en $0$ pour toujours.
3. *Question ouverte* : Si on brise la symétrie initiale (comme à l'exercice 2.4), peut-on espérer un mouvement ? Expliquer pourquoi la réponse est non.

---

### Exercice 2.8 ★★★
**Vitesse d'étalement de la bosse**

Sur la chaîne avec $\varepsilon = \frac{1}{2}$, soit la bosse initiale :
$u_0(0) = 1$, $u_n(0) = 0$ pour $n \neq 0$.

1. Calculer $u_n(1)$ pour $n = -1, 0, 1$.
2. Calculer $u_n(2)$ pour $n = -2, -1, 0, 1, 2$.
3. Calculer $u_n(3)$ pour $n = -3, -2, -1, 0, 1, 2, 3$.
4. Observer le pattern. Quelle est la vitesse à laquelle l'information se propage ?
5. Comparer avec un mouvement balistique (où la bosse avancerait d'un cran par pas de temps).

---

### Exercice 2.9 ★★
**Marche aléatoire vs diffusion déterministe**

Soit une marche aléatoire simple sur $\mathbb{Z}$ : à chaque pas, le marcheur va à gauche ou à droite avec probabilité $1/2$.

1. Quelle est l'espérance de la position après $t$ pas ?
2. Quelle est la variance de la position après $t$ pas ?
3. Pour la dynamique de diffusion $u_n(t+1) = \frac{u_{n-1}(t) + u_{n+1}(t)}{2}$ avec la condition initiale $u_0(0) = 1$ et $0$ ailleurs, calculer la variance de la distribution à $t=2$ (i.e., $ \sum_n n^2 u_n(2) $).
4. Comparer les comportements. Que partagent la marche aléatoire et la diffusion déterministe ?

---

## series 4 : Vers la solution — comprendre ce qu'il manque

### Exercice 2.10 ★★★
**Dynamique avec mémoire : premier essai**

Supposons qu'on utilise une dynamique du second ordre (avec mémoire) :
$$u(t+1) = 2u(t) - u(t-1) - \varepsilon^2 L u(t).$$

*Remarque* : Cette dynamique utilise $u(t)$ et $u(t-1)$.

1. Vérifier que si $u(t) = u(t-1) = c$ (champ constant), alors $u(t+1) = c$ aussi.
2. Soit une bosse qui se déplace à vitesse constante : $u_n(t) = f(n - vt)$ pour une certaine fonction $f$ et vitesse $v$.
   Montrer que si on choisit $\varepsilon = 1$ et $v = 1$, alors cette dynamique peut préserver la forme de la bosse.
   *Indice* : Calculer $u_n(t+1) - 2u_n(t) + u_n(t-1)$ pour $u_n(t) = f(n-t)$.
3. *Interprétation* : Que représente le terme $2u(t) - u(t-1)$ ?

---

### Exercice 2.11 ★★ (Optionnel - peut utiliser Python)
**Simuler l'échec sur un graphe plus grand**

Sur une chaîne de 11 nœuds indexés de $-5$ à $5$, avec la bosse initiale :
$u_{-2}(0) = 1, u_{-1}(0) = 2, u_0(0) = 3, u_1(0) = 2, u_2(0) = 1$, et $0$ ailleurs.

1. Calculer à la main (ou avec Python) $u_n(1), u_n(2), u_n(3)$.
2. Tracer l'évolution du profil.
3. Calculer le barycentre à chaque pas et vérifier qu'il reste constant.
4. *Option Python* : Écrire un script qui calcule 10 pas de temps et affiche l'évolution. Observer que la bosse s'étale sans se déplacer.

---

## Solutions attendues et conseils

- **Pour les calculs directs** (Ex 2.1, 2.3, 2.4, 2.8, 2.11) : Faire les calculs pas à pas avec soin. Une erreur courante est d'oublier que le Laplacien sur une chaîne se simplifie en $2u_n - u_{n-1} - u_{n+1}$.
- **Pour les preuves de conservation** (Ex 2.2, 2.5, 2.6) : Utiliser systématiquement la propriété $\sum_v (\mathcal{L}u)_v = 0$ et manipuler les sommes avec attention.
- **Pour l'interprétation** : Se rappeler que **sans mémoire, pas de direction**. Le barycentre est une quantité conservée qui bloque tout déplacement net.
- **Pour l'exercice 2.10** : C'est un avant-goût du chapitre suivant. La mémoire (deux instants) permet d'introduire une notion de "vitesse".

---

## Résumé des concepts clés à maîtriser après ces exercices

✅ Dynamique de diffusion : $u(t+1) = u(t) - \varepsilon L u(t)$  
✅ Conservation de la somme $\sum_v u_v(t)$  
✅ Conservation du barycentre $X(t) = \frac{\sum_v x_v u_v(t)}{\sum_v u_v(t)}$  
✅ Étalement diffusif vs mouvement balistique  
✅ Théorème d'impossibilité : sans mémoire, pas de déplacement net  
✅ Nécessité d'introduire $u(t-1)$ pour briser la symétrie temporelle  
✅ Lien entre marche aléatoire et équation de la chaleur discrète
