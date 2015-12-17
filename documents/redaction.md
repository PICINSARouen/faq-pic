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

## DataTool

Ce package est très utile pour gérer vos documents. Il permet, en gros, de créer une base de données en LaTeX. Où vous devez l'utiliser ? Je l'ai utilisé dans mon PQ et dans mon PGC mais vous pouvez l'utiliser à pleins d'autres endroits. Comment ça marche ? Vous définissez vos champs dans un fichier `.tex` comme par exemple mon fichier `etudiants.tex` :
```latex
\DTLnewdb{etudiants}

\DTLnewrow{etudiants}
\DTLnewdbentry{etudiants}{Nom}{\Christophe}
\DTLnewdbentry{etudiants}{Role}{\cp}
\DTLnewdbentry{etudiants}{Engagement}{courriel du 03/09/2015}

\DTLnewrow{etudiants}
\DTLnewdbentry{etudiants}{Nom}{\Thibaud}
\DTLnewdbentry{etudiants}{Role}{\resq, \rgc, \rrs, \dev}
\DTLnewdbentry{etudiants}{Engagement}{courriel du 03/09/2015}
```

Alors oui c'est un peu verbeux mais ensuite dans votre PQ vous pouvez écrire pour pas l'oublier lors du changement de semestre :
```latex
\item[Nombre d'élèves-ingénieur de l'équipe PIC~:] \DTLrowcount{etudiants}
```

Ou plus pratique dans les tableaux de rôles qui se baladent dans le PQ et qu'il faut changer à la main :
```latex
\begin{table}[h]
	\centering
	\begin{longtable}{|p{4cm}|p{7cm}|p{3cm}|} \hline
		\rowcolor[gray]{0.85}
		Membre équipe PIC & Rôle(s) dans le projet & Signature \\\hline

		\DTLforeach*{etudiants}
		{\nom=Nom,\role=Role,\engagement=Engagement}
		{\DTLiffirstrow{}{\\\hline}\nom & \role & \engagement}\\\hline
	\end{longtable}
	\caption{Engagement}
    \label{engagement}
\end{table}
```

```latex
\begin{table}[h]
    \centering
    \begin{longtable}{|p{4cm}|p{12cm}|} \hline
        \rowcolor[gray]{0.85}
        Membre équipe PIC & Rôle(s) dans le projet \\\hline

        \DTLforeach*{etudiants}
        {\nom=Nom,\role=Role}
        {\DTLiffirstrow{}{\\\hline}\nom & \role}\\\hline
    \end{longtable}
    \caption{Répartition des rôles}
    \label{repartitionDesRoles}
\end{table}
```

Bon effectivement c'est pas non plus super efficace mais si vous êtes motivés, vous pouvez mutualiser le fichier `etudiants.tex` pour tous les documents et l'utiliser pour générer le rôle dans les tableaux des signatures (pour chaque documents avec une vérification / validation, vous devez mettre un tableau des signature avec le nom de la personne et son rôle). Ce package prend tout son sens dans le PGC où vous allez avoir pleins de tableaux illisibles qui résument des informations sur comment on gère les documents. Dans ce cas j'ai créé un fichier `documents.tex` pour que quand on en rajoute un, aucun tableau n'est oublié d'être mis à jour et toutes les informations sont là (ça vous évitera quelques FT à cause d'oublis). Pour plus d'infos, vous pouvez me contacter pour que je vous file des sources qui fonctionnent mais [la documentation](http://mirrors.concertpass.com/tex-archive/macros/latex/contrib/datatool/datatool-user.pdf) est très bien faites également (faut juste pas avoir peur des 225 pages ^^).
