# REFLEXION.md

1. `robots.txt` empêche-t-il, à lui seul, le duplicate content entre
   `/produits?tri=prix` et `/produits?tri=prix-asc` ? Pourquoi ?

   Non. `robots.txt` contrôle principalement l'exploration, pas la
   déduplication à l'indexation. Une URL bloquée peut tout de même être
   découverte et indexée si elle reçoit des liens externes, et
   `robots.txt` ne désigne pas quelle version doit être considérée comme
   l'URL de référence.

2. Pourquoi la balise canonique est-elle l'outil adapté ici, plutôt que
   `robots.txt` ou une meta `noindex` ?

   Les deux URLs affichent le même contenu et doivent donc être regroupées
   autour d'une URL préférée. La balise canonique indique explicitement aux
   moteurs de recherche que `/produits?tri=prix` est cette version de
   référence, tout en laissant les pages explorables. `robots.txt` ne sert
   pas à choisir une URL canonique, tandis que `noindex` empêcherait
   l'indexation au lieu de consolider les signaux sur la bonne URL.

3. Si demain `/admin` existe sur ce site et ne doit jamais être exploré par
   Google, quelle ligne ajoutes-tu dans `robots.txt` ?

   `Disallow: /admin`
