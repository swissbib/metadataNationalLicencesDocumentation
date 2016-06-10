---
layout: page
title: Summary Quality Control
---

# Petit résumé

 1. Dezipper les fichiers (un fichier xml par article)
 2. Regrouper les fichiers par lots (par exemple par périodique) pour réduire le nombre de fichiers (un grand nombre ralentit tout le processus). Lors de cette opération, supprimer les doctypes (ou alors passer cette information dans le xml).
 3. Avec metafacture transformer un périodique en json et l'indexer dans elasticsearch
 4. extraire le mapping de elasticsearch `GET /springer/_mapping`
 5. ajuster le mapping (années de type int, champs pas analysés ou alors analyzer trimmer qui enlève les espaces)
 6. charger le mapping corrigé
 7. indexer le contenu complet dans elasticsearch (1 heure pour springer)
 8. analyser dans elasticsearch
 9. résultat intéressant (liste des titres en json)
 10. avec python parser le résultat pour en faire un csv
