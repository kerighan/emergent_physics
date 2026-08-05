# Chapitre II — Exercices : peut-on déplacer un objet ?

On travaille d’abord sur la chaîne infinie Z, avec $(Lu)_n=2u_n-u_{n-1}-u_{n+1}$ et $u_n(t+1)=u_n(t)-ε(Lu(t))_n$. Les champs considérés sont à support fini au départ ; cela justifie les sommes utilisées.

## 1. Le premier pas : diffusion ou translation ?

On prend $ε=1/2$ et $u_{-1}(0)=1$, $u_0(0)=2$, $u_1(0)=1$, les autres valeurs étant nulles.

1. Calculer le profil à $t=1$, puis à $t=2$.
2. Comparer la hauteur maximale et le nombre de sommets non nuls aux deux instants.
3. Le profil s’est-il déplacé, ou s’est-il étalé ? Donner un critère précis qui distingue ces deux phénomènes.

## 2. Une quantité conservée, mais pas un objet conservé

Montrer que, pour tout $ε$ et tout champ à support fini, $S(t)=Σ_{n∈Z}u_n(t)$ est constant.

1. Faire la preuve en développant les sommes, sans invoquer seulement la notation matricielle.
2. Cette conservation interdit-elle l’étalement ? Tester la question sur l’exercice 1.
3. Donner deux champs différents ayant la même somme, mais des profils très différents.

## 3. Le barycentre : ce qui reste immobile

Supposer maintenant $S(t)≠0$ et définir $X(t)=Σ_n n u_n(t)/S(t)$.

1. Montrer que $X(t+1)=X(t)$ pour la dynamique de diffusion sur Z.
2. Calculer $X(0)$ et $X(1)$ pour le profil $u_{-1}=1,u_0=2,u_1=3$.
3. Expliquer pourquoi ce résultat ne signifie pas que chaque morceau du profil reste en place.
4. Quelles hypothèses faut-il mentionner pour que la preuve soit légitime sur Z ?

## 4. Symétrie et fausse conclusion

Soit un champ initial pair : $u_{-n}(0)=u_n(0)$.

1. Montrer par récurrence que le champ reste pair à tout instant.
2. En déduire que son barycentre est nul lorsqu’il est défini.
3. Construire un champ initial non pair dont le barycentre reste pourtant constant.
4. Formuler correctement la conclusion du chapitre : que peut-on établir exactement, et que ne peut-on pas établir, à propos du mouvement ?

## 5. Propagation de l’influence

Partir de $u_0(0)=1$ et $u_n(0)=0$ pour $n≠0$, avec $ε=1/2$.

1. Calculer les profils pour $t=1,2,3$.
2. Montrer par récurrence que $u_n(t)=0$ si $|n|>t$.
3. Cette propriété est-elle une vitesse de déplacement de l’objet, une vitesse de propagation de l’influence, ou les deux ? Justifier.
4. Pourquoi le maximum du profil ne constitue-t-il pas nécessairement un objet qui se déplace ?

## 6. La mémoire comme test minimal

Considérer la règle du second ordre $u_n(t+1)=2u_n(t)-u_n(t-1)-(Lu(t))_n$.

1. Vérifier qu’un champ constant dans l’espace et dans le temps est solution.
2. Pour une fonction quelconque $f$, poser $u_n(t)=f(n-t)$. Vérifier directement que cette forme est solution sur Z.
3. Refaire le calcul pour $u_n(t)=f(n+t)$.
4. Que permet de distinguer la donnée de deux instants successifs, que la diffusion du premier ordre ne permettait pas de distinguer ?
5. Cette expérience prouve-t-elle déjà que toute dynamique du second ordre est réversible et stable ? Répondre en donnant la propriété manquante.

## 7. Bilan critique

Rédiger une réponse structurée à la question :

> Pourquoi la dynamique de diffusion conserve-t-elle une quantité globale tout en détruisant la forme locale d’une bosse ?

La réponse devra distinguer conservation de la somme, conservation du barycentre, propagation de l’influence et conservation de la forme.
