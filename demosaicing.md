Title:      À la découverte du dématriçage
Date:       2016-11-15
Tags:       photographie
Slug:       dematricage
Category:   Photo


Après avoir pris [une photo récemment][1], je me suis rendu compte que dans une zone de l'image se trouvaient de curieux artéfacts :

![labyrinthe](maze.png)

J'ai alors cherché [à droite, à gauche][2], et il semblerait que ce soit dû au dématriçage.

## Qu'est-ce que c'est ?

Pour résumer sommairement [l'article Wikipédia][3], les pixels des capteurs de nos appareils photos sont répartis selon la matrice de Bayer. C'est-à-dire que sur une ligne on a une alternance de pixels verts et bleus, et sur la suivante verts et rouges.

Un pixel n'ayant qu'une couleur, ça fait beaucoup de manques et il faut reconstituer l'image complète pour chaque couche rouge, verte et bleue : c'est le dématriçage. Pour les photos JPEG, c'est le boîtier qui fait le travail. Quand on prend des photos en RAW c'est le logiciel de traitement de l'image qui se charge de cette tâche (Lightroom, …).

![dématriçage](/images/bayer.png)

Il existe plusieurs méthodes pour calculer la valeur des pixels manquants, chacune ayant des avantages et des inconvénients. Et manifestement une, qui sous certaines conditions, peu provoquer l'apparition de ces formes labyrinthiques.

## Comment les éviter ?

En changeant l'algorithme de dématriçage, c'est-à-dire bien souvent en changeant le logiciel avec lequel vous développez votre RAW. Pas de chance, dans mon cas j'ai essayé Photoshop, Apple Photos et DxO sans succès. Chacun d'entre eux me produisant une version différente des artéfacts, mais aucun une image correcte. 

L'autre solution est d'utiliser un programme qui permet de choisir son algorithme de dématriçage et éventuellement de le paramétrer. J'ai donc utilisé [RawTherapy][4] (logiciel libre disponible pour Windows, Linux et Mac). Après avoir ouvert l'image, il est donc possible de choisir la méthode de dématriçage (demosaicing en anglais), ici « amaze ». Il se trouve qu'aucune ne convenant parfaitement, il a fallu que je joue sur le curseur « Green equilibration ».

![algorithm selection](/images/raw-therapy-1.png)

![green cursor](/images/raw-therapy-2.png)

Et voici la comparaison avant/après :

[![compare](/images/maze-before-after.png)][5]


  [1]: https://www.flickr.com/photos/gregseth/30943721475/
  [2]: http://photo.stackexchange.com/questions/84507/strange-pattern-in-picture 
  [3]: https://fr.wikipedia.org/wiki/D%C3%A9matri%C3%A7age
  [4]: http://rawtherapee.com/
  [5]: /images/maze-before-after.png

