
## Général

 * Il n'y a pas de favicons
 * L’affichage des astérisques pour les champs obligatoire n'est que visuel, il doit y avoir un champ vocalisable, on devrait avoir : `<label for="monchamp"><abbr aria-hidden="true" title="(Obligatoire)">*</abbr> Numéro de télépaiement : </label>`

## Menu principal

* Le menu d’évitement devrait être un menu (`<nav>`)
* Le menu principal doit avoir le `role=navigation`
* Manque des `title` ou `aria-label` sur les liens externes

## Tableau de bord

* La liste devrait être une navigation `role=navigation`
* Le bouton retour devrait être un lien
* Le bouton consulter du tableau devrait être plus explicite : consulter la déclaration numéro 4735077. (ajouter un `aria-label`).
* Supprimer la 11 ème colonne car elle est vide. Le bouton accéder doit être dans la colonne "actions".
* On ne sait pas quelle est la différence entre "consulter" et "accéder"… consulter quoi ? accéder à quoi ?

## Déposer/modifier mes déclarations

 * Pas d’erreur sur le type de contenu (non numéraire) pour : Sucre pour la chaptalisation
 * Aucun placeholder pour proposer des types de données à indiquer.
