---
layout: page
title: De Gruyter
---
# Analysis of De Gruyter complete set

## Introduction

|Description du jeu||
| :------------- | :------------- |
|Editeur|De Gruyter|
|Remarque|Première livraison complète, y compris fulltext dans le XML|
|Date de réception du jeu de données|18.12.2015|
|Nombre de fichiers XML|517'320|
|Type de récupération (OAI, FTP, autre)|FTP|
|Structure de fichiers|un fichier xml par article|
|Licence sur les métadonnées|CC0 (mais pas pour les fulltexts)|

## Champs présents

<div markdown="1">
champ|nombre d'occurences
------------- | -------------:
{% include quality_control/gruyter1/fields.txt %}
</div>

## Champs présents (ES)

<div markdown="1">
champ|pourcentage de présence|nombre de documents avec ce champ
------------- | -------------: | -------------:
{% include quality_control/gruyter1/fieldsES.txt %}
</div>

## Répartition sur les DTD

<div markdown="1">
|nombre de documents|DTD|
| -------------: | :------------- |
{% include quality_control/gruyter1/doctypes.txt %}
</div>

On peut résumer ceci ainsi :

|DTD|nombre de documents|pourcentage
| :--- | ---: | ---:
|NLM 2.2|66'758|13.8%
|NLM 3.0 & 3.0.2|185133|38.3%
|JATS 1.0|54'906|11.3%
|No DTD given (a priori NLM 2.2)|177'161|36.6%
|**Total**| **483'958** | **100%**


## XML bien formés

100% des fichiers XML sont bien formés (le test prend environ 1h30 avec xmllint).

## Validité

Quelques tests manuels : probablement peu de documents valides : il y a des choses comme (avec `<!DOCTYPE article PUBLIC "-//NLM//DTD JATS (Z39.96) Journal Publishing DTD with OASIS Tables v1.0 20120330//EN" "JATS-journalpublishing-oasis-article1.dtd">`)

{% highlight xml %}
<related-article xmlns:xlink="http://www.w3.org/1999/xlink" related-article-type="pdf" xlink.href="annalen-1942-jg07.pdf" />
<post-process status="nothing-found">2014-07-13T19:39:36.929331+02:00</post-process>
<original type="pdf" xlink.href="annalen-1942-jg07.pdf" />
{% endhighlight %}

Ces éléments sont inventés par De Gruyter.

## Namespaces

<div markdown="1">
|nombre d'occurence|namespace|
| -------------: | :------------- |
{% include quality_control/gruyter1/namespaces.txt %}
</div>

## Encodings

<div markdown="1">
|nombre d'occurence|encodings|
| -------------: | :------------- |
{% include quality_control/gruyter1/encodings.txt %}
</div>


## Liste des titres
[Liste des titres pour analyse]({{ site.github.url }}/public/csv/gruyter_analyis.csv)


## Répartition sur les années de copyright

<div markdown="1">
|nombre de documents|année|
| -------------: | :------------- |
{% include quality_control/gruyter1/copyright-years.txt %}
</div>
