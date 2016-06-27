---
layout: page
title: Cambridge
---
# Analysis of Cambridge first set

## Introduction

|Description du jeu||
| :------------- | :------------- |
|Editeur|Cambridge|
|Remarque|Première livraison complète|
|Date de réception du jeu de données|26.2.2016|
|Nombre de fichiers XML & SGML ||
|Type de récupération (OAI, FTP, autre)|FTP déposé sur swissbib.org|
|Structure de fichiers|un fichier xml ou sgml par article|


## Champs présents (XML + SGML)

<div markdown="1">
champ|nombre d'occurences
------------- | -------------:
{% include quality_control/cambridge1/fields.txt %}
</div>

## Champs présents XML seulement (ES)

<div markdown="1">
champ|pourcentage de présence|nombre de documents avec ce champ
------------- | -------------: | -------------:
{% include quality_control/cambridge1/fieldsES.txt %}
</div>

## Répartition sur les DTD

<div markdown="1">
|nombre de documents|DTD|
| -------------: | :------------- |
{% include quality_control/cambridge1/doctypes.txt %}
</div>


On peut résumer ceci ainsi :

|DTD|nombre de documents|pourcentage
| :--- | ---: | ---:
|JATS 0.4|149'831|13.2%
|JATS 1.0|70'346|6.2%
|NLM 2.2|767'070|67.7%
|SGML|145'463|12.8%
|**Total**| **1'132'710** | **100%**



## XML bien formés

100% des fichiers XML sont bien formés.



## Validité



## Namespaces

<div markdown="1">
|nombre d'occurence|namespace|
| -------------: | :------------- |
{% include quality_control/cambridge1/namespaces.txt %}
</div>

## Encodings

<div markdown="1">
|nombre d'occurence|encodings|
| -------------: | :------------- |
{% include quality_control/cambridge1/encodings.txt %}
</div>

## Liste des titres
[Liste des titres pour analyse](https://github.com/swissbib/metadataNationalLicences/tree/master/title-lists)


## Répartition sur les années de copyright

<div markdown="1">
|nombre de documents|année|
| -------------: | :------------- |
{% include quality_control/cambridge1/copyright-years.txt %}
</div>
