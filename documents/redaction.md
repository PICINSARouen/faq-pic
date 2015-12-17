# Rédaction des documents

Vous allez utiliser LaTeX. Vous allez bien en bouffer :-) Donc mieux vaut utiliser toutes les fonctionnalités à votre disposition pour gagner un maximum de temps.

## Les références

Limitez les références ! Vous savez (ou pas ^^) les tableaux que vous avez au début de tous les documents. Ce tableau que vous copiez à chaque fois que vous avez un nouveau document à rédiger. Faites-y attention, si il y en a trop ça va vous souler par la suite. Donc regardez le bien, enlevez tout, et ajoutez uniquement les documents qui sont cités dans votre texte. Ça va vous simplifier la vie pour les EC (États des Configurations)

## Les dates

À défaut de trouver quelque chose de mieux, dans beaucoup de vos documents vous allez avoir des choses du genre :
```latex
\title{Compte-rendu du 14/04/2015}
\referenceVersion{CRC_15-04-14}
```
Si vous voulez éviter les erreurs et la perte de temps, utilisé des commandes LaTeX séparée pour les jours, les mois et les années. Du genre :
```latex
\newcommand{\jour}{14}
\newcommand{\mois}{04}
\newcommand{\annee}{15}

\title{Compte-rendu du \jour/\mois/20\annee}
\referenceVersion{CRC_\annee-\mois-\jour}
```
Avec cette méthode vous avez uniquement besoin d'une seule modification dans votre document à la place de deux. Donc moins d'erreurs.

## Les acronymes

Même chose que pour le tableau de références, les acronymes c'est un tableau au début de vos documents qui est toujours copié et qui est jamais à jour. Je vous conseille l'utilisation du package `glossary` dont [la documentation](https://en.wikibooks.org/wiki/LaTeX/Glossary) est très bien faite. Et au passage, arrêtez d'utiliser les commandes LaTeX inutiles du genre `\ctftCourt` pour écrire `CTFT`. C'est plus court et plus lisible (et on sait très bien que l'acronyme CTFT ne changera jamais…). Avec le package `glossary`, vous pouvez écrire `\gls{ctft}`. LaTeX se chargera automatiquement de mettre l'acronyme, le nom complet ou les deux en fonction de si vous avez déjà utilisé l'acronyme avant. Et il vous générera un tableau des acronymes toujours à jour (les acronymes non utilisés ne sont pas affichés). Petite astuce supplémentaire, utilisez toujours les commandes `\acrshort{}` ou `\acrlong{}` dans les titres sinon la définition de l'acronyme se retrouvera dans le sommaire (c'est là où il apparaît la première fois) donc c'est pas pratique.
