---
layout: page
title: Critères
---

# Critères pour les métadonnées

## Techniques

 * Ist das XML wohlgeformt?
 * Stimmt die Zeichensatzdeklaration mit dem tatsächlichen Zeichensatz überein?
 * Validiert das XML gegen ein angegebenes Schema oder DTD?
 * Lassen sich die Daten „vernünftig“ parsen?
 * gestion correcte des caractères spéciaux (par exemple formules mathématiques en MathML)
 * structure de fichier facilement utilisable (le plus simple oai). Si arborescence, est-elle utilisable ?
 * Comment sont gérés les namespaces XML


## Contenu


* spécifications différentes pour livres, articles, chapitres, ...
* tout ce qui est sur la page (comme les français)
* Homogénéité du contenu. Est-ce que tout le contenu de l'archive est décrit de manière homogène. Attention avec les rachats d'un éditeur par un autre et les fusions multiples.
* est-ce que les informations volumes / issues sont cohérentes tout au long du contenu ?
* les métadonnées sont-elles disponibles pour tout le contenu ?
* quels contenus sont disponibles : niveau périodique, article, niveau livre, chapitres
* y a-t-il de la ponctuation superflue à la fin de certains champs ?
* Est-il possible de lier les métadonnées aux fulltexts (pdf) ? Y a-t-il un champ permettant de faire ce lien ?


### Champs pour les articles

 * nom des auteurs
 * prénom complet des auteurs
 * initiale du prénom
 * nom et prénom dans des champs séparés
 * affiliation des auteurs
 * adresse d'un auteur pour la correspondance
 * nom du périodique
 * nom abbrégé du périodique
 * année de publication
 * mois de publication
 * jour de publication
 * année de publication en ligne
 * mois de publication en ligne
 * jour de publication en ligne
 * volume
 * numéro
 * page de début
 * page de fin
 * nombre de pages
 * publisher
 * abstract
 * keywords (texte libre)
 * keywords (selon un thésaurus, une ontologie)
 * doi
 * url
 * type de document
 * issn électronique
 * issn imprimé
 * documents cités
 * identifiant unique de l'éditeur ?
 * licence sur les métadonnées ?
 * licence sur le contenu (pdf, html)
 * copyright ?
 * open access ?
 * Mention des grants ayant financé la recherche (par exemple via fundref) dans un champ note
 * Mention des grants ayant financé la recherche (par exemple via fundref) dans un champ spécifique
 * historique de publication (date de réception, date d'acceptation, révisions, ...)
 * langue du document
 * format du document final (pdf, html, …)


## Juridiques

Hier sollten wir (Konsortium, swissbib, die Bibliotheken im Allgemeinen) eine einheitliche und klare
Policy haben. Kurz gesagt: Lizenz CC0. Falls das nicht möglich ist, haben wir Schwierigkeiten, die
Metadaten als linked open data zu verwenden (linked schon, open nicht). Ich sehe die Metadaten
gewissermassen als der Schlüssel zum Haus: Das Haus kostet, um die Nutzung zu vereinfachen und
für unserer Nutzerinnen alles zugänglich zu machen, geben uns die Verlage die Schlüssel frei in die
Hand. Ist es nicht möglich, diese Lizenz als Vorbedingung für einen Vertragsabschluss zu fixieren? Die
Schweizer Verbünde haben ihre Metadaten grösstenteils unter eine freie Lizenz gestellt,
unterschiedliche Lizenzbedingungen erschweren oder verunmöglichen zukünftige Angebote. Gerade
Punkt III/04g enthält Potential für Definitionsstreitigkeiten.
In anderem Fall haben wir es mit unterschiedlich gestuften Rechten zu tun.

 * droit d'héberger les métadonnées
 * licence CC0

## Tests à effectuer sur les données entières

 * est-ce que toutes les issues / volumes / années sont présentes
 * est-ce que les caractères spéciaux sont bien gérés
 * est-ce que les champs sont utilisés de manière homogène sur tout le contenu
 * quelle DTD quand
 * est-ce que les informations de volume, issue, pages sont saisies de manière uniforme (sans abbréviation vol, no, ...)
 * est-ce que les mois / jours /années de publication ont des valeurs correctes (pas des 00 par exemple)
 * pas de doublons ? Test sur les doi ?
 * est qu'il y a des titres récurrents du genre "keine titel verfügbar" ?
