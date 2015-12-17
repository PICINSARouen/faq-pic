# État des configurations

Un état des configurations c'est un document qui donne toutes les infos sur ce que vous livrez (nom des documents, documents en références et versions). Vous devez le faire **À CHAQUE FOIS** que vous livrez quelque chose (majoritairement pour le client et pour l'inspection technique).

Un EC c'est un tableau des documents que vous livrez (pour une livraison au client : les documents de spécification, le code source, l'éventuelle procédure d'installation, etc.), puis un tableau avec toutes les références des documents que vous livrez (ce deuxième tableau est juste là pour la déco, vous ne livrez pas les documents qui sont listés ici), puis un tableau avec toutes les références des documents qui sont en référence des documents que vous livrez (même chose, vous livrez pas ces documents), etc. C'est long à faire… Ah et vous ne mettez pas plusieurs fois le même document si il change de version (parce que sinon ça peut remonter jusqu'au début du PIC avec les différentes versions qui s'appellent en référence).

## Tableau des références

Je l'ai déjà dit dans [la partie rédaction](redaction.md#les-références) mais essayez de limiter les tableaux de référence aux documents réellement utiles car vous allez devoir tous les lister dans votre EC, et que je l'ai déjà dit mais… Qu'est-ce que c'est long !

## Version

Lorsque vous livrez du code, pensez à mettre une version (habituellement c'est un tag Git, mais si vous avez pas encore tagué votre projet, vous pouvez simplement mettre un numéro du commit). Pensez-y pour les inspections techniques :-)

## Inspections techniques

Pour une livraison client, c'est pas trop dur de savoir ce qu'il faut livrer. Pour une inspection technique c'est différent. Vous devez livrer… Tout :-)

* Les documents qualité : PQ et PGC.
* Les documents de spécification : DSE, DSI et PTV.
* Les documents de conception : DCP et DCD.
* Le code avec une version (tag ou commit).

Pensez bien à livrer également tous les documents nécessaires à la compréhension des documents livrés. Ça casse un peu la règle de « je ne livre pas les documents en référence », mais il faut également mettre (dans le premier tableau du coup).

* Les comptes-rendus en référence (par exemple dans votre DSE vous référencez un compte-rendu avec le client où il vous explique ce qui doit être fait).
* Les documents techniques (si vous en avez en référence).
