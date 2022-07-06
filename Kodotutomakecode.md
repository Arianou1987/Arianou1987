# Roguelike
## Bienvenue dans ce tutoriel ! 
Nous allons apprendre ensemble les bases pour créer un jeu Roguelike c'est-à-dire un jeu de donjon construit sur plusieurs niveaux.
## Indice
Quand l'ampoule apparait dans cette zone, elle te donne un indice sur la marche à suivre.
## Bloc au démarrage
Ce bloc est comme un bouton ``||loops:START||``. Dans ce bloc, nous allons placer tous les éléments du jeu qui s'exécuteront quand le programme démarrera.
## Choisissons un personnage joueur
Va dans l'onglet ``||sprites:Sprites||`` et place le bloc ``||sprites:définir mySprite||`` dans le bloc ``||loops:au démarrage||``
```blocks
 let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
```
## Choisissons un personnage joueur
Clique sur le carré gris au centre de la zone bleue. Tu te retrouves alors dans l'éditeur mais nous allons choisir un sprite depuis la galerie. Pour cela, clique en haut de ton écran sur "Galerie" et choisis un sprite.
```blocks
 let mySprite = sprites.create(img`
    . . . . . . f f f f . . . . . . 
    . . . . f f f 2 2 f f f . . . . 
    . . . f f f 2 2 2 2 f f f . . . 
    . . f f f e e e e e e f f f . . 
    . . f f e 2 2 2 2 2 2 e e f . . 
    . . f e 2 f f f f f f 2 e f . . 
    . . f f f f e e e e f f f f . . 
    . f f e f b f 4 4 f b f e f f . 
    . f e e 4 1 f d d f 1 4 e e f . 
    . . f e e d d d d d d e e f . . 
    . . . f e e 4 4 4 4 e e f . . . 
    . . e 4 f 2 2 2 2 2 2 f 4 e . . 
    . . 4 d f 2 2 2 2 2 2 f d 4 . . 
    . . 4 4 f 4 4 5 5 4 4 f 4 4 . . 
    . . . . . f f f f f f . . . . . 
    . . . . . f f . . f f . . . . . 
    `, SpriteKind.Player)
```
## Scène
Nous allons maintenant construire le décor. Va dans ``||scene:Scène||`` et ajoute le bloc ``||scene:Définir plan de tuile||``. Clique ensuite sur le carré gris à l'intérieur du bloc et dessine un niveau à l'aide des tuiles du style "Dungeon".
```blocks
 let mySprite = sprites.create(img`
    . . . . . . f f f f . . . . . . 
    . . . . f f f 2 2 f f f . . . . 
    . . . f f f 2 2 2 2 f f f . . . 
    . . f f f e e e e e e f f f . . 
    . . f f e 2 2 2 2 2 2 e e f . . 
    . . f e 2 f f f f f f 2 e f . . 
    . . f f f f e e e e f f f f . . 
    . f f e f b f 4 4 f b f e f f . 
    . f e e 4 1 f d d f 1 4 e e f . 
    . . f e e d d d d d d e e f . . 
    . . . f e e 4 4 4 4 e e f . . . 
    . . e 4 f 2 2 2 2 2 2 f 4 e . . 
    . . 4 d f 2 2 2 2 2 2 f d 4 . . 
    . . 4 4 f 4 4 5 5 4 4 f 4 4 . . 
    . . . . . f f f f f f . . . . . 
    . . . . . f f . . f f . . . . . 
    `, SpriteKind.Player)
 // @highlight
 tiles.setCurrentTilemap(tilemap`level1`)
```
## Contrôle
Nous allons maintenant faire bouger notre sprite. Va dans l'onglet ``||control:Contrôleur||`` et ajoute le bloc ``||control:Déplace mySprite avec les boutons +||``. Désormais nous pouvons déplacer notre sprite avec le bouton + de la console ou bien avec les flèches du clavier.
```blocks
let mySprite = sprites.create(img`
    . . . . . . f f f f . . . . . . 
    . . . . f f f 2 2 f f f . . . . 
    . . . f f f 2 2 2 2 f f f . . . 
    . . f f f e e e e e e f f f . . 
    . . f f e 2 2 2 2 2 2 e e f . . 
    . . f e 2 f f f f f f 2 e f . . 
    . . f f f f e e e e f f f f . . 
    . f f e f b f 4 4 f b f e f f . 
    . f e e 4 1 f d d f 1 4 e e f . 
    . . f e e d d d d d d e e f . . 
    . . . f e e 4 4 4 4 e e f . . . 
    . . e 4 f 2 2 2 2 2 2 f 4 e . . 
    . . 4 d f 2 2 2 2 2 2 f d 4 . . 
    . . 4 4 f 4 4 5 5 4 4 f 4 4 . . 
    . . . . . f f f f f f . . . . . 
    . . . . . f f . . f f . . . . . 
    `, SpriteKind.Player)
tiles.setCurrentTilemap(tilemap`level1`)
// @highlight
controller.moveSprite(mySprite)
```
## Suivre le Sprite
Afin que notre sprite ne sorte pas de l'écran quand nous le contrôlons, ajoute ``||scene:Caméra suit sprite||``
```blocks
let mySprite = sprites.create(img`
    . . . . . . f f f f . . . . . . 
    . . . . f f f 2 2 f f f . . . . 
    . . . f f f 2 2 2 2 f f f . . . 
    . . f f f e e e e e e f f f . . 
    . . f f e 2 2 2 2 2 2 e e f . . 
    . . f e 2 f f f f f f 2 e f . . 
    . . f f f f e e e e f f f f . . 
    . f f e f b f 4 4 f b f e f f . 
    . f e e 4 1 f d d f 1 4 e e f . 
    . . f e e d d d d d d e e f . . 
    . . . f e e 4 4 4 4 e e f . . . 
    . . e 4 f 2 2 2 2 2 2 f 4 e . . 
    . . 4 d f 2 2 2 2 2 2 f d 4 . . 
    . . 4 4 f 4 4 5 5 4 4 f 4 4 . . 
    . . . . . f f f f f f . . . . . 
    . . . . . f f . . f f . . . . . 
    `, SpriteKind.Player)
tiles.setCurrentTilemap(tilemap`level1`)
controller.moveSprite(mySprite)
// @highlight
scene.cameraFollowSprite(mySprite)
```
## Créons une entrée
Nous allons maintenant ajouter une tuile de début de jeu et y placer notre sprite au démarrage. Nous allons retourner sur le plan de tuile en cliquant dessus et ajouter un escalier depuis l'onglet "Dungeon" en x0, y2
## Créons une entrée
Ajoute maintenant le bloc ``||scene:placer mySprite sur plan de tuiles||`` et modifie la ligne à 2
```blocks
let mySprite = sprites.create(img`
    . . . . . . f f f f . . . . . . 
    . . . . f f f 2 2 f f f . . . . 
    . . . f f f 2 2 2 2 f f f . . . 
    . . f f f e e e e e e f f f . . 
    . . f f e 2 2 2 2 2 2 e e f . . 
    . . f e 2 f f f f f f 2 e f . . 
    . . f f f f e e e e f f f f . . 
    . f f e f b f 4 4 f b f e f f . 
    . f e e 4 1 f d d f 1 4 e e f . 
    . . f e e d d d d d d e e f . . 
    . . . f e e 4 4 4 4 e e f . . . 
    . . e 4 f 2 2 2 2 2 2 f 4 e . . 
    . . 4 d f 2 2 2 2 2 2 f d 4 . . 
    . . 4 4 f 4 4 5 5 4 4 f 4 4 . . 
    . . . . . f f f f f f . . . . . 
    . . . . . f f . . f f . . . . . 
    `, SpriteKind.Player)
tiles.setCurrentTilemap(tilemap`level1`)
controller.moveSprite(mySprite)
scene.cameraFollowSprite(mySprite)
// @highlight
tiles.placeOnTile(mySprite, tiles.getTileLocation(0, 2))
```
## Créons une sortie
De la même manière, nous allons placer une tuile de fin sur le plan de tuile. Veille à utiliser une tuile différente que celle de l'entrée (escalier dans l'autre sens).
## Créons une sortie
Dans ``||scene:Scènes||``, sélectionne le bloc ``||scene:Lorsque sprite de type Player chevauche à location||`` et place-le où tu veux dans la zone de programmation. Dans le menu déroulant, choisis la tuile d'escalier de sortie.
```blocks
scene.onOverlapTile(SpriteKind.Player, sprites.dungeon.stairWest, function (sprite, location) {
	
})
```
## Les murs
Tu remarques que notre joueur peut toujours aller sur les murs. Pour les rendre solides, va dans le plan de tuile, sélectionne l'icône mur qui devient rouge et passe sur les éléments qu'il faut rendre solides.
## Créons une sortie
Dans l'onglet ``||game:Jeu||``, sélectionne le bloc ``||game:Jeu terminé||`` et insère le dans cette nouvelle boucle. Modifie ensuite "perdu" en "gagné".
```blocks
scene.onOverlapTile(SpriteKind.Player, sprites.dungeon.stairWest, function (sprite, location) {
    game.over(true)
})
```
## Objets à ramasser
Nous allons créer des objets qui rapportent des points. Mais tout d'abord, afin d'en avoir plusieurs, nous allons définir leur emplacement. Va sur le plan de tuile, dans "My Tiles" et créer une tuile en cliquant sur +. Sélectionne ensuite le pot de peinture, choisis une couleur qui se rapproche très fort de ton décor et pose cette nouvelle tuile là où il y aura un objet à ramasser.
## Objets à ramasser
Dans ``||loops:Au démarrage||``, place une autre boucle ``||loops:Pour l'élément valeur de list||``. Remplace "list" par ``||scene:Tableau des emplacements de||`` et sélectionne ta tuile de couleur.
```blocks
let mySprite = sprites.create(img`
    . . . . . . f f f f . . . . . . 
    . . . . f f f 2 2 f f f . . . . 
    . . . f f f 2 2 2 2 f f f . . . 
    . . f f f e e e e e e f f f . . 
    . . f f e 2 2 2 2 2 2 e e f . . 
    . . f e 2 f f f f f f 2 e f . . 
    . . f f f f e e e e f f f f . . 
    . f f e f b f 4 4 f b f e f f . 
    . f e e 4 1 f d d f 1 4 e e f . 
    . . f e e d d d d d d e e f . . 
    . . . f e e 4 4 4 4 e e f . . . 
    . . e 4 f 2 2 2 2 2 2 f 4 e . . 
    . . 4 d f 2 2 2 2 2 2 f d 4 . . 
    . . 4 4 f 4 4 5 5 4 4 f 4 4 . . 
    . . . . . f f f f f f . . . . . 
    . . . . . f f . . f f . . . . . 
    `, SpriteKind.Player)
tiles.setCurrentTilemap(tilemap`level1`)
controller.moveSprite(mySprite)
scene.cameraFollowSprite(mySprite)
tiles.placeOnTile(mySprite, tiles.getTileLocation(0, 2))
// @highlight
for (let valeur of tiles.getTilesByType(assets.tile`myTile2`)) {

}
```
## Objets à ramasser
Dans cette nouvelle boucle, place à nouveau le bloc ``||sprites:Définir mysprite||`` et sélectionne "Food" dans le menu déroulant. Clique le carré gris et, dans la galerie, choisis un objet ou de la nourriture. Attention de modifier ta variable et d'indiquer mySprite2 dans le bloc !
```blocks
for (let valeur of tiles.getTilesByType(assets.tile`myTile2`)) {
    // @highlight
    mySprite2 = sprites.create(img`
        . . . . . . 2 2 2 2 . . . . . . 
        . . . . 2 2 3 3 3 3 2 e . . . . 
        . . . 2 3 d 1 1 d d 3 2 e . . . 
        . . 2 3 1 d 3 3 3 d d 3 e . . . 
        . 2 3 1 3 3 3 3 3 d 1 3 b e . . 
        . 2 1 d 3 3 3 3 d 3 3 1 3 b b . 
        2 3 1 d 3 3 1 1 3 3 3 1 3 4 b b 
        2 d 3 3 d 1 3 1 3 3 3 1 3 4 4 b 
        2 d 3 3 3 1 3 1 3 3 3 1 b 4 4 e 
        2 d 3 3 3 1 1 3 3 3 3 1 b 4 4 e 
        e d 3 3 3 3 d 3 3 3 d d b 4 4 e 
        e d d 3 3 3 d 3 3 3 1 3 b 4 b e 
        e 3 d 3 3 1 d d 3 d 1 b b e e . 
        . e 3 1 1 d d 1 1 1 b b e e e . 
        . . e 3 3 3 3 3 3 b e e e e . . 
        . . . e e e e e e e e e e . . . 
        `, SpriteKind.Food)
}
```
## Objets à ramasser
Ajoute, dans cette boucle, le bloc ``||scene:Placer mySprite sur plan des tuiles||``. Sélectionne le bloc valeur dans la boucle et duplique-le à la place de "Plan des tuiles". N'oublie pas de modifier mySprite en mySprite2 !
```blocks
for (let valeur of tiles.getTilesByType(assets.tile`myTile2`)) {
    mySprite2 = sprites.create(img`
        . . . . . . 2 2 2 2 . . . . . . 
        . . . . 2 2 3 3 3 3 2 e . . . . 
        . . . 2 3 d 1 1 d d 3 2 e . . . 
        . . 2 3 1 d 3 3 3 d d 3 e . . . 
        . 2 3 1 3 3 3 3 3 d 1 3 b e . . 
        . 2 1 d 3 3 3 3 d 3 3 1 3 b b . 
        2 3 1 d 3 3 1 1 3 3 3 1 3 4 b b 
        2 d 3 3 d 1 3 1 3 3 3 1 3 4 4 b 
        2 d 3 3 3 1 3 1 3 3 3 1 b 4 4 e 
        2 d 3 3 3 1 1 3 3 3 3 1 b 4 4 e 
        e d 3 3 3 3 d 3 3 3 d d b 4 4 e 
        e d d 3 3 3 d 3 3 3 1 3 b 4 b e 
        e 3 d 3 3 1 d d 3 d 1 b b e e . 
        . e 3 1 1 d d 1 1 1 b b e e e . 
        . . e 3 3 3 3 3 3 b e e e e . . 
        . . . e e e e e e e e e e . . . 
        `, SpriteKind.Food)
    // @highlight
    tiles.placeOnTile(mySprite2, valeur)
}
```
## Objets à ramasser
Notre joueur doit maintenant pouvoir interagir avec nos objets. Ajoute le bloc ``||sprites:Quand sprite de type player chevauche othersprite||`` et place-le où tu veux. Modifie le deuxième menu déroulant en "Food".
```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	
})
```
## Objets à ramasser
Dans cette nouvelle boucle, ajoute le bloc ``||sprites:Détruire mySprite||``.  Duplique "othersprite" de la boucle et remplace "mySprite" dans ce nouveau bloc. Appuie sur + pour créer un effet.
```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    // @highlight
    otherSprite.destroy(effects.spray, 500)
})
```
## Ajoutons un score
