# Contenu de Pourquivoter

Les données que l'application télécharge : questions, candidats, décryptages de
thèmes. Publiées par GitHub Pages sous `/v1/`, elles sont mises à jour sans
passer par une revue App Store.

**Dépôt public, et c'est délibéré.** Une application qui dit à quelqu'un pour qui
voter doit pouvoir être contredite sur ses données. Chaque position, chaque
source, chaque changement est ici, avec son historique.

## Structure

    v1/manifest.json     version du contenu, version d'app minimale, bannière
    v1/questions.json    les 25 affirmations et leurs poids par axe
    v1/candidates.json   les candidats, leurs positions, leurs sources
    v1/themes.json       les 8 axes et leurs décryptages

## Règles

1. Toute modification incrémente `contentVersion` dans `manifest.json`.
2. `schemaVersion` ne bouge qu'avec une migration et une rétrocompatibilité :
   les binaires déjà installés doivent survivre au nouveau contenu.
3. Une position de candidat sans source ne se publie pas.
4. `officialProgramURL` ne se renseigne qu'avec un vrai programme publié. Un site
   de campagne n'est pas un programme.

## Photos

Sous `v1/photos/`, uniquement des images sous licence libre (CC0, CC BY, CC BY-SA,
domaine public), avec auteur et licence dans `candidates.json`. Elles sont
hébergées ici plutôt qu'appelées chez Wikimedia : l'application ne doit pas
signaler à un tiers quel candidat quelqu'un consulte.
