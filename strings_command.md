
>You can use [Google Translate](https://translate.google.com/) to read them in your preferred language.

```linux
strings nom_fichier
```

Cette méthode retourne les chaînes de caractères lorsque le système d'exploitation effectue le décodage d'un fichier, par exemple binaire. En effet, les fichiers binaires ne contiennent pas de texte lisible par l'humain. Lorsque le fichier est chargé en mémoire, le système d'exploitation traduit chaque séquence selon l'encodage par défaut. Il se peut qu'il y ait des séquences binaires correspondant à un code caractère d'un caractère donné, et donc le caractère en question sera affiché. C'est pourquoi, même si le fichier est binaire, il est fort probable que les séquences binaires le constituant correspondent à un ou plusieurs caractères connus, puisque le système d'exploitation essaie tout de même de décoder pour savoir quoi afficher par la suite.​

Donc, la commande strings récupère juste les chaînes de caractères dans l'ordre de ce que le système d'exploitation a décodé. Bien sûr, le système d'exploitation va vérifier chaque séquence pour voir si elle correspond à un code de caractère connu dans la table d'encodage, par exemple UTF-8 ou ASCII. Il saura alors afficher ce caractère. Si la séquence ne correspond pas à un code de caractère, il affichera des symboles bizarres, comme le fameux losange avec un point d'interrogation à l'intérieur.​

Exemple :
Lecture du fichier pour savoir d'abord son contenu
On essaie de lire le fichier suivant : data.txt. On voit que le système d'exploitation a pu décoder quelques séquences binaires, puisqu'elles correspondaient à des codes caractères de caractères connus. Par contre, ceux qu'il n'a pas pu déterminer, il a mis à la place : le losange.​

Donc, la commande strings vient et ignore tous les symboles bizarres (le losange) et retourne que les caractères lisibles par l'humain dans l'ordre.​

![image](https://github.com/user-attachments/assets/1e1ef68e-2862-4aaa-8391-29b802c6e014)


Application de la commande strings
On voit qu'elle extrait que les caractères et ignore les symboles bizarres (le losange) et les écrit dans l'ordre.​
![image](https://github.com/user-attachments/assets/f7a539cf-a36e-4ea8-abf2-5f2ff2b86cb5)

Puisque dans Bandit le mot de passe est précédé par plusieurs symboles =, j'ai appliqué un filtre sur ce que cette commande retourne 
