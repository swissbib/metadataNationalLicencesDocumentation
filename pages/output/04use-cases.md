---
layout: page
title: Use Cases
---

# Different Use Cases

## Simplification du Workflow pour les bibliothèques universitaires

Avant : Chaque gestionnaire de ressources électroniques dans une université télécharge sur le site du consortium la liste des titres achetés. Puis il doit la charger dans son résolveur de lien et/ou ERM. Ce processus est assez long et fastidieux car il implique différentes transformations des données et corrections d'erreur sur les listes

Après : une target spécifique

### En images

Télécharger la liste du consortium :

![liste consortium]({{ site.github.url }}/public/images/consortium_list.png)

Sans années, ni print issn, ni volumes, ...

Retravail de cette liste dans Excel (dans les 10 universités suisses, instituts de recherche, ...). Ajout des années, volumes, ...

Import dans le résolveur de lien

![sfx loader]({{ site.github.url }}/public/images/sfx_dataloader.png)

Un prétravail de tout ceci au niveau suisse simplifierait bien des choses :

![French National Licenses]({{ site.github.url }}/public/images/french_national_licenses.jpg)


## Un privé aimerait accéder à la version en ligne d'un article

Public cible pour l'accès pour les privés : alumni hautes écoles, médecins, juristes, start-ups, pasteurs, bibliothèques publiques (pour service genre interroge), professeurs secondaires [link](http://ncse.com/blog/2016/03/teachers-access-to-scientific-literature-is-priceless-0016972), wikipediens, collaborateurs scientifiques (état, confédération)

Contexte : admettons qu'un médecin non affilié à aucune université aimerait lire l'article suivant : *Patel, S., Lyons, A. and Hosking, D. (1993). Drugs Used in the Treatment of Metabolic Bone Disease. Drugs, 46(4), pp.594-617.* Cet article est compris dans les licences nationales

Avant : il se rend dans sa bibliothèque favorite pour le demander

Après : il se rend sur swissbib.ch, recherche l'article et peut le lire en ligne. Au prélable il devra s'être inscrit dans une bibliothèque pour recevoir un login / mot de passe pour un service de type swiss edu id.

## Les state licences

Bern donne accès à toutes ses e-ressources via un EZProxy pour les gens qui ont un NPA dans le canton de Bern dans Aleph.

Luzern prévoit de faire de même.


## Mémoire à long terme

Dans 10 ans, savoir ce qui a été acheté pour les licences nationales.

Préserver les métadonnées, ainsi que (éventuellement) les fulltexts.

## Data mining, bibliométrie,

Comme on a accès au corpus complet bibliographique, on peut

 * faire du data mining sur le corpus
 * faire de la bibliométrie en interrogeant les champs <aff> par exemple

{% highlight bash %}
bmte.1995.40.issue-s1/bmte.1995.40.s1.403/bmte.1995.40.s1.403.xml:<aff id="aff1">Prof. für Biokompatible Werkstoffe und Bauweisen, ETH Zürich</aff>
bmte.1995.40.issue-s1/bmte.1995.40.s1.403/bmte.1995.40.s1.403.xml:<aff id="aff2">Prof. für Biokompatible Werkstoffe und Bauweisen, ETH Zürich</aff>
bmte.1995.40.issue-s1/bmte.1995.40.s1.403/bmte.1995.40.s1.403.xml:<aff id="aff3">, K. RuffieuxProf. für Biokompatible Werkstoffe und Bauweisen, ETH Zürich</aff>
bmte.1995.40.issue-s1/bmte.1995.40.s1.403/bmte.1995.40.s1.403.xml:<aff id="aff5">Prof. für Biokompatible Werkstoffe und Bauweisen, ETH Zürich</aff>
bmte.1995.40.issue-s1/bmte.1995.40.s1.13/bmte.1995.40.s1.13.xml:<aff id="aff1">Lehrstuhl für Biokompatible Werkstoffe und Bauweisen, ETH Zürich, Wagistr. 23, CH-8952 Schlieren</aff>
bmte.1995.40.issue-s1/bmte.1995.40.s1.377/bmte.1995.40.s1.377.xml:<aff id="aff1">Professur für Biokompatible Werkstoffe und Bauweisen, ETH Zürich, Schweiz</aff>
bmte.1995.40.issue-s1/bmte.1995.40.s1.377/bmte.1995.40.s1.377.xml:<aff id="aff2">Professur für Biokompatible Werkstoffe und Bauweisen, ETH Zürich, Schweiz</aff>
bmte.1995.40.issue-s1/bmte.1995.40.s1.377/bmte.1995.40.s1.377.xml:<aff id="aff3">Professur für Biokompatible Werkstoffe und Bauweisen, ETH Zürich, Schweiz</aff>
bmte.1995.40.issue-s1/bmte.1995.40.s1.377/bmte.1995.40.s1.377.xml:<aff id="aff4">Professur für Biokompatible Werkstoffe und Bauweisen, ETH Zürich, Schweiz</aff>
bmte.1995.40.issue-s1/bmte.1995.40.s1.377/bmte.1995.40.s1.377.xml:<aff id="aff5">Professur für Biokompatible Werkstoffe und Bauweisen, ETH Zürich, Schweiz</aff>
bmte.1995.40.issue-s1/bmte.1995.40.s1.395/bmte.1995.40.s1.395.xml:<aff id="aff1">Professur für Biokompatible Werkstoffe und Bauweisen, ETH Zürich</aff>
peps.2013.19.issue-3/peps-2013-0051/peps-2013-0051.xml:<aff id="aff1"><sup>1</sup>Department of Government, University of Essex, Wivenhoe Park, Colchester CO4 3SQ, UK, Phone: +44 1206 87 2288, Fax: +44 1206 87 3234; and ETH Zurich, Haldeneggsteig 4, Zurich 8092, Switzerland</aff>
auto.2011.59.issue-11/auto.2011.9093/auto.2011.9093.xml:<aff id="a2"><sup>2</sup> ETH Zürich, Sensory-Motor Systems Lab, Zürich, Schweiz</aff>
bfup.2005.29.issue-1/bfup.2005.56/bfup.2005.56.xml:<aff>ETH-Bibliothek Zürich, Rämisstr. 101, CH-8092 Zürich. E-Mail: marianne.tschaeppaet@library.ethz.ch</aff>
zkri.2011.226.issue-8/zkri.2011.1383/zkri.2011.1383.xml:<aff id="a1"><sup>1</sup> ETH Zürich, Laboratory of Inorganic Chemistry, Zürich, Schweiz</aff>
zkri.2011.226.issue-8/zkri.2011.1429/zkri.2011.1429.xml:<aff id="a1"><sup>1</sup> ETH Zürich, Laboratory of Inorganic Chemistry, Zürich, Schweiz</aff>
hfsg.2014.68.issue-8/hf-2013-0189/hf-2013-0189.xml:<aff id="aff1"><sup>1</sup>Institute for Building Materials, ETH Zurich, Switzerland</aff>
zpch.1989.164.issue-part_1/zpch.1989.164.part_1.1053/zpch.1989.164.part_1.1053.xml:<aff id="a1">Institute for Intermediate Energy Physics (IMP), ETHZ, CH-5234 Villigen, Switzerland</aff>
zpch.1989.164.issue-part_1/zpch.1989.164.part_1.1047/zpch.1989.164.part_1.1047.xml:<aff id="a1">Institute for Intermediate Energy Physics (IMP), ETHZ, CH-5234 Villigen, Switzerland</aff>
ract.2012.100.issue-11/ract.2012.1976/ract.2012.1976.xml:<aff id="a3">ETH Zurich, Institute of Particle Physics, Zurich, Schweiz</aff>
ract.2012.100.issue-11/ract.2012.1976/ract.2012.1976.xml:<aff id="a4">ETH Zurich, Institute of Particle Physics, Zurich, Schweiz</aff>
ijcre.2007.5.1/ijcre.2007.5.1.1650/ijcre.2007.5.1.1650.xml:<aff id="a3"><sup>3</sup>CETHIL, INSA-Lyon, <email xlink.href="mailto:dominique.baillis@insa-lyon.fr">dominique.baillis@insa-lyon.fr</email></aff>
hfsg.1978.32.issue-3/hfsg.1978.32.3.77/hfsg.1978.32.3.77.xml:<aff id="aff1">Institut für Mikrotechnologische Holzforschung, ETH Zürich</aff>
gej.2007.7.4/gej.2007.7.4.1301/gej.2007.7.4.1301.xml:<aff id="a1"><sup>1</sup>ETH Zurich - KOF Swiss Economic Institute, <email xlink.href="mailto:atukeren@kof.ethz.ch">atukeren@kof.ethz.ch</email></aff>

{% endhighlight %}

## Potentiel si on a plus de 80% des articles en ligne, potentiel futur

### discovery pour petites bibliothèques (HES)

Par exemple, on pourrait imaginer un discovery tool pour toutes les HES

### peb simplifié

Il devient très facile de savoir quelle bibliothèque suisse a accès à quel article (plus besoin de passer par les états de collection des journaux électroniques)

### open index global

En collaboration avec d'autres pays, un index libre d'articles pourrait éventuellement être créé, si les autorisations nécessaires des éditeurs sont ouvertes. Ou alors en passant par Crossref.

### ebooks

Un projet similaire pourrait être lancé pour les ebooks, qui sont souvent mal signalés actuellement dans les catalogues.
