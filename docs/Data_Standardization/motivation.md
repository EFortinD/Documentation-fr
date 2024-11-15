---
layout: default
title: Motivation
parent: Normalisation des données
nav_order: 1
---

# Motivation pour la normalisation des données
{: .no_toc }

## Table des matières
{: .no_toc .text-delta }

1. TOC
{:toc}

Bien que les ensembles de données d'un projet puissent avoir été créés et hébergés pour répondre aux besoins immédiats de ses objectifs de recherche, une attention particulière est généralement requise pour créer des produits de données standardisés afin qu'ils puissent être trouvés et réutilisés par d'autres parties prenantes (personnel universitaire, gouvernemental, industriel et autre organisme de recherche) avec un minimum d'effort. Même si les ensembles de données du projet sont enregistrés dans les catalogues de données FAIR (alias portails de recherche de données), la découverte et la réutilisation peuvent être perturbées par des métadonnées et des données non harmonisées, en particulier dans le contexte du flot d'ensembles de données expérimentales et de surveillance générés dans de nombreux domaines de recherche. Nous reconnaissons que de nombreuses interfaces de recherche de catalogues de données ne peuvent pas encore tirer parti de métadonnées d'ensembles de données plus riches, mais en attendant, ces informations sont nécessaires aux chercheurs pour déterminer manuellement la pertinence des ensembles de données.

## Détectabilité
Défis rencontrés par les chercheurs et autres consommateurs de données :

* **Catalogues de données** : pour la découverte, il faut soumettre les métadonnées d'ensembles de données du projet à des catalogues de données comme [FAIRsharing.org](https://fairsharing.org/) ou à la [recherche d'ensembles de données](https://datasetsearch.research.google.com/) de Google, mais les catalogues cibles eux-mêmes ne partagent souvent pas le même cadre général de description des données (comme Schema.org [Dataset](https://schema.org/Dataset)), ou les mêmes termes de contenu sémantique.
* **Cohérence du sac de mots-clés** : dans les catalogues de données, une description sémantique d'un ensemble de données est souvent limitée à un ensemble de mots-clés - et ces mots-clés sont souvent du texte libre riche en synonymes fourni par l'utilisateur et/ou sélectionnés dans un menu large plutôt que complet. Même lorsque le vocabulaire contrôlé est utilisé, les changements dans l'étiquetage préféré perturbent la récupération des résultats passés et présents (par exemple dans la taxonomie, « Malus pumila » contre « Malus domestica » pour faire référence au pommier).
* **Précision et rappel des résultats de recherche** : la recherche de quelques mots-clés généraux du domaine d'un ensemble de données dans un catalogue de données produira de plus en plus de résultats trop nombreux pour être passés au crible par un humain (faux positifs et non classés de manière appropriée pour faciliter un point de coupure). À l'inverse, fournir plus de mots-clés et des mots-clés plus spécifiques peut réduire de manière trop nette les ensembles de données candidats, en excluant les bons qui utilisent simplement des synonymes de mots-clés différents (faux négatifs). L'utilisation de mots-clés dans ou entre les catalogues de données est souvent incohérente et ne représente qu'une fraction des termes nécessaires pour différencier ce que sont les ensembles de données.
* **Filtres dimensionnels** : les filtres spécifiques à la conception et au protocole expérimentaux, aux données démographiques des sujets et au contexte biologique ou social sont souvent manquants, ce qui conduit à des recherches plus approfondies pour voir si des types de données spécifiques sont collectés, avec des méthodes comparables et dans un contexte comparable. Certains efforts visant à fournir des champs standard relatifs à la portée de la base de données existent (par exemple, les champs Schema.org pour [temporalCoverage](https://schema.org/temporalCoverage), [countryOfOrigin](https://schema.org/countryOfOrigin) et
[contentLocation](https://schema.org/contentLocation)).

## Réutilisation
On estime que 80 % du temps de doctorat est consacré au nettoyage et à la préparation des données pour l'analyse. Les partisans des données FAIR préconisent donc un investissement initial de 5 % du budget du projet dans la normalisation des données afin de réduire cette charge en aval ainsi que les coûts des opportunités perdues en cas d'échec de la découverte des données. [[Investir 5 % des fonds de recherche pour garantir la réutilisation des données](https://www.nature.com/articles/d41586-020-00505-7)]. Une attention particulière portée à la normalisation des données en amont encourage la réutilisation et évite les travaux coûteux ultérieurs nécessaires à la cartographie des ensembles de données peer-to-peer lorsque de nouveaux utilisateurs en aval des données du projet sont rencontrés.

* **Normalisation des données** : une fois qu'un chercheur a localisé les bases de données adaptées à ses besoins de recherche, une grande partie de son temps d'analyse est souvent consacrée à l'harmonisation préparatoire des données au niveau du terrain. La section [ontologie](https://github.com/ClimateSmartAgCollab/Documentation-en/blob/main/docs/Data_Standardization/ontology.md) présente les moyens de réduire cette charge.

Auteurs : Damion Dooley