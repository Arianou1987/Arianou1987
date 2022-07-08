# Roguelike
## Bienvenue dans ce tutoriel !
Nous allons apprendre ensemble les bases pour créer un jeu Roguelike c'est-à-dire un jeu de donjon construit sur plusieurs niveaux.
## Indice
Quand l'ampoule apparait dans cette zone, elle te donne un indice sur la marche à suivre.
## Bloc au démarrage
Ce bloc est comme un bouton ``||loops:START||``. Dans ce bloc, nous allons placer tous les éléments du jeu qui s'exécuteront quand le programme démarrera.
## Choisissons un personnage joueur
Va dans l'onglet ``||sprites:Sprites||`` et place le bloc ``||variables:définir mySprite||`` dans le bloc ``||loops:au démarrage||``
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
## Créons une sortie
Dans l'onglet ``||game:Jeu||``, sélectionne le bloc ``||game:Jeu terminé||`` et insère le dans cette nouvelle boucle. Modifie ensuite "perdu" en "gagné".
```blocks
scene.onOverlapTile(SpriteKind.Player, sprites.dungeon.stairWest, function (sprite, location) {
    game.over(true)
})
```
## Les murs
Tu remarques que notre joueur peut toujours aller sur les murs. Pour les rendre solides, va dans le plan de tuile, sélectionne l'icône mur qui devient rouge et passe sur les éléments qu'il faut rendre solides.
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
Dans cette nouvelle boucle, place à nouveau le bloc ``||variables:Définir mysprite||`` et sélectionne "Food" dans le menu déroulant. Clique le carré gris et, dans la galerie, choisis un objet ou de la nourriture. Attention de modifier ta variable et d'indiquer mySprite2 dans le bloc !
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
## Animation
Rendons ces objets plus "vivants". Clique sur "Avancé", choisis le bloc ``||animation:Animer mySprite trames||`` dans l'onglet ``||animation:Animation||`` et place-le dans la boucle "Pour l'élément valeur...". Sélectionne bien "mySprite2" dans le menu déroulant.
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
    tiles.placeOnTile(mySprite2, valeur)
    // @highlight
    animation.runImageAnimation(
    mySprite2,
    [img`
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
        `],
    500,
    false
    )
}
```
## Animation
Clique maintenant sur le caré gris et va dans galerie sélectionner ton objet. Duplique la frame en cliquant sur la double page. En t'aidant de l'outil Marquee Tool, sélectionne l'image et rétrécis-la. Clique sur terminé et, dans le bloc, modifie "en boucle" de "off" à "on".
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
    tiles.placeOnTile(mySprite2, valeur)
    animation.runImageAnimation(
    mySprite2,
    [img`
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
        `,img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . 2 2 2 . . . . . . 
        . . . . . 2 2 3 3 3 2 e . . . . 
        . . . . 2 3 d 1 d d 3 2 e . . . 
        . . . 2 3 1 d 3 3 d d 3 e . . . 
        . . 2 3 1 3 3 3 3 d 1 3 b e . . 
        . . 2 1 d 3 3 3 d 3 3 1 3 b b . 
        . 2 3 1 d 3 3 1 3 3 3 1 3 4 b . 
        . 2 d 3 3 3 1 3 3 3 3 1 b 4 4 . 
        . 2 d 3 3 3 1 1 3 3 3 1 b 4 4 . 
        . e d 3 3 3 3 d 3 3 d d b 4 4 . 
        . e d d 3 3 3 d 3 3 1 3 b 4 b . 
        . e 3 d 3 3 1 d 3 d 1 b b e e . 
        . . e 3 1 1 d d 1 1 b b e e e . 
        . . . e 3 3 3 3 3 b e e e e . . 
        . . . . . . . . . . . . . . . . 
        `],
    500,
    true
    )
}
```
## Score 
Ajoutons un score chaque fois que le joueur attrape un objet. Retourne dans la boucle ``||sprites:Quand sprite de type Player chevauche||`` et ajoute le bloc ``||info:Modifier le score de 1||`` depuis l'onglet ``||info:Info||``
```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
    otherSprite.destroy(effects.spray, 500)
    // @highlight
    info.changeScoreBy(1)
})
```
## Score
Afin que le score redémarre toujours à 0 au début du jeu, ajoute ``||info:Définir score à 0||`` dans la boucle ``||loops:Au démarrage||``
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
info.setScore(0)
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
    tiles.placeOnTile(mySprite2, valeur)
    animation.runImageAnimation(
    mySprite2,
    [img`
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
        `,img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . 2 2 2 . . . . . . 
        . . . . . 2 2 3 3 3 2 e . . . . 
        . . . . 2 3 d 1 d d 3 2 e . . . 
        . . . 2 3 1 d 3 3 d d 3 e . . . 
        . . 2 3 1 3 3 3 3 d 1 3 b e . . 
        . . 2 1 d 3 3 3 d 3 3 1 3 b b . 
        . 2 3 1 d 3 3 1 3 3 3 1 3 4 b . 
        . 2 d 3 3 3 1 3 3 3 3 1 b 4 4 . 
        . 2 d 3 3 3 1 1 3 3 3 1 b 4 4 . 
        . e d 3 3 3 3 d 3 3 d d b 4 4 . 
        . e d d 3 3 3 d 3 3 1 3 b 4 b . 
        . e 3 d 3 3 1 d 3 d 1 b b e e . 
        . . e 3 1 1 d d 1 1 b b e e e . 
        . . . e 3 3 3 3 3 b e e e e . . 
        . . . . . . . . . . . . . . . . 
        `],
    500,
    true
    )
}
```
## Difficultés
Créons des projectiles afin de compliquer le parcours du joueur. Ajoute la boucle ``||game:Quand mise à jour du jeu chaque 500 ms||`` depuis l'onglet ``||game:Jeu||``.
```blocks
game.onUpdateInterval(500, function () {
	
})
```
## Projectiles
Choisis un type de projectile en insérant dans cette nouvelle boucle le bloc ``||variables:Définir mySprite||``. Clique le carré gris, choisis un objet. Sélectionne le type d'objet à "Projectile" dans le menu déroulant.
```blocks
game.onUpdateInterval(500, function () {
    // @highlight
    mySprite3 = sprites.create(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . 4 4 4 4 . . . . . . 
        . . . . 4 4 4 5 5 4 4 4 . . . . 
        . . . 3 3 3 3 4 4 4 4 4 4 . . . 
        . . 4 3 3 3 3 2 2 2 1 1 4 4 . . 
        . . 3 3 3 3 3 2 2 2 1 1 5 4 . . 
        . 4 3 3 3 3 2 2 2 2 2 5 5 4 4 . 
        . 4 3 3 3 2 2 2 4 4 4 4 5 4 4 . 
        . 4 4 3 3 2 2 4 4 4 4 4 4 4 4 . 
        . 4 2 3 3 2 2 4 4 4 4 4 4 4 4 . 
        . . 4 2 3 3 2 4 4 4 4 4 2 4 . . 
        . . 4 2 2 3 2 2 4 4 4 2 4 4 . . 
        . . . 4 2 2 2 2 2 2 2 2 4 . . . 
        . . . . 4 4 2 2 2 2 4 4 . . . . 
        . . . . . . 4 4 4 4 . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, SpriteKind.Projectile)
})
```
## Projectiles
Nous allons maintenant programmer ces projectiles afin qu'ils défilent à travers l'écran de façon aléatoire. Ajoute dans la boucle le bloc ``||sprites:Définir la vitesse||`` et inscris vx 0, vy 100. Vy = la vitesse selon y donc selon un axe vertical. N'oublie pas de sélectionner mySprite3 dans le menu déroulant. 
```blocks
let mySprite3: Sprite = null
game.onUpdateInterval(500, function () {
    mySprite3 = sprites.create(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . 4 4 4 4 . . . . . . 
        . . . . 4 4 4 5 5 4 4 4 . . . . 
        . . . 3 3 3 3 4 4 4 4 4 4 . . . 
        . . 4 3 3 3 3 2 2 2 1 1 4 4 . . 
        . . 3 3 3 3 3 2 2 2 1 1 5 4 . . 
        . 4 3 3 3 3 2 2 2 2 2 5 5 4 4 . 
        . 4 3 3 3 2 2 2 4 4 4 4 5 4 4 . 
        . 4 4 3 3 2 2 4 4 4 4 4 4 4 4 . 
        . 4 2 3 3 2 2 4 4 4 4 4 4 4 4 . 
        . . 4 2 3 3 2 4 4 4 4 4 2 4 . . 
        . . 4 2 2 3 2 2 4 4 4 2 4 4 . . 
        . . . 4 2 2 2 2 2 2 2 2 4 . . . 
        . . . . 4 4 2 2 2 2 4 4 . . . . 
        . . . . . . 4 4 4 4 . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, SpriteKind.Projectile)
    // @highlight
    mySprite3.setVelocity(0, 100)
})
```
## Projectiles
Ajoute ``||sprites:Définir la position||`` et sélectionne à nouveau mySprite3. Nous allons déterminer une position aléatoire sur l'axe des x donc horizontal. Dans l'onglet ``||math:Maths||``, prends le bloc arrondi ``||math:Choisir aléatoirement entre 0 et 10||`` et place le en x. Modifie ensuite les valeurs entre 25 et 250.
```blocks
let mySprite3: Sprite = null
game.onUpdateInterval(500, function () {
    mySprite3 = sprites.create(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . 4 4 4 4 . . . . . . 
        . . . . 4 4 4 5 5 4 4 4 . . . . 
        . . . 3 3 3 3 4 4 4 4 4 4 . . . 
        . . 4 3 3 3 3 2 2 2 1 1 4 4 . . 
        . . 3 3 3 3 3 2 2 2 1 1 5 4 . . 
        . 4 3 3 3 3 2 2 2 2 2 5 5 4 4 . 
        . 4 3 3 3 2 2 2 4 4 4 4 5 4 4 . 
        . 4 4 3 3 2 2 4 4 4 4 4 4 4 4 . 
        . 4 2 3 3 2 2 4 4 4 4 4 4 4 4 . 
        . . 4 2 3 3 2 4 4 4 4 4 2 4 . . 
        . . 4 2 2 3 2 2 4 4 4 2 4 4 . . 
        . . . 4 2 2 2 2 2 2 2 2 4 . . . 
        . . . . 4 4 2 2 2 2 4 4 . . . . 
        . . . . . . 4 4 4 4 . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, SpriteKind.Projectile)
    mySprite3.setVelocity(0, 100)
    // @highlight
    mySprite3.setPosition(randint(25, 250), 0)
})
```
## Projectiles
Ajoute ``||sprites:Définir mySprite destruction automatique||``, sélectionne mySprite3 et "Détruire les murs" - "on".
```blocks
let mySprite3: Sprite = null
game.onUpdateInterval(500, function () {
    mySprite3 = sprites.create(img`
        . . . . . . . . . . . . . . . . 
        . . . . . . 4 4 4 4 . . . . . . 
        . . . . 4 4 4 5 5 4 4 4 . . . . 
        . . . 3 3 3 3 4 4 4 4 4 4 . . . 
        . . 4 3 3 3 3 2 2 2 1 1 4 4 . . 
        . . 3 3 3 3 3 2 2 2 1 1 5 4 . . 
        . 4 3 3 3 3 2 2 2 2 2 5 5 4 4 . 
        . 4 3 3 3 2 2 2 4 4 4 4 5 4 4 . 
        . 4 4 3 3 2 2 4 4 4 4 4 4 4 4 . 
        . 4 2 3 3 2 2 4 4 4 4 4 4 4 4 . 
        . . 4 2 3 3 2 4 4 4 4 4 2 4 . . 
        . . 4 2 2 3 2 2 4 4 4 2 4 4 . . 
        . . . 4 2 2 2 2 2 2 2 2 4 . . . 
        . . . . 4 4 2 2 2 2 4 4 . . . . 
        . . . . . . 4 4 4 4 . . . . . . 
        . . . . . . . . . . . . . . . . 
        `, SpriteKind.Projectile)
    mySprite3.setVelocity(0, 100)
    mySprite3.setPosition(randint(25, 250), 0)
    // @highlight
    mySprite3.setFlag(SpriteFlag.DestroyOnWall, true)
})
```
## Projectiles
Afin de créons une interaction entre le joueur et les projectiles, ajoute la boucle ``||sprites:Quand sprite de type player chevauche othersprite||`` et modifie le deuxième menu déroulant en "Projectile".
```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Projectile, function (sprite, otherSprite) {
	
})
```
## Projectiles
Dans cette nouvelle boucle, ajoute ``||sprites:Détruire mySprite||``, clique sur le + et choisis l'effet que tu souhaites.
```blocks
let mySprite: Sprite = null
sprites.onOverlap(SpriteKind.Player, SpriteKind.Projectile, function (sprite, otherSprite) {
    // @highlight
    mySprite.destroy(effects.fire, 500)
})
```
## Vie 
Et si nous perdions une vie chaque fois qu'un projectile touche le joueur ? Ajoute le bloc ``||info:Modifier la vie de -1||`` dans notre dernière boucle.
```blocks
 sprites.onOverlap(SpriteKind.Player, SpriteKind.Projectile, function (sprite, otherSprite) {
    sprite.destroy(effects.fire, 500)
    // @highlight
    info.changeLifeBy(-1)
})
```
## Vie
Ajoute le bloc ``||info:Définir la vie à 3||`` dans la boucle ``||loops:Au démarrage||``
```blocks
let mySprite3: Sprite = null
let mySprite2: Sprite = null
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
info.setScore(0)
// @highlight
info.setLife(3)
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
    tiles.placeOnTile(mySprite2, valeur)
    animation.runImageAnimation(
    mySprite2,
    [img`
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
        `,img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . 2 2 2 . . . . . . 
        . . . . . 2 2 3 3 3 2 e . . . . 
        . . . . 2 3 d 1 d d 3 2 e . . . 
        . . . 2 3 1 d 3 3 d d 3 e . . . 
        . . 2 3 1 3 3 3 3 d 1 3 b e . . 
        . . 2 1 d 3 3 3 d 3 3 1 3 b b . 
        . 2 3 1 d 3 3 1 3 3 3 1 3 4 b . 
        . 2 d 3 3 3 1 3 3 3 3 1 b 4 4 . 
        . 2 d 3 3 3 1 1 3 3 3 1 b 4 4 . 
        . e d 3 3 3 3 d 3 3 d d b 4 4 . 
        . e d d 3 3 3 d 3 3 1 3 b 4 b . 
        . e 3 d 3 3 1 d 3 d 1 b b e e . 
        . . e 3 1 1 d d 1 1 b b e e e . 
        . . . e 3 3 3 3 3 b e e e e . . 
        . . . . . . . . . . . . . . . . 
        `],
    500,
    true
    )
}
```
## Vie
Ajoute la boucle ``||info:Quand la vie est à zéro||`` et insère le bloc ``||game:Jeu terminé perdu||``.
```blocks
info.onLifeZero(function () {
    game.over(false)
})
```
## Ajoutons un niveau
Pour créer des niveaux, il faut créer une fonction et une variable. Va dans "Avancé", dans l'onglet ``||functions:Fonctions||`` et crée une fonction que tu nommes "NouveauNiveau". Clique sur "Terminé" et place ta boucle.
```blocks
function NouveauNiveau () {
	
}
```
## Ajoutons un niveau
Créons maintenant la variable de niveau. Va dans l'onglet ``||variables:Variables||`` et créer une variable intitulée "NuméroNiveau".
## Ajoutons un niveau
Depuis l'onglet ``||variables:Variables||``, ajoute le bloc ``||variables:Définir NuméroNiveau||`` dans ``||loops:Au démarrage||`` et modifie le nombre en 1.
```blocks
let mySprite3: Sprite = null
let mySprite2: Sprite = null
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
info.setScore(0)
info.setLife(3)
// @highlight
let NuméroNiveau = 1
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
    tiles.placeOnTile(mySprite2, valeur)
    animation.runImageAnimation(
    mySprite2,
    [img`
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
        `,img`
        . . . . . . . . . . . . . . . . 
        . . . . . . . 2 2 2 . . . . . . 
        . . . . . 2 2 3 3 3 2 e . . . . 
        . . . . 2 3 d 1 d d 3 2 e . . . 
        . . . 2 3 1 d 3 3 d d 3 e . . . 
        . . 2 3 1 3 3 3 3 d 1 3 b e . . 
        . . 2 1 d 3 3 3 d 3 3 1 3 b b . 
        . 2 3 1 d 3 3 1 3 3 3 1 3 4 b . 
        . 2 d 3 3 3 1 3 3 3 3 1 b 4 4 . 
        . 2 d 3 3 3 1 1 3 3 3 1 b 4 4 . 
        . e d 3 3 3 3 d 3 3 d d b 4 4 . 
        . e d d 3 3 3 d 3 3 1 3 b 4 b . 
        . e 3 d 3 3 1 d 3 d 1 b b e e . 
        . . e 3 1 1 d d 1 1 b b e e e . 
        . . . e 3 3 3 3 3 b e e e e . . 
        . . . . . . . . . . . . . . . . 
        `],
    500,
    true
    )
}
```
## Niveaux
