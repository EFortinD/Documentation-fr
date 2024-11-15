---
layout: default
title: GitHub Desktop
parent: Aide GitHub
nav_order: 3
---

# GitHub Desktop
{: .no_toc }

## Table des matières
{: .no_toc .text-delta }

1. TOC
{:toc}

GitHub Desktop vous aide à copier le contenu de votre référentiel sur votre ordinateur. Cela est utile lorsque vous souhaitez exécuter le code sur votre ordinateur pour l'analyser, ou si vous souhaitez utiliser un éditeur de texte sur votre ordinateur car l'éditeur Web de la page Web GitHub n'est pas suffisant. Vous utilisez GitHub Desktop pour garder votre version locale synchronisée avec la version GitHub du référentiel.

Vous devez d'abord [installer GitHub Desktop (disponible pour Windows et MacOS)](https://docs.github.com/en/desktop/installing-and-authenticating-to-github-desktop/installing-github-desktop).

## Lier un référentiel

Sur le Web, accédez au référentiel GitHub que vous souhaitez ouvrir avec GitHub Desktop. À partir du bouton « <> Code », sélectionnez « Ouvrir avec GitHub Desktop ». Vous commencerez le processus de clonage du référentiel localement sur votre ordinateur. Le référentiel GitHub que vous avez cloné est l'origine, il est en amont de votre version locale et est considéré comme distant. Le référentiel sur votre ordinateur est votre version locale.

![Lien vers un référentiel existant dans GitHub](../assets/images/github_desktop_open.png).

La liaison à un référentiel créera un dossier GitHub sur votre ordinateur qui contiendra le contenu du référentiel. Vous pouvez accéder à ce dossier et exécuter du code, afficher des documents, modifier le contenu et enregistrer vos résultats. Enregistrer vos résultats n'est pas la même chose que valider. Lorsque vous utilisez GitHub Desktop, vous devrez faire les deux : enregistrer vos fichiers, puis valider (localement) vos modifications. Lorsque vous êtes satisfait de votre travail, vous repoussez vos modifications vers l'origine.

## Pousser, tirer et requêtes de tirage

Nous avons d'abord fait l'expérience des requêtes de tirage lorsque nous avons discuté de l'utilisation des branches dans GitHub et de la fusion de branches. Avec l'introduction du travail local, nous introduisons maintenant les concepts de pousser et de tirer. Le pousser et le tirer dans GitHub sont différents de la création d'une requête de tirage (PR), bien qu'ils fassent tous partie du flux de travail Git. Voici une répartition :

### Pousser et tirer :

* **Tirer** : cette action récupère les dernières modifications du référentiel distant (origine) et les intègre dans votre branche locale. Cela peut être fait avec ou sans que vos propres modifications soient présentes dans la branche. _Objectif_ : mettre à jour votre copie locale avec les derniers commits effectués par d'autres.
* **Pushing** : cette action envoie les modifications (commits) que vous avez apportées localement au référentiel distant (origine), en le mettant à jour avec votre nouveau travail. _Objectif_ : partager vos modifications avec d'autres en les rendant disponibles sur le référentiel distant.

Le push et le pull sont des interactions directes entre votre référentiel local et le référentiel distant (origine).

### Pull Request (PR) :

* Une **Pull Request** est une demande formelle de fusion des modifications d'une branche (généralement une branche de fonctionnalité ou de développement) dans une autre branche (souvent la branche principale ou master). _Objectif_ : proposer, examiner et discuter des modifications avant qu'elles ne soient fusionnées dans la base de code principale. Cela permet aux autres membres de l'équipe d'examiner votre code, de le commenter et de demander des modifications si nécessaire.

{: .important-title }
> Push et Pull vs Pull Request
>
> Le push et le pull traitent de la synchronisation des modifications entre votre référentiel local et le référentiel distant.
>
> Les demandes d'extraction impliquent une demande de fusion des modifications d'une branche vers une autre et sont généralement utilisées pour les révisions de code, les discussions et la collaboration avant l'intégration finale.

Bien que vous envoyiez souvent des modifications avant de créer une demande d'extraction, le processus de demande d'extraction ajoute une couche de collaboration et d'examen que la simple insertion et l'extraction ne fournissent pas.

## Travailler localement

Chaque fois que vous commencez à travailler, vous devez confirmer le référentiel et la branche sur lesquels vous travaillez, puis extraire l'origine - cela récupère toutes les dernières modifications de votre branche de travail dans GitHub Desktop. Si quelqu'un a apporté des modifications en amont dans le référentiel GitHub lui-même (l'origine), et si vous avez apporté des modifications aux fichiers mais n'avez pas poussé vos modifications en amont vers l'origine, vous devrez peut-être résoudre certains conflits.

La récupération fréquente de l'origine signifie que votre copie locale du référentiel est à jour avec toutes les modifications qui peuvent avoir été apportées par d'autres ou à partir d'autres branches. Si quelqu'un a poussé des modifications vers le référentiel distant, vous serez au courant de ces modifications avant de commencer votre travail.

En récupérant et en extrayant les dernières modifications, vous réduisez le risque de conflits de fusion ultérieurs. Si vos modifications locales entrent en conflit avec les modifications distantes récemment récupérées, il est préférable de les résoudre avant de commencer à travailler plutôt qu'après avoir effectué des modifications supplémentaires.

![GitHub desktop](../assets/images/github_desktop.png)

## Enregistrement et validation

Une fois vos fichiers enregistrés sur votre ordinateur, il est temps de valider vos fichiers dans GitHub Desktop. La validation fait partie de l'historique des versions dans votre référentiel local. Vous pouvez ultérieurement revenir à cette validation si nécessaire ou la comparer à d'autres validations.

Les modifications sont enregistrées **uniquement** dans votre **référentiel Git local** (sur votre ordinateur). Cette validation n'est pas encore partagée avec d'autres personnes, car elle reste locale jusqu'à ce que vous la transmettiez au référentiel distant (origine).

{: .important }
La validation locale dans GitHub Desktop **enregistre un instantané de vos modifications** dans votre référentiel local, mais les modifications restent privées sur votre ordinateur jusqu'à ce que vous les transmettiez au référentiel distant.

## Étapes suivantes après la validation locale
- **Push to Remote** : une fois les fichiers validés localement, vous pouvez les _push_ vers le référentiel distant sur GitHub (origine) pour partager les modifications avec d'autres.
- **Pull Requests** : si vous travaillez sur une branche et êtes prêt à proposer des modifications à une autre branche (par exemple, « main »), vous pouvez créer une _Pull Request_ après l'avoir poussée.

- écrit par Carly Huitema



