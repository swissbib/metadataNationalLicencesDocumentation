---
layout: page
title: Exemple de rapport de qualité
---

# Exemple de rapport de qualité d'analyse de métadonnées

## Introduction

|Description du jeu||
| :------------- | :------------- |
|Editeur|De Gruyter|
|Remarque|Echantillon pour 237 journaux en anglais|
|Date de réception du jeu de données|5.12.2015|
|Date d'analyse|7.12.2015|
|Nombre de documents (article)|824'000|
|Type de récupération (OAI, FTP, autre)|OAI|
|Structure de fichiers|un fichier xml par article|
|Licence sur les métadonnées| inconnu|

## XML bien formés

||Nombre de documents|Pourcentage|
| :------------- | :------------- | :------------- |
|Nombre de fichier XML bien formés|735000|89.1%|
|Nombre de fichier XML mal formés|89000|10.9%|


### Erreurs.

 * Fichier de validation principal: /home/lionel/Documents/swissbib/testdata/testdata_nationallizenzen/CUP/CUP.S113874161400002Xh.xml
 * Schéma: /home/lionel/programmes/Oxygen XML Editor 17/frameworks/jats/O2-DTD/O2-blue.dtd
 * Nom du moteur: Xerces

Erreurs (par nombre d'occurences décroissantes):

 * **823 fois** : Description: Un élément avec l'identificateur "ref11" doit apparaître dans le document.
Emplacement de début: 103:386
Emplacement de fin: 103:393
 * **212 fois** : Description: L'attribut "pub-id-type" avec la valeur "ThomsonISI" doit avoir une valeur de la liste "art-access-id arxiv coden doaj doi isbn manuscript medline other pii pmcid pmid publisher-id sici std-designation ".
Emplacement de début: 1388:290
Emplacement de fin: 1388:302
 * **5 fois** : Description: L'attribut "xlink.href" n'est pas autorisé à apparaître dans l'élément "inline-graphic".
Emplacement de début: 1345:17
Emplacement de fin: 1345:66
 * **3 fois** : Description: L'attribut "xmlns:mml" n'est pas autorisé à apparaître dans l'élément "sec".
Emplacement de début: 85:63
Emplacement de fin: 85:109

## Encodage

||Nombre de documents|Pourcentage|
| :------------- | -------------: | -------------: |
|UTF-8|687'000|83%|
|US-ASCII|130'000|16%|
|inconnu|7'000|1%|


##   Caractères spéciaux

|type|exemple|
| :------------- | :------------- |
|Exemple d'un auteur avec é|Théodore de Bèze|
|Exemple d'un auteur avec ş|Yaşar Kemal|
|Exemple d'un auteur avec č|Julius Fučík|
|Exemple de formule mathématique| ∂F t|
|Exemple de formule mathématique (MathML)|&lt;mml:mi mathvariant="normal"&gt;Γ&lt;/mml:mi&gt;|


## Namespaces

Une liste des namespaces utilisés dans les documents.


## DTD

||Nombre de documents|Pourcentage|Documents valides|Proportion de documents valides|
| :------------- | -------------: | -------------: |-------------: |-------------: |
|-//NLM//DTD JATS (Z39.96) Journal Publishing DTD with OASIS Tables v1.0 20120330//EN|107'000|13%|100'000|93%|
|//NLM//DTD Journal Publishing DTD v2.3 20070202//EN|52'000|6%|26'000|50%
|-//Springer-Verlag//DTD A++ V2.4//EN|665'000|81%|100'000|15%

## Répartition sur les années

|année|nombre de documents|
| :------------- | :------------- |
|2015|22'000|
|2014|25'000|
|...|...|
|1826|339|
|vide|47|
|jg|345|

## Répartition sur les journaux

|titre|issn|années trouvées|nombre de documents|
| :------------- | :------------- |:------------- |:------------- |
|journal of blabli| 1234-5678 |1982-2015 |224'000
|journal of blabla|4234-9678| 1937-1999 |132'000
|...|...|...|...|


## Proportion des champs

|champ|proportion|
| :------------- | ------------: |
|doi|100%|
|abstract|25%|
|...|...|


## Les 10 titres les plus courants

Pour repérer d'éventuels "Kein Titel verfügbar"
Les 10 titres les plus courts.

## Tests manuels

### Ponctuation

Champs terminés par de la poncutation superflue ?

### Contenus

Y a-t-il des contenus à exclure (tables des matières, préfaces, ...) ?
Y a-t-il des champs sur la plateforme de l'éditeur qui ne sont pas dans les méatadonnées ?
