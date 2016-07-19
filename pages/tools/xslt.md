---
layout: page
title: XSLT
---

# XSLT

Un très grand standard utilisé par tous. Semble le moyen le plus approprié pour partager des transformations avec d'autres bibliothèques.

Problèmes :

 * on ne peut pas tout faire avec XSLT (il faut parfois y injecter du java ou du php)
 * tout ce qui tourne autour (traitement des fichiers, moteur de transformation, ...) peut être alors peu documenté

## Problèmes

C'est conseillé d'avoir 5* en RAM la taille du fichier pour l'analyser. Donc il faut splitter les fichiers en plus petites parties (fichier d'environ 1Go par exemple pour 8Go de RAM)

## xsltproc
