---
layout: page
title: JATS
---
# JATS format

## Description

The Journal Article Tag Suite (JATS) project at NCBI is a continuation of the work done here to create and support the "Archiving and Interchange Tag Suite" or the "NLM DTDs". The current standard is NISO JATS version 1.0 and is fully backward compatible with NLM version 3.0.

La version 3.0 de NLM est un grand changement par rapport aux versions précédentes.

<http://jats.nlm.nih.gov>

## Transfomations

 * [Transformation NLM de Import Vufind](https://github.com/vufind-org/vufind/blob/master/import/xsl/nlm_ojs.xsl)
 * [Transformation de JATS vers Crossref XML](http://help.crossref.org/nlm-to-crossref-conversion)

## Différentes flavour de la NLM DTD

Iil y a 3 variantes, de la plus complète à la plus simple :
 * Journal Archiving and Interchange
 * Journal Publishing
 * Article Authoring

Pour comparer, voici la définition de abstract pour chacune des versions :

* Journal Archiving and Interchange `((object-id)*, (sec-meta?, label?, title?, (address | alternatives | array | boxed-text | chem-struct-wrap | fig | fig-group | graphic | media | preformat | supplementary-material | table-wrap | table-wrap-group | disp-formula | disp-formula-group | def-list | list | tex-math | mml:math | p | related-article | related-object | ack | disp-quote | speech | statement | verse-group | x)*, (sec)*, (notes | fn-group | glossary | ref-list)*))`
* Journal Publishing `(label?, title?, (p)*, (sec)*)`
* Article Authoring `(title?, (p)*, sec*)`

Il y a un xsl qui convertit JATS vers Crossref xml : <http://www.crossref.org/help/NLM.JATS2CrossRef.v3.0.xsl>

## JATS 1.1

Début 2016 est sorti le nouveau standard ISO pour JATS 1.1. Voir les [changements](http://www.niso.org/apps/group_public/download.php/14543/JATS-SC-Recommendations-1.1.pdf) par rapport à JATS 1.0.

### Champs obligatoires dans JATS 1.0 Journal Publishing

[Diagramme](http://jats.nlm.nih.gov/publishing/tag-library/1.0/n-hqa2.html)

Journal Meta :

 * journal-id
 * issn

Article Meta :

* article-title
* pubdate - year
* contrib-group - contrib
* abstract

### Champs étonemment pas obligatoires dans JATS 1.0

 * journal-title : les informations sur le journal, on peut donc avoir des articles sans nom de journal qui passent la validation

### Swissbib JATS DTD

Avoir une DTD plus stricte par-dessus celle de JATS ? Avec des Overrides ?
