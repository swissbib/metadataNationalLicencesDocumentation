---
layout: page
title: Content Collector
---

# Content Collector

## Installation

Le [Content Collector](https://github.com/swissbib/contentCollector) est disponible sur GitHub. A noter qu'il y en a aussi un dans le git interne, avec par exemple les informations de configuration sur les connexions OAI.

Le plus simple pour l'installation est d'utiliser la version précompilée par Guenter avec toutes les bonnes librairies (en particulier bson, oaiphm et requests qui ne sont pas standards) qui se trouve sur `swissbib@sb-s5.swissbib.unibas.ch:/swissbib_index/forLionel/envContentCollector`

Attention : pour que cela fonctionne il faut absolument installer ceci dans un répertoire appelé `/home/harvester`

Instructions d'installation

1. Copier le package complet
2. Créer une structure de répertoire à un endroit quelconque sur le disque

```
ln -s /home/harvester/envContentCollector/confdir confdir
mkdir data
mkdir oaiDeletes
mkdir results
mkdir rundir
```

3. Dans `/envContentCollector/bin/process-harvesting.sh`, modifier la valeur `DATA_BASE_DIR` et indiquer l'endroit déterminé ci-dessus
4. Les fichiers de configuration sont sous `confdir`. En particulier il faut modifier le `<baseDir>` pour y mettre le répertoire créé sous 2.
5. copier la config `/confdir/config.idsbb.prod.xml` et modifier les valeurs en suivant les [instructions](http://www.swissbib.org/wiki/index.php?title=Members:HarvestingInfrastructure#Elementnamen_.2F_Tags)


## Execution pour les licences nationales

On sb-coai2 :

```
cd /home/harvester/envContentCollector/bintest/
./process-nationalLicense_testdir.sh config.oxford.prod.xml
```


## Thieme

On va tenter de harvester le set suivant :
<https://www.thieme-connect.de/oai/provider?verb=ListRecords&metadataPrefix=nlm&set=journalarticles&from=2014-12-02T13:23:48z>. Ce sont tous les articles de journaux de Thieme au format NLM depuis le 2 décembre 2014.

Cela fonctionne bien. Le résultat est un très long fichier xml avec tous les records avec une entête OAI.
