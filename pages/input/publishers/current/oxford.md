---
layout: page
title: Oxford University Press
---

# Oxford University Press (OUP)

## Description de l'échantillon

2 articles de recherche et 5 articles de type "front matter" (cover, editorial board, table of contents...), du [volume 108, issue 5 de Annals of the Entomological Society of America](http://aesa.oxfordjournals.org/content/108/5)

## Structure des fichiers

Un fichier par article

## Remarques

 * DTD //NLM//DTD Journal Publishing DTD v2.3 20070202//EN pour les articles de recherche
 * aussi -//NLM//DTD JATS (Z39.96) Journal Publishing DTD v1.1d1 20130915//EN pour les "front matters"
 * mais aussi des namespaces MathML et xlink
 * Il y a aussi la table des matières qui est décrite par un fichier XML, ainsi qu'une page [décrivant la publication](http://aesa.oxfordjournals.org/content/108/5/i4)
 * Des [informations](http://www.oxfordjournals.org/en/help/tech-info/metadata/oaipmh.html) sur le serveur OAI-PMH de Oxford. **Ne semble pas fonctionner**
 * les articles de recherche passent la validation par DTD
 * Pour les url's des journaux, on ne peut pas le construire en se basant sur le journal code du JATS. Il faut [matcher avec le domain name](http://www.oxfordjournals.org/en/help/tech-info/linking.html).
 * On peut récupérer les couvertures de cette façon <http://brain.oxfordjournals.org/current-issue/cover.gif>. Il y a les infos <http://www.oxfordjournals.org/en/help/tech-info/linking.html>
 * Il y a 5 titres un peu biscornus à bien surveiller :
   * Journal of Gerontology (qui se splitte en 4 puis se remerge en 2) : voir si toutes les métadonnées sont bien livrées
   * AIBS Bulletin
   * The archive material of the journal currently known as Pathogens & Disease actually appeared in under two archive titles, **FEMS Immunology & Medical Microbiology** and **FEMS Microbiology Immunology**.
   * Social Work Research and Abstract (qui est lié à Social Work Research)
 * Il y a 3 titres qui n'ont pas été livrés dans la première livraison
   * American Journal of Agricultural Economics
   * Mammalian Species
   * Teaching Mathematics and its Applications: An International Journal of the IMA



## Télphone avec Oxford Legal Service, 24.2.2016, David Sant

 * they are investigating in Oxford to deliver all metadata with a CC-BY-NC license but the decision won't happen before 2-3 months. They don't want to deliver already the metadata without a proper decision for all partners.
 * they don't want to allow commercial use because they sell the metadata to commercial providers
 * they might accept a CC-BY-NC license with the condition that only users from Switzerland can use it. That's kind of bad, but might serve our purposes


## Télphone avec Oxford, 29.2.2016, Elisabeth Kukla

 * ils ont SAML 2.0


## Réception des données 3 mars 2016

 * en plusieurs fois, car le serveur FTP de Swissbib a été rempli (en espérant que cela n'a pas posé de problèmes)
 * 223 dossiers (correspondants à des journaux) qui contiennent un fichier tar par issue
 * 29'063 fichiers tar, totalisant 4.0 Go
 * Pour dézipper, petit script pour regrouper les issues par périodique car l'arborescence complète (avec nom de journal) n'est pas présente dans les fichiers tar
 * Une fois extrait : 683'050 éléments (y compris répertoires), totalisant 3.6 Go.
 * Il y a 30 notices qui ont comme eyear 0000 ! Exemple `OCCMED/occmed62-4/abstracts/kqs039.xml`
 * Gros problème : il n'y a que des notices post 1996 !!!

## 2ème livraison 28 avril 2016, les archives

 * cette fois pas de répertoires mais des fichiers tar par issue uniquement
 * ils ont livré les pdf avec !!! Mais seulement pour certains périodiques
 * 14 juin 2016 : 973'245 fichiers et dossiers








## Contact technique

 Stephen Flockton  
 Digital Content Manager  
 Journals Online Content and Archive  

 Oxford University Press  
 Great Clarendon Street  
 Oxford OX2 6DP, UK  

 Tel: +44 (0)1865 355397  
 stephen.flockton@oup.com  
 www.oxfordjournals.org

## Contact legal

 David SANT  
 +4418653530000  
 david.sant@oup.com  

## Contact licence

Elisabeth Kukla  
Regional Manager Central & Northern Europe  
Online Resources & Journals  
Oxford University Press  

www.oup.com/online | www.oxfordjournals.org  
T: +49 (0)30 85407098  
M: +49 (0)176 55452100  
E: elisabeth.kukla@oup.com


## Exemple

Exemple pour cet article <http://dx.doi.org/10.1093/aesa/sav039>

{% highlight xml %}
<article
    xmlns:mml="http://www.w3.org/1998/Math/MathML"
    xmlns:xlink="http://www.w3.org/1999/xlink"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" article-type="research-article" dtd-version="2.3" xml:lang="EN">
    <front>
        <journal-meta>
            <journal-id journal-id-type="publisher-id">aesa</journal-id>
            <journal-id journal-id-type="hwp">aesa</journal-id>
            <journal-title>Annals of the Entomological Society of America</journal-title>
            <abbrev-journal-title abbrev-type="full">Ann. Entomol. Soc. Am.</abbrev-journal-title>
            <issn pub-type="ppub">0013-8746</issn>
            <issn pub-type="epub">1938-2901</issn>
            <publisher>
                <publisher-name>Oxford University Press</publisher-name>
            </publisher>
        </journal-meta>
        <article-meta>
            <article-id pub-id-type="doi">10.1093/aesa/sav039</article-id>
            <article-id pub-id-type="publisher-id">sav039</article-id>
            <article-categories>
                <subj-group>
                    <subject>Conservation Biology and Biodiversity</subject>
                </subj-group>
            </article-categories>
            <title-group>
                <article-title>Faunistic Composition of Cleridae (Coleoptera) in El Limón de Cuauchichinola, Morelos, Mexico</article-title>
            </title-group>
            <contrib-group>
                <contrib contrib-type="author" corresp="yes" xlink:type="simple">
                    <name name-style="western">
                        <surname>Toledo-Hernández</surname>
                        <given-names>Víctor H.</given-names>
                    </name>
                    <xref ref-type="aff" rid="sav039-AFF1">
                        <sup>1</sup>
                    </xref>
                    <xref ref-type="corresp" rid="sav039-COR1">
                        <sup>2</sup>
                    </xref>
                </contrib>
                <contrib contrib-type="author" xlink:type="simple">
                    <name name-style="western">
                        <surname>Rifkind</surname>
                        <given-names>Jacques</given-names>
                    </name>
                    <xref ref-type="aff" rid="sav039-AFF3">
                        <sup>3</sup>
                    </xref>
                </contrib>
                <contrib contrib-type="author" xlink:type="simple">
                    <name name-style="western">
                        <surname>Corona-López</surname>
                        <given-names>Angélica Ma.</given-names>
                    </name>
                    <xref ref-type="aff" rid="sav039-AFF1">
                        <sup>1</sup>
                    </xref>
                </contrib>
                <contrib contrib-type="author" xlink:type="simple">
                    <name name-style="western">
                        <surname>Flores-Palacios</surname>
                        <given-names>Alejandro</given-names>
                    </name>
                    <xref ref-type="aff" rid="sav039-AFF1">
                        <sup>1</sup>
                    </xref>
                </contrib>
                <contrib contrib-type="author" xlink:type="simple">
                    <name name-style="western">
                        <surname>Leavengood</surname>
                        <given-names>John M.</given-names>
                        <suffix>Jr.</suffix>
                    </name>
                    <xref ref-type="aff" rid="sav039-AFF4">
                        <sup>4</sup>
                    </xref>
                </contrib>
                <aff id="sav039-AFF1">
                    <sup>1</sup>Centro de Investigación en Biodiversidad y Conservación (CIβyC), Universidad Autónoma del Estado de Morelos, México 62209.
                </aff>
                <aff id="sav039-AFF3">
                    <sup>3</sup>California State Collection of Arthropods, Sacramento, CA 95832.
                </aff>
                <aff id="sav039-AFF4">
                    <sup>4</sup>Department of Entomology, University of Kentucky, Agricultural Science Center Building – North, Lexington, KY 40546-0091.
                </aff>
            </contrib-group>
            <author-notes>
                <corresp id="sav039-COR1">
                    <sup>2</sup>Corresponding author, e-mail:
                    <email xlink:type="simple">victor.toledo@uaem.mx</email>.
                </corresp>
            </author-notes>
            <pub-date pub-type="ppub">
                <month>09</month>
                <year>2015</year>
            </pub-date>
            <pub-date pub-type="epub">
                <day>06</day>
                <month>07</month>
                <year>2015</year>
            </pub-date>
            <volume>108</volume>
            <issue>5</issue>
            <fpage>771</fpage>
            <lpage>776</lpage>
            <history>
                <date date-type="received">
                    <day>26</day>
                    <month>1</month>
                    <year>2015</year>
                </date>
                <date date-type="accepted">
                    <day>16</day>
                    <month>4</month>
                    <year>2015</year>
                </date>
            </history>
            <permissions>
                <copyright-statement>© The Authors 2015. Published by Oxford University Press on behalf of Entomological Society of America. All rights reserved. For Permissions, please email: journals.permissions@oup.com</copyright-statement>
                <copyright-year>2015</copyright-year>
            </permissions>
            <abstract>
                <p>This paper presents the first detailed faunistic study in Mexico for the family Cleridae, an important group of predatory beetles. The study was carried out in El Limón de Cuauchichinola, Tepalcingo, in the state of Morelos, Mexico, over a year of systematic collections (June 2006 to May 2007). The family Cleridae was found to be represented in the study area by seven subfamilies, 18 genera, and 44 species. The dominant genera were
                    <italic>Phyllobaenus</italic> Dejean with nine species, followed by
                    <italic>Cymatodera</italic> Gray with eight, and
                    <italic>Enoclerus</italic> Gahan with seven. The nonparametric estimators Incidence Coverage Estimate, Chao2, and second-order Jacknife estimated that between 65 and 78% of the true richness was recorded. The family showed a marked seasonality, with greater richness and abundance found during the rainy season. Sweeping and beating vegetation were the most efficient collection methods, producing 71.7% of the recorded species richness. Of the species determined, 18 represent new records for Morelos and five of these are new records for the country. The results provide evidence that the tropical dry forest of the Sierra de Huautla Biosphere Reserve is an ecosystem rich in species. The new records also serve to contribute to our general knowledge of the distribution of Cleridae in Mexico.
                </p>
            </abstract>
            <trans-abstract xml:lang="ES">
                <title>RESUMEN</title>
                <p>Este trabajo presenta el primer estudio sistemático de la familia Cleridae en México, un grupo muy importante de coleópteros depredadores. El estudio fue realizado en El Limón de Cuauchichinola, Tepalcingo, en el estado de Morelos, México, durante un año de recolectas sistemáticas (junio 2006 a mayo 2007). La familia Cleridae estuvo representada en el área de estudio por siete subfamilias, 18 géneros y 44 especies. Los géneros dominantes fueron
                    <italic>Phyllobaenus</italic> Dejean con nueve especies, seguido de
                    <italic>Cymatodera</italic> Gray con ocho y
                    <italic>Enoclerus</italic> Gahan con siete. Los estimadores no paramétricos ICE, Chao 2 y Jacknife 2 estiman que se registró entre 65 a 78% de la riqueza verdadera. La familia mostró una marcada estacionalidad, con su mayor riqueza y abundancia durante la temporada de lluvias. El método de colecta de barrer/golpear vegetación fue el más eficiente, con el 71.7% de las especies registradas. De las especies determinadas, 18 representan nuevos registros para el estado de Morelos y cinco de éstos son nuevos para el País. Los resultados aportan evidencia de que el Bosque Tropical Caducifolio de la Reserva de la Biosfera Sierra de Huautla es un ecosistema rico en especies. Los nuevos registros contribuyen al mejor conocimiento de la distribución de Cleridae en México.
                </p>
            </trans-abstract>
            <kwd-group>
                <kwd>predator</kwd>
                <kwd>Sierra de Huautla</kwd>
                <kwd>tropical dry forest</kwd>
                <kwd>rare species</kwd>
                <kwd>seasonality</kwd>
            </kwd-group>
            <counts>
                <page-count count="6"/>
            </counts>
        </article-meta>
    </front>
</article>
{% endhighlight %}
