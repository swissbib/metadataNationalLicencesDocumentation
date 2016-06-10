---
layout: page
title: SOLR
---

# SOLR

Fonction première : un moteur de recherche.

Néanmoins, il pourrait éventuellement être utilisé pour analyser la qualité des donneés de la manière suivante :
 * import dans un index de dev
 * observation des facettes et des résultats

Après quelques tests le 30.11.2015, cela semble quand même être un peu overkill pour les tâches nécessaires dans le cadre de ce projet. D'autres outils semblent plus appropriés pour tester la qualité des données.

**Grand avantage** : certain que cela fonctionne, même avec d'importantes quantité de données.

### 2 décembre 2015

Installation de l'index Swissbib Basel-Bern en local :

```
cd /media/lionel/Data/swissbib-data/solrbb/solrmarkus/bin
bash start.sh
```
Et ensuite ouvrir <http://localhost:8080/solr>.

### Remarques

La pertinence est gérée dans VuFind dans le fichier `searchspecs.yaml`
