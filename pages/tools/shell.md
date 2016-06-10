---
layout: page
title: Shell scripts
---

# grep

    grep '<article-id pub-id-type\=\"doi\">' thieme.xml | wc -l

Prend 24 secondes pour les 329'000 articles de l'échantillon pubmed central.

    grep 'SchemaLocation\=\".*\"/' thieme.xml | cut -c 1-170 | sort | uniq -c | sort -n

Compte les occurences des différents schémas (lignes tronquées au 170 premiers caractères)

Prend aussi 24 secondes pour les 329'000 articles pubmed central

Encore mieux

    grep 'SchemaLocation\=\".*\"/' thieme.xml | cut -c 1-170 | sort -n | uniq -c

Ou alors

    grep 'SchemaLocation\=\".*\"/' thieme.xml | cut -c 1-170 | sort -n | uniq -c

Qui renvoie

    64465 http://dtd.nlm.nih.gov/ns/archiving/2.3/ http://dtd.nlm.nih.gov/archiving/2.3/xsd/archivearticle.xsd
    265135 http://jats.nlm.nih.gov/ns/archiving/1.0/ http://jats.nlm.nih.gov/archiving/1.0/xsd/JATS-archivearticle1.xsd

Pour les titres de périodiques

    grep -o 'journal-title.*\journal-title' 20151209110351-thieme-big.xml | cut -c 15-170 | sort | uniq -c | sort -n

Enlever les tags <journal-title> et </journal-title>

    sed -e 's/<[\/]\{0,1\}journal-title>//g' -i test.txt


Au final :

    grep -o '<journal-title>.*<\/journal-title>' pmc-big.xml | sed -e 's/<[\/]\{0,1\}journal-title>//g' | sort  | uniq -c | sort -n

Renvoie

     1700 Applied and Environmental Microbiology
     1913 Journal of Korean Medical Science
     1929 British journal of experimental pathology
     1965 Indian Journal of Psychiatry
     2044 Journal of Virology
     2906 British Journal of Experimental Pathology
     3072 BMJ Case Reports
     3793 BMJ : British Medical Journal
     5691 Proceedings of the National Academy of Sciences of the United States of America
     8806 The Journal of Biological Chemistry
    14681 PLoS ONE
    15859 Acta Crystallographica Section E: Structure Reports Online


Même sur tous les fichiers d'un répertoire

    grep -ohr '<journal-title>.*<\/journal-title>' . | sed -e 's/<[\/]\{0,1\}journal-title>//g' | sort  | uniq -c | sort -n
