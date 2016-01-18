# Plan Qualité

Le Plan Qualité est sans doute le document le plus utile de votre PIC. C'est celui qui décrit tout ce que vous devez faire et comment vous devez le faire. Il est basé sur la DGQ2 que je vous conseille de lire même si elle paraît un peu indigeste au premier abord.

## Bien rédiger le PQ

Étape numéro 1 : lire la DGQ2 ! Ah ! (oui ça fait peur ^^). Il y a une checklist qui permet de savoir quoi mettre dans le PQ.

* **La fiche projet** contient toutes les informations concernant le PIC : voir le PQ des années précédentes. Essayez de ne pas mettre la fiche des rôles à cet endroit, mettez juste une liste des étudiants participants.
* **Les engagements** c'est juste un tableau avec le nom des personnes et une référence à un courriel d'engagement au PQ (pas nécessaire de s'engager à suivre le PGC car le PQ le dit déjà)
* **WBS** je n'ai aucune idée de ce que c'est et de l'utilité du truc. Voir avec la mission qualité.
* **La gestion de projet**
    * Planning : les sprints prévus par votre client. Dites bien ouvertement que ce planning n'a pas besoin d'être à jour (ça vous évitera de faire des FFT pour mettre à jour cette partie). C'est juste le planning prévu au départ avec le client et que la plannification se fera au fur et à mesure des réunions clients.
    * Le suivi du projet : expliquer que vous allez suivre les tâches par personne avec PGPic. Si votre client est d'accord, je vous conseille de dire que vous allez suivre les tâches avec Trello à la place de PGPic (comme ça vous vous débarrassez de la partie lourde de PGPic qui est difficile à gérer). Le client est d'accord ça veut dire avoir un mail de sa part disant qu'il approuve le choix.
    * Gestion des risques (« et opportunités » ça manque dans la DGQ2 c'est une faute) : dire que vous allez identifier les risques et mettre en place des actions pour éviter qu'ils se déclenchent. Que vous allez identifier les opportunités et que vous allez mettre en place des actions pour qu'elles se déclenchent. Que vous allez rédiger un Portefeuille de risques et opportunités et des fiches de risques et opportunités avec des pilotes responsable et que vous allez les réévaluer toutes les semaines durant une réunion.
* **Réalisation du produit**
    * Communication avec le client. Le client aura accès à vos outils du genre Trello si vous voulez l'utiliser. Vous pouvez détailler ici toutes les autres méthodes de communication avec le client sur le projet. Chaque remarque du client fera l'objet d'une FFT.
    * Cycle de développement de type agile (j'imagine pour tous ?). Vous devez décider ici si vous allez faire un DSI ou pas (vu qu'il est pas obligatoire). Je vous conseille le cycle suivant pour chaque lot.
        * Réunion avec le client -> Besoins du client
        * Spécification. Mise à jour du DSE, DSI, et PTV (documents avec versions)
        * Conception. Mise à jour du DC, PTI et PTU (documents sans versions)
        * Développement. Développement des tests et du code. Mise à jour du DC, PTI et PTU en fonction de l'évolution de l'architecture. Validation des tests unitaires et d'intégration automatique (via Jenkins ou Gitlab CI).
        * Validation. Déroulement du PTV en interne.
        * Recette. Déroulement du CDR avec le client. (à décrire en détail)
        * Réunion avec le client -> Besoins du client

## Temps de travail

Votre plan qualité définir les indicateurs de votre PIC. Des chiffres à calculer toutes les semaines (ou lors des résultats de l'enquête de satisfaction de votre client par exemple) pour vérifier qu'ils sont bien en dessous ou au dessus du seuil que vous avez fixé. Dans ces indicateurs il y a un problème : le temps de travail. Si vous vous fixez un seuil de 22h par semaine par exemple, il est fort probable que vous soyez en dessous lors des semaines avec des jours fériés, des cours obligatoires ajoutés ou des forums étudiants par exemple. Il est donc conseillé d'ajouter une petite phrase du genre :

> Lors de semaines spéciales avec des évènements excusés par le département ASI (cours obligatoires, salons étudiants…), le seuil des indicateurs du temps de travail pourra être diminué du temps PIC correspondant au créneau horaire de l'évènement (en fonction de la dernière semaine classique)
