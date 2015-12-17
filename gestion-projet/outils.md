# Outils

On utilise beaucoup d'outils pour gérer le PIC (pas tous libres) pour combler [les lacunes de PGPic](https://github.com/PICINSARouen/cahier-des-charges). Pour les outils qui ne sont pas en interne, pensez à demander une approbation à votre client sous forme écrite (un mail ça ira parfaitement ^^).

## Trello

Si vous n'êtes pas en cycle en V (haha), [Trello](https://trello.com) est génial pour gérer les tâches. Vous pouvez créer des checklists pour être sûr de rien oublier dans le processus des documents. Voilà la notre :

* rédaction ;
* vérification ;
* validation ;
* mise à jour des dates (des signatures) ;
* envoi au client ;
* approbation ;
* mise à jour des dates (approbation) et suivi des diffusions ;
* modifier couleurs (enlever les couleurs lors des modifications dans le document) ;
* diffusion ;
* archivage.

## Slack

[Slack](https://slack.com) c'est une sorte d'IRC pour discuter avec les autres membres du PIC sans les déranger sur ce qu'ils font. Et aussi partager des liens et des textes.

## Google Drive

On utilise [Google Drive](https://docs.google.com/) pour le planning du PIC et pour l'organisation des revues. Petit mail à m'envoyer pour que je fasse tourner les templates qui vont bien.

## Gitlab

[Gitlab](https://about.gitlab.com/) c'est comme Github, mais en libre et en auto-hébergé. Ça permet de partager du code source sans utiliser l'immonde MonProjet. Nous vous conseillons grandement de l'installer sur votre serveur PIC en attendant qu'il y ait un outil correct pour la gestion des sources en interne.

### Gitlab CI

On utilise également Gitlab CI pour tout ce qui est *Continuous Integration*. Ça permet de lancer les tests à chaque commit d'un membre du PIC, de vérifier sur les *Pull Request* qu'il n'y a pas de problème avec les tests existants, et même de génerer et de mettre en ligne la documentation et le *code coverage*. Très pratique ! 
