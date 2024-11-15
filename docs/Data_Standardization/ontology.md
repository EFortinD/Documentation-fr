---
layout: default
title: Ontology
parent: Normalisation des données
nav_order: 2
---

# Ontology
{: .no_toc }

## Table des matières
{: .no_toc .text-delta }

1. TOC
{:toc}

Pour évoluer vers un avenir de données trouvables et fédérables, les projets adoptent une couche de cadre d'ontologie qui tente essentiellement d'externaliser autant que possible le langage utilisé par un ensemble de données, lui permettant de rejoindre une communauté plus large d'ensembles de données interopérables sémantiquement. D'autres avantages en découlent : le personnel de développement de bases de données réutilise le vocabulaire structuré de tiers plutôt que de maintenir involontairement des semblances en miroir de celui-ci, par exemple. Nous commençons par une brève discussion sur ce que sont les ontologies, en quoi elles diffèrent des types plus simples de vocabulaire structuré et pourquoi certaines de leurs caractéristiques sont nécessaires pour parvenir à un avenir de données fédérées. Nous couvrons également des conseils et des ressources de formation sur la façon de localiser et de réutiliser les ontologies dans les métadonnées d'étude et les schémas de données.

La définition de « **ontologie** » dans Wikipédia évoque ses racines historiques en tant que domaine de la philosophie dédié à « l'étude de l'être dans la réalité » et explore la manière dont les choses peuvent être catégorisées et identifiées au fil du temps. Nous nous concentrons sur « **ontologie appliquée** », qui utilise la catégorisation et le travail de logique formelle en philosophie, mais se tourne vers la description des **entités matérielles** (choses), de leurs **caractéristiques** (attributs), des **processus** ou événements dans lesquels elles sont impliquées, et des **rôles, fonctions ou dispositions** qu'elles peuvent avoir. Toute cette formalité vise à parvenir à un accord commun sur la manière de catégoriser les termes scientifiques de manière systématique, une fois pour toutes - mais en reconnaissant que la science elle-même laisse place aux hypothèses, aux révisions et aux changements de paradigme, et a donc besoin des ontologies pour évoluer.

La plupart des ontologies ont été créées après le Web lui-même et, en tant que projets open source collaboratifs inter-agences, nombre d'entre elles sont encore en évolution, adoptant de nouveaux termes et abandonnant les termes archaïques, affinant leur(s) propre(s) domaine(s) de contenu et transmettant des termes à d'autres ontologies pour une curation plus ciblée, et vice versa. La complexité sociotechnique de la localisation ou de la création de ressources d'ontologie adaptées à l'objectif peut être frustrante, et nous discutons également ici des mesures de réussite.

## Avantages du format d'ontologie
Notre article sur la normalisation des données a expliqué la nécessité de types de vocabulaire structuré couvrant l'agriculture et les domaines connexes avec des fonctionnalités qui les rendent réutilisables, compatibles avec l'infrastructure et sémantiquement précis. Les ontologies, combinées à certaines bonnes pratiques de conservation, intègrent ces fonctionnalités d'une manière que d'autres formats de vocabulaire structuré ne peuvent égaler. Toutes les ontologies ne sont pas créées de la même manière, et il en existe des mortes, des incomplètes ou très mal conçues. Par conséquent, les collaborations en matière d'ontologies telles que l'OBO Foundry ont créé des [principes de conservation](https://obofoundry.org/principles/fp-000-summary.html) pour permettre la reconnaissance des ontologies de référence. Nous mentionnerons également d'autres formats de vocabulaire structurés comme le système commun d'organisation simple des connaissances [SKOS](https://en.wikipedia.org/wiki/Simple_Knowledge_Organization_System) qui, bien que logiquement et/ou sémantiquement laxistes, peuvent être utiles car ils disposent de ressources soutenues par des institutions et répondent aux besoins des index de catégories de style bibliothécaire, comme le vocabulaire des concepts, définitions et relations agricoles [AGROVOC](https://www.fao.org/agrovoc/).

Une brève note sur la terminologie de l'ontologie ci-dessous : On peut ouvrir une ontologie OWL dans un éditeur d'ontologie populaire comme [Protege](https://protege.stanford.edu/) de Stanford et voir des hiérarchies et des listes de termes à différents endroits ; passer la souris sur un terme donnera un identifiant de style purl unique pour celui-ci. Les ontologies expriment quelques types de termes : les **classes** qui sont des catégories d'objets, les **instances** qui sont des objets qui (par déclaration explicite ou par inférence raisonnée) appartiennent à une ou plusieurs catégories de classes, les propriétés d'objet qui relient les classes ou les instances, et les propriétés de données qui relient les instances (et parfois les classes) à des valeurs particulières.

Une bonne ontologie doit être :

* dans un [format OWL](https://en.wikipedia.org/wiki/Web_Ontology_Language) qui possède quelques variations de syntaxe et des pouvoirs de raisonnement logique.

* hébergée sur un référentiel public versionné tel que GitHub.

* soutenue par des curateurs bénévoles ou financés (idéalement des experts de plusieurs organisations collaboratrices) qui peuvent répondre aux demandes et requêtes des utilisateurs.

* disponible sur un ou plusieurs services de recherche d'ontologies.

Dans ce contexte, une ontologie est capable de fournir :

### URL permanentes
Chaque terme d'ontologie reçoit une URL et est attaché à un service Web qui renvoie des informations lisibles par l'homme et l'ordinateur sur le terme, telles que l'étiquette, la définition, les synonymes, les entités parent et enfant. Le purl du terme est censé exister à perpétuité ; un système de référence de termes d'obsolescence et de remplacement existe, ce qui facilite les mises à jour de la base de données face à l'évolution des ontologies.

### Termes hiérarchiques et héritage
Chaque terme apparaît dans une hiérarchie de termes du même type, qu'il s'agisse d'entités matérielles, de types de processus ou de caractéristiques de choses. Ici, nous passons plus justement à la référence d'un terme d'ontologie en tant qu'**entité** ou **classe**, car les ontologies permettent aux raisonneurs logiques de prendre en compte une description ontologique d'une entité et de déterminer à quelles classes elle correspond ou appartient dans une ontologie, par exemple un animal qui « a exactement 4 pattes » peut être classé comme un « quadripède ». On s'attend également à ce que toute sous-classe (un enfant d'une classe donnée) de « quadrupède » ait 4 pattes en raison de la puissance d'héritage des ontologies OWL. Si un raisonneur est exécuté sur une ontologie avec une classe quadrupède, et que lui ou son descendant a une instance qui n'a que 3 pattes, une erreur logique se produira. Cela met en évidence une mesure de contrôle de qualité - la cohérence logique - qui peut être obtenue au sein d'une ontologie, et également lors du raisonnement sur des ontologies fusionnées qui partagent le même ensemble de relations, et sur des ontologies + données décrites par elles.

Une organisation hiérarchique des termes permet également d'utiliser les branches d'une ontologie comme source de choix de liste de sélection pour certains attributs, équivalents aux tables de recherche que les développeurs informatiques connaissent bien.

### Relations entre les types d'entités
Naturellement, une ontologie a besoin d'un langage de relations entre les classes (appelées « propriétés d'objet ») telles que « situé dans » ou « partie de » et d'une manière de les utiliser pour exprimer des énoncés logiques, appelés axiomes, qui doivent être vrais pour qu'une entité corresponde à une classe donnée. Il existe également certaines fonctionnalités (utilisant des « propriétés de données ») pour associer des valeurs ou des plages spécifiques à des axiomes de classe (par exemple, « pi 'a la valeur' ​​"3.1415927"^^xsd:decimal).

### Définition en texte libre
Une classe doit avoir une définition en texte libre qui reflète en langage clair la logique de tous les axiomes qu'elle possède, ou si aucun axiome n'existe, aide au moins le lecteur à reconnaître ce qui est inclus ou exclu de sa catégorie d'entité. Ce style de définition est appelé la forme aristotélicienne de genre-différenciation qui fait référence à la classe parente d'une classe et continue à différencier les types d'entités auxquels elle correspond de ceux auxquels ses frères et sœurs correspondraient.

### Multilingue (également par le biais de tables de recherche de synonymes)
Tout comme un terme d'ontologie a une étiquette et une définition en texte libre, il peut également avoir des variantes linguistiques de celles-ci, ce qui lui permet d'être affiché dans plusieurs langues.

### Normes de conservation
Les termes sont expliqués au singulier et sont fournis dans une seule langue comme l'anglais, et sont en minuscules, sauf pour les parties de noms propres.

### Autorat
Le crédit est accordé aux conservateurs de termes et aux sources de définition.

## Schémas de données : vue de base de données et vue d'ontologie
Une séparation des préoccupations ...

## Formats de données sérialisées
Les données codées par Phenopacket utilisent des ontologies

## Modélisation de graphes de connaissances
Avancé ! ...

## Rôles
* Utilisateur
* Implémenteur
* Conservateur

## Formation

* Cours Force11 : [L14 Introduction à la conservation des données à l'aide d'ontologies : ensembles de données FAIR et collaboration communautaire](https://osf.io/fj38v/) rédigé dans une perspective de santé publique mais également applicable aux métadonnées d'échantillons biologiques dans d'autres domaines.

### Ressources
Il existe de nombreux endroits où trouver des vocabulaires structurés tels que des ontologies et des taxonomies comme source de termes.

- L'organisation CGIAR a publié une ressource d'ontologies communes pour l'agriculture (https://bigdata.cgiar.org/ontologies-for-agriculture/).
- [AgroPortal](https://agroportal.lirmm.fr/) est une autre source de vocabulaire de recherche agricole.
- Les ressources ci-dessus relaient un certain nombre d'ontologies des sciences de la vie [OBO Foundry](https://obofoundry.org/) liées à la recherche en agriculture, biologie, climat et écologie, comme détaillé dans la section de documentation [ontology](https://github.com/ClimateSmartAgCollab/Documentation-en/blob/main/docs/Data_Standardization/ontology.md).

*








