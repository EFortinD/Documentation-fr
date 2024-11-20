---
layout: default
title: Ontology
parent: Data Standardisation
nav_order: 3
---

# Ontology
{: .no_toc }

## Table des matières
{: .no_toc .text-delta }

1. TOC
{:toc}

Pour évoluer vers un avenir de données trouvables et fédérables, les projets adoptent une couche de cadre d'ontologie qui tente essentiellement d'externaliser autant que possible le langage utilisé par un ensemble de données, lui permettant de rejoindre une communauté plus large d'ensembles de données interopérables sémantiquement. D'autres avantages en découlent : le personnel de développement de bases de données réutilise le vocabulaire structuré de tiers plutôt que de conserver involontairement des semblants de celui-ci, par exemple. Nous commençons par une brève discussion sur ce que sont les ontologies, en quoi elles diffèrent des types de vocabulaire structuré plus simples et pourquoi certaines de leurs caractéristiques sont nécessaires pour parvenir à un avenir de données fédérées. Nous couvrons également des conseils et des ressources de formation sur la façon de localiser et de réutiliser les ontologies dans les métadonnées d'étude et les schémas de données.

La définition de « **ontologie** » dans Wikipédia évoque ses racines historiques en tant que domaine de la philosophie dédié à « l'étude de l'être dans la réalité » et explore la manière dont les choses peuvent être catégorisées et identifiées au fil du temps. Nous nous concentrons sur « **ontologie appliquée** », qui utilise la catégorisation et le travail de logique formelle en philosophie, mais se tourne vers la description des **entités matérielles** (choses), de leurs **caractéristiques** (attributs), des **processus** ou événements dans lesquels elles sont impliquées, et des **rôles, fonctions ou dispositions** qu'elles peuvent avoir. Toute cette formalité vise à parvenir à un accord commun sur la manière de catégoriser les termes scientifiques de manière systématique, une fois pour toutes - mais en reconnaissant que la science elle-même laisse place aux hypothèses, aux révisions et aux changements de paradigme, et a donc besoin des ontologies pour évoluer.

La plupart des ontologies ont été créées après le Web lui-même et, en tant que projets open source collaboratifs inter-agences, beaucoup d'entre elles sont encore en évolution, adoptant de nouveaux termes et dépréciant les termes archaïques, affinant leur(s) propre(s) domaine(s) de contenu et transmettant des termes à d'autres ontologies pour une conservation plus ciblée, et vice versa. La complexité sociotechnique de la localisation ou de la création de ressources d'ontologie adaptées peut être frustrante, et nous discutons des stratégies pour réussir à les choisir et à les utiliser.

## Rôles des utilisateurs d'ontologie
Les gens utilisent les ontologies de différentes manières, et heureusement, la plupart des gens n'ont pas besoin de connaître la complexité de la création ou de la maintenance d'une ontologie.

* **Utilisateur** : les utilisateurs peuvent même ne pas savoir qu'ils utilisent une terminologie basée sur l'ontologie, car dans les interfaces utilisateur, les identifiants des termes d'ontologie sont généralement cachés. Pour les utilisateurs chercheurs, ils ont probablement intérêt à connaître certaines ontologies préférées pertinentes pour leur discipline, pour les utiliser comme matériel de référence, et pour comprendre dans quelle mesure la terminologie de leur discipline est couverte sémantiquement. Les utilisateurs experts peuvent contribuer à la boucle de rétroaction sur les nouvelles demandes de termes ou les révisions.

* **Implémentateur** : programmeur ou développeur chargé de réutiliser des ontologies existantes dans certaines applications, notamment des bases de données. Cette personne devra généralement savoir comment juger de la qualité d'une ontologie, contribuer aux recommandations d'une agence pour l'utilisation de l'ontologie et être capable d'utiliser des scripts pour récupérer et actualiser des termes ou des branches d'ontologie à partir de référentiels distants pour les utiliser dans des applications. Ils devront au moins connaître les différents types de termes d'ontologie (classe, instance, entité matérielle, processus, relation, etc.)

* **Curateur** : un conservateur d'ontologie doit connaître des parties de ses classes et relations d'ontologie, ainsi que le processus de conservation pour gérer les nouvelles demandes de termes et le système de construction pour développer de nouvelles versions. Étant donné que les ontologies sont souvent des normes en évolution de facto, les conservateurs doivent aspirer à ce niveau de contrôle qualité.

## Avantages du format d'ontologie
Notre article sur la normalisation des données a expliqué la nécessité de types de vocabulaire structuré couvrant l'agriculture et les domaines connexes avec des fonctionnalités qui les rendent réutilisables, compatibles avec l'infrastructure et sémantiquement précis. Les ontologies, combinées à certaines bonnes pratiques de conservation, ont ces fonctionnalités intégrées d'une manière que d'autres formats de vocabulaire structuré ne peuvent égaler. Toutes les ontologies ne sont pas créées égales, et il en existe des mortes, des incomplètes ou très mal conçues. Par conséquent, les collaborations d'ontologies telles que l'OBO Foundry ont créé des [principes de conservation](https://obofoundry.org/principles/fp-000-summary.html) pour permettre la reconnaissance et le développement d'ontologies de référence.

Il existe d'autres formats de vocabulaire structurés populaires comme le système commun d'organisation simple des connaissances [SKOS](https://en.wikipedia.org/wiki/Simple_Knowledge_Organization_System) qui, bien que logiquement et/ou sémantiquement laxistes par rapport à l'ontologie, peuvent être utiles car ils disposent de ressources soutenues par des institutions et répondent aux besoins de navigation dans les catalogues de style bibliothécaire scientifique des catégories, comme le vocabulaire [AGROVOC](https://www.fao.org/agrovoc/) des concepts agricoles.

Un bref aperçu de la terminologie de l'ontologie détaillée ci-dessous : On peut ouvrir une ontologie OWL dans un éditeur d'ontologie populaire comme [Protege](https://protege.stanford.edu/) de Stanford et voir des hiérarchies et des listes de termes à différents endroits ; passer la souris sur un terme donnera un identifiant PUL unique pour celui-ci. Les ontologies expriment quelques types de terme/entité : une « **classe** » est une catégorie de chose, et une « **instance** » est une chose qui (par déclaration explicite ou par inférence raisonnée) appartient à une ou plusieurs catégories de classe. Deux types de relations sont proposés, à savoir une relation « **propriété d'objet** » comme « partie de » qui relie des classes ou des instances, et une « **propriété de données** » comme « a une valeur » qui relie une instance à une valeur particulière.

Une bonne ontologie doit être :

* dans un [format OWL](https://en.wikipedia.org/wiki/Web_Ontology_Language). OWL a quelques [variations de syntaxe](https://oboacademy.github.io/obook/explanation/owl-format-variants/). (Il a également quelques « profils » de puissance de raisonnement logique en fonction des types d'expressions logiques autorisées dans une ontologie).

* hébergé sur un référentiel public versionné tel que GitHub.

* avoir un système de construction qui assemble les différentes parties d'une ontologie en plus d'appliquer des contrôles de qualité pour garantir que les modifications n'ont pas créé de contradictions ou d'autres conséquences imprévues. (Le [kit de développement d'ontologie](https://github.com/INCATools/ontology-development-kit) est l'un de ces outils.)
* soutenu par des conservateurs bénévoles ou financés (idéalement des experts de plusieurs organisations collaboratrices) qui peuvent répondre aux demandes et requêtes des utilisateurs.

* disponible sur un ou plusieurs services de recherche d'ontologie.
* lister les synonymes de termes, pour résoudre le problème des personnes qui ne peuvent pas [localiser](https://oboacademy.github.io/obook/explanation/intro-to-ontologies/#we-cant-find-what-were-looking-for) un bon terme à utiliser simplement parce qu'elles utilisent un synonyme pour effectuer une recherche.

* utiliser un ensemble partagé de relations et de catégories de termes avec d'autres ontologies pour faciliter l'interopérabilité et la fédération de données. Ce n'est actuellement pas si facile à atteindre dans la mesure où il existe de nombreuses ontologies autonomes, et il faut généralement se conformer à une [ontologie de niveau supérieur](https://en.wikipedia.org/wiki/Upper_ontology) pour voir une telle congruence, et il en existe également une poignée parmi lesquelles choisir.

Pour soutenir leurs propres projets, les organismes de recherche ou autres peuvent également avoir leurs propres ontologies privées et/ou des versions miroir d'ontologies accessibles au public ; cela permet un contrôle des versions et une fiabilité face aux perturbations d'Internet.

Dans ce contexte, une ontologie est capable de fournir :

### URL permanentes
Chaque terme d'ontologie reçoit une URL et est attaché à un service Web qui renvoie des informations lisibles par l'homme et l'ordinateur sur le terme, telles que l'étiquette, la définition, les synonymes, les entités parent et enfant. Le purl du terme est censé exister à perpétuité ; un système de référence de termes d'obsolescence et de remplacement existe, ce qui facilite les mises à jour de la base de données face à l'évolution des ontologies.

### Termes hiérarchiques, héritage et raisonnement
Chaque terme apparaît dans une hiérarchie de termes du même type, qu'il s'agisse d'entités matérielles, de types de processus ou de caractéristiques de choses. Ici, nous passons plus justement à la référence d'un terme d'ontologie en tant qu'**entité** ou **classe**, car les ontologies permettent aux raisonneurs logiques de prendre en compte une description ontologique d'une entité et de déterminer à quelles classes (catégories) elle correspond ou appartient dans une ontologie, par exemple un animal qui « a exactement 4 pattes » peut être catégorisé comme membre d'une classe « quadripède ». On s'attend également à ce que toute sous-classe (un enfant d'une classe donnée) de « quadrupède » ait 4 pattes en raison de la puissance d'héritage des ontologies OWL. Si un raisonneur est exécuté sur une ontologie avec une classe quadrupède, et que lui ou son descendant a une instance qui n'a que 3 pattes, une erreur logique en résultera. Cela met en évidence une mesure de contrôle de qualité - la cohérence logique - qui peut être obtenue au sein d'une ontologie, et également lors du raisonnement « sur » des ontologies fusionnées qui partagent le même ensemble de relations, et sur des ontologies + données décrites par elles.

Notez qu'un terme peut avoir plus d'un parent dans une ontologie, et si cela se produit, on parle d'ontologie [polyhiérarchique](https://oboacademy.github.io/obook/explanation/intro-to-ontologies/#polyhierarchy). La conception d'une ontologie simple à un seul parent est encouragée pour identifier le parent « principal » ou essentiel de chaque classe, mais le raisonnement peut produire une ontologie polyhiérarchique en raison des autres classes qu'une classe subordonnée peut avoir.

Une organisation hiérarchique des termes permet également d'utiliser les branches d'une ontologie comme source de choix de listes de sélection pour certains attributs, de manière similaire aux tables de recherche de termes que connaissent bien les développeurs informatiques.

### Relations entre les types d'entités
Une ontologie a besoin d'un langage de relations entre les classes (appelées « **propriétés d'objet** ») telles que « situé dans » ou « partie de » et d'une manière de les utiliser pour exprimer des énoncés logiques, appelés axiomes, qui doivent être vrais pour qu'une entité corresponde à une classe donnée. Il existe également certaines fonctionnalités (utilisant « **propriétés de données** ») permettant d'associer des valeurs ou des plages spécifiques à des axiomes de classe (par exemple, « pi 'a la valeur' ​​"3.1415927"^^xsd:decimal).

### Normes de curation
Il existe un certain nombre de communautés de curation d'ontologies, souvent basées sur une ontologie de niveau supérieur telle que [BFO](https://basic-formal-ontology.org/) ou [UFO](https://philarchive.org/rec/PORUUF), chacune avec ses propres pratiques. La communauté OBO Foundry propose un ensemble de [meilleures pratiques](https://obofoundry.org/principles/fp-000-summary.html), par exemple que les termes sont expliqués au singulier, ont des étiquettes fournies dans une langue principale comme l'anglais, sont en minuscules sauf pour les parties de noms propres, n'ont pas de traits de soulignement et ont des caractères numériques purl afin que le réétiquetage puisse se produire sans impacter les références de base de données. Le singulier Cette exigence permet aux conservateurs (ou aux ordinateurs) de façonner des termes pluriels et leurs caractéristiques en référence à des termes singuliers.

### Définition textuelle
Une classe doit avoir une définition textuelle qui reflète en langage clair la logique de tous les axiomes importants qu'elle possède, ou si aucun axiome de ce type n'existe, aide au moins le lecteur à reconnaître ce qui est inclus ou exclu de sa catégorie d'entité. Ce style de définition est appelé la forme aristotélicienne de genre-différenciation qui fait référence à la classe parente d'une classe et continue à différencier les types d'entités auxquelles elle correspond de ceux auxquels ses frères et sœurs correspondraient. OBO Foundry propose plus de conseils sur les [définitions](https://obofoundry.org/principles/fp-006-textual-definitions.html).

### Synonymes et étiquettes multilingues
Tout comme un terme d'ontologie a une étiquette et une définition textuelle, il peut également avoir des synonymes et des variantes linguistiques de ceux-ci, améliorant ainsi sa facilité de recherche dans les moteurs de recherche en texte libre et lui permettant d'être affiché dans plusieurs langues.

### Contenu importé depuis d'autres ontologies
Alors qu'une « **ontologie de référence** » peut fournir une hiérarchie complète de termes pour un domaine restreint, une **ontologie plus orientée vers les applications** aura souvent des termes importés depuis d'autres ontologies, par exemple une ontologie alimentaire aura des termes d'anatomie et de taxonomie inclus pour décrire des parties de plantes et d'animaux. C'est ce que l'on appelle le principe [MIREOT](https://www.nature.com/articles/npre.2009.3576.1).

Il est très important lors de l'importation de termes depuis d'autres ontologies de les conserver dans un fichier séparé de l'ontologie qui les importe, afin de faciliter l'actualisation des importations qui sont susceptibles de changer au fil des mois. Il est également important d'importer uniquement les termes tiers nécessaires, plutôt qu'une ontologie entière, sinon les conservateurs peuvent se perdre au fil du temps quant aux termes qui sont importants pour la maintenance et ceux qui ne le sont pas. Il existe quelques systèmes qui permettent de récupérer des parties sélectionnées d'autres ontologies, comme [OntoFox](https://ontofox.hegroup.org/) et la commande [robot](https://github.com/ontodev/robot).

### Autorat
Les crédits des contributeurs sont fournis pour les curateurs de termes et les sources de définition, idéalement par l'identifiant [ORCID](https://orcid.org/) et le purl, respectivement.

## Schémas de données et ontologies
Un travail de normalisation important peut être effectué sur un schéma de données avant d'y introduire des identifiants d'ontologie. Le schéma est l'arbre pratique sur lequel pendent les purl d'ontologie, et ces purl fournissent ensuite les fruits comparables de l'interopérabilité. La séparation des tâches principales d'un schéma de données (organiser les attributs dans des tables ou des objets, fournir du texte brut, coder les noms et les types de données des attributs) et son rôle dans l'interopérabilité des données FAIR, en mappant les identifiants d'ontologie ou de vocabulaire structuré à ces attributs, permet de réaliser séparément le travail d'ontologie, souvent plus lent.

Les schémas de données s'appuient souvent sur quatre types de termes ontologiques :
les références d'entités matérielles, les processus, les caractéristiques et les références d'informations (comme une référence à une mesure ou un document de protocole). Prenons un exemple concernant le méthane :

* « [**méthane**](http://purl.obolibrary.org/obo/CHEBI_16183) » est un matériau (produit chimique) dans l'ontologie CHEBI (définition : « Composé à un seul carbone dans lequel le carbone est attaché par des liaisons simples à quatre atomes d'hydrogène. C'est un gaz incolore, inodore, non toxique mais inflammable ».)
* « **concentration de méthane dans l'air** » est une caractéristique.
* « [**mesure du méthane**](http://purl.obolibrary.org/obo/NCIT_C186080) » est un processus de l'ontologie NCIThesaurus (définition : « La détermination de la quantité de méthane présente dans un échantillon. »).

Ou, pour le dioxyde de carbone :

* « **[dioxyde de carbone](http://purl.obolibrary.org/obo/CHEBI_16526)** » est un produit chimique de l'ontologie CHEBI (définition : « Composé à un seul carbone de formule CO2 dans lequel le carbone est attaché à chaque atome d'oxygène par une double liaison. Gaz incolore et inodore dans des conditions normales, [...]. »)
* « [**concentration de dioxyde de carbone dans l'air**](http://purl.obolibrary.org/obo/ENVO_04000004) » est une qualité (c'est-à-dire une caractéristique) dont la définition est « La concentration de dioxyde de carbone mesurée dans l'air ».
* « [**dosage du dioxyde de carbone**](http://purl.obolibrary.org/obo/OBI_2100001) » est un processus dont la définition est « Analyse d'analyte qui mesure l'abondance du dioxyde de carbone ». Notez cependant qu'aucun de ses enfants ne concerne l'échantillonnage de l'air.

Malheureusement, il est possible que les termes ci-dessus ne soient pas présents dans les ontologies auxquelles vous vous attendez ; par exemple, bien que **[concentration de méthane dans l'eau liquide](http://purl.obolibrary.org/obo/ENVO_3100020)** existe dans ENVO, il n'existe aucun terme pour la concentration de méthane dans l'air - il faudrait pour cela faire une demande de nouveau terme (NTR) pour cette ontologie.

Attention au choix entre un terme « [caractéristique](http://purl.obolibrary.org/obo/BFO_0000020) » ou un terme « information » (alias « [entité de contenu d'information](http://purl.obolibrary.org/obo/IAO_0000030) », ICE ou sa sous-classe « élément de données ») à mapper à un attribut de schéma de données. Si un terme caractéristique approprié est disponible, c'est probablement le meilleur choix. Par exemple, si vous avez le choix entre un attribut « température », choisissez une caractéristique PATO « [température](http://purl.obolibrary.org/obo/PATO_0000146) » plutôt qu'une caractéristique OBI « [donnée de mesure de température](http://purl.obolibrary.org/obo/OBI_0003079) ». (Chaque élément de données sur une mesure d'une caractéristique doit présumer à juste titre que le terme caractéristique lui-même est établi. En théorie, on pourrait générer un terme d'élément de données correspondant pour chaque caractéristique mesurable contenue dans une ontologie, mais cette hiérarchie fantôme de termes d'éléments de données est difficile à gérer manuellement, de sorte que diverses ontologies au sein d'OBO Foundry évitent cette approche.)

**L'équipe DCC Hub aidera à garantir que les NTR sont soumis et traités dans les ontologies appropriées.**

## Modélisation de graphes de connaissances
Les organismes de recherche et autres s'appuient souvent sur des formats de données tabulaires - feuilles de calcul ou bases de données SQL - et n'envisagent les graphes de connaissances que de manière expérimentale. Pendant ce temps, les ontologistes ajoutent souvent des relations et tentent des modèles de structure de données (c'est-à-dire des composants graphiques, y compris des [nanopublications](https://pmc.ncbi.nlm.nih.gov/articles/PMC7959622) qui pourraient contribuer à des bases de données graphiques potentiellement fédérées plus importantes. Cependant, comme indiqué dans une [revue](https://www.sciencedirect.com/science/article/abs/pii/S0950705121006092?via%3Dihub) de diverses ontologies, les relations qui apparaissent dans les ontologies, les graphes de connaissances et les ressources lexicales, bien que peut-être sémantiquement proches, sont souvent nommées différemment, ce qui « rend l'intégration de ces sources et la compréhension de leur couverture et de leurs lacunes très difficiles ». Certains systèmes de schémas de données comme LinkML fournissent des moyens de traduire entre les mondes tabulaires et les mondes graphiques de connaissances, mais dans ce projet, nous nous concentrons sur l'utilisation des ontologies pour les données de projet au format tabulaire.

## Formation

* Cours Force 11 : [L14 Introduction à la conservation des données à l'aide de Ontologies : ensembles de données FAIR et collaboration communautaire](https://osf.io/fj38v/) rédigés dans une perspective de santé publique mais également applicables aux métadonnées d'échantillons biologiques dans d'autres domaines.

* Pour les utilisateurs plus techniques, il existe un site Web complet [OBO Semantic Engineering Training](https://oboacademy.github.io/obook/) qui contient une [introduction à l'ontologie](https://oboacademy.github.io/obook/explanation/intro-to-ontologies/), des tutoriels, des guides pratiques (pour Protege, ODK GitHub, etc.), des guides de référence [y compris la logique](https://oboacademy.github.io/obook/explanation/subClassOf-vs-equivalentTo/) et d'autres contenus qui ont une application au-delà des ontologies compatibles avec OBO Foundry.

## Ressources
Il existe de nombreux endroits où trouver des vocabulaires structurés tels que des ontologies et des taxonomies comme source de termes.

* L'organisation CGIAR a publié une ressource d'[ontologies communes pour l'agriculture](https://bigdata.cgiar.org/ontologies-for-agriculture/).
* [AgroPortal](https://agroportal.lirmm.fr/) est une autre source de vocabulaire de recherche agricole.
* Les ressources ci-dessus relaient un certain nombre d'ontologies des sciences de la vie [OBO Foundry](https://obofoundry.org/) liées à la recherche agricole, biologique, climatique et écologique, dont un certain nombre sont répertoriées ci-dessous.

### Ontologies utiles pour la recherche agricole
Nous accueillons favorablement les ajouts à cette liste !

Nom | Préfixe | Description
--|--|--
[Ontologie agronomique](https://obofoundry.org/ontology/agro.html) | AGRO | « Ontologie des pratiques agronomiques, des techniques agronomiques et des variables agronomiques utilisées dans les expériences agronomiques.»
[Ontologie cellulaire](https://obofoundry.org/ontology/cl.html) | CL | « L'ontologie cellulaire est un vocabulaire contrôlé structuré pour les types de cellules chez les animaux.»
[Entités chimiques d'intérêt biologique](https://obofoundry.org/ontology/chebi.html) | CHEBI | « Une classification structurée des entités moléculaires d'intérêt biologique axée sur les « petits » composés chimiques.»
[Ontologie environnementale](https://obofoundry.org/ontology/envo.html) | ENVO | « Une ontologie des systèmes, composants et processus environnementaux.»
[Ontologie alimentaire](https://foodon.org) | FOODON | "Une ontologie de portée générale représentant des entités qui jouent un rôle alimentaire. Elle englobe les matériaux des écosystèmes naturels et de l'agriculture qui sont consommés par les humains et les animaux domestiques."
[Ontologie génétique](https://obofoundry.org/ontology/go.html) | GO | Fournit "une manière uniforme de décrire les fonctions des produits génétiques des organismes de tous les règnes de la vie et permet ainsi l'analyse des données génomiques"
[Classification des organismes NCBI](https://obofoundry.org/ontology/ncbitaxon.html) | NCBITaxon | "Une représentation ontologique de la taxonomie des organismes NCBI"
[Ontologie des maladies Mondo](https://obofoundry.org/ontology/mondo.html) | MONDO | "Un effort communautaire mondial visant à harmoniser plusieurs ressources sur les maladies afin de produire une ontologie fusionnée cohérente". Elle couvre à la fois les maladies spécifiques à l'homme, les maladies animales non humaines et les maladies infectieuses, y compris les maladies zoonotiques.
[Ontologie du phénotype et des traits](https://obofoundry.org/ontology/pato.html) | PATO | Une ontologie des qualités phénotypiques (propriétés, attributs ou caractéristiques).
[Ontologie des plantes](https://archive.plantontology.org/) | PO | Cette ontologie « décrit l'anatomie et la morphologie des plantes ainsi que les stades de développement de toutes les plantes. »
[Ontologie du stress des plantes](https://obofoundry.org/ontology/pso.html) | PSO | « L'ontologie du stress des plantes décrit les stress biotiques et abiotiques qu'une plante peut rencontrer. »
[UBERON](https://obofoundry.org/ontology/uberon.html) | UBERON | « Une ontologie anatomique inter-espèces intégrée couvrant les animaux et reliant plusieurs ontologies spécifiques aux espèces. »
[Ontologie des races de vertébrés](https://monarch-initiative.github.io/vertebrate-breed-ontology/) | VBO | « Se limite aux espèces animales vertébrées non humaines. Elle couvre les races et les populations de races destinées au bétail, aux animaux de compagnie et aux animaux de laboratoire.»

Auteurs : Damion Dooley