---
layout: page
title: ISTEX
---

# Le projet istex

## Informations générales

## Partenaires

* ABES
* Couperin
* Uni Lorraine pour CPU (la CRUS française), en particulier le LORIA un labo d'informatique
* CNRS

## Liens
* [Démonstration](http://demo.istex.fr)
* [Information sur les licences](http://www.licencesnationales.fr/). De plus les licences elles-mêmes sont en ligne.
* [Trello du développement DATA](https://trello.com/b/J25RKdNU/istex-data-roadmap-dpi)
* [Trello du développement API](https://trello.com/b/bxBsza88/istex-api-roadmap-dpi)
* [Trello ISTEX-SNU - intégration discovery ou api](https://trello.com/b/7WPf2ZEI/suivi-du-projet-istex-snu)



## Sources
D'après une recherche * sur la version démo le 2.11.2015

 * elsevier 6'015'593 documents
 * wiley 4'655'394
 * springer 2'304'877
 * oup 1'444'253
 * bmj 722'426
 * nature 377'804
 * ecco 207'613
 * brill-journals 130'322
 * eebo 124'410


## Remarques

  * 60 Mio d'Euros sur 3 ans (55 pour l'achat de contenus, 5 pour les services). Début mi 2012.
  * publient leurs sources sur leur propre serveur [Gitbucket](https://git.istex.fr/) et sur [GitHub](https://github.com/istex)
  * la plupart des développements techniques sont faits par l'insitut INIST du CNRS à Nancy
  * L'intégration dans les outils discovery est faite par l'uni de Lorraine aussi à Nancy
  * l'ABES fait la négociation avec les éditeurs
  * Couperin gère les contacts et recueille les besoins des bibliothécaires
  * ils ont aussi les fulltexts (pdf, ...)
  * utilisent [GROBID](http://grobid.readthedocs.org) pour extraire les métadonnées des pdf, ...
  * le format pivot est MODS pour les métadonnées et TEI pour les fulltexts
  * **Conversion** : message de Claude Niederlender de décembre 2015 : "Oui, nous utilisons XSLT : une feuille de style par DTD ou schéma. La même XSLT peut couvrir plusieurs versions du même schéma. Notre chaîne de traitement exécute ces transformations via l'outil linux xsltproc."
  * vu dans le [rapport des journées ISTEX](http://www.istex.fr/wp-content/uploads/2015/06/CR-s%C3%A9minaire-services-ISTEX-18-et-19-mars-2015_V080615.pdf)

> **Rapport sur la qualité des données et métadonnées ISTEX et le besoin de curation**
>
> Stéphane POUYLLAU, président du Comité Technique ISTEX, indique que, suite à la dernière réunion
du Comité Technique le 4 mars 2015, une note est en cours de rédaction sur la question de la qualité
des données et métadonnées acquises dans le cadre d’ISTEX et sur le besoin de curation. Cette note
sera remise au Comité Exécutif ISTEX pour permettre une réflexion sur les besoins de prétraitement et
de normalisation des données textuelles et des métadonnées.

&nbsp;


> **Email de Yann Nicolas du 8.12.2015**
>
> Nous recevons les métadonnées au niveau articles et l'on peut distinguer trois cas où elles pêchent : la structure, l'exactitude, et la richesse.
Pour la structure, on constate que l'on est parfois loin d'avoir 100 % de fichiers valides, ce qui signifie que les DTD sont mal appliquées. Dans un cas (RSC) il faut même faire appel à plusieurs fichiers différents pour reconstituer un ensemble de métadonnées pertinent.

>Pour l'exactitude, on relève fréquemment des problèmes de "découpages" d'une revue (i.e les versions anciennes d'un titre ont le même ISSN que la version courante).

>Les métadonnées sont par ailleurs assez pauvres : peu de résumés, peu de mots clés (cela s'explique cependant par les pratiques scientifiques de certaines disciplines, évoluant par ailleurs dans le temps). Les métadonnées n'utilisent par ailleurs pas de référentiels auteur.

## Licence

Sur les métadonnées, figure dans la licence la phrase suivante pour De Gruyter et Oxford.

> Les Métadonnées seront placées sous le régime de la licence ouverte/open licence Etalab

Si l'on en croit <https://www.etalab.gouv.fr/licence-ouverte-open-licence>, cela s'apparente à CC-BY. Il faut notamment :

> Mentionner la paternité de « l’Information » : sa source (a minima le nom du « Producteur ») et la date de sa dernière mise à jour.

De plus pour Oxford :

> ... à l'exception des résumés, lesquels seront placés sous une licence CC-BY-NC 3.0

Pour Springer, c'est moins clair :

> Le droit d'adapter, modifier, transformer, faire évoluer, enrichir en tout ou en partie, les métadonnées, d'en extraire tout ou partie, les intégrer en tout ou partie dans toute création nouvelle, les associer à tout texte, légende, les intégrer dans toute base de données selon les droits d'accès définis à l'article 2 (définition). Notamment les métadonnées pourront être associées et liées à d'autres métadonnées des établissements et versées dans Worldcat

Pas sûr qu'on puisse faire quelque chose avec ceci...



## Diagramme

![Schéma ISTEX]({{ site.github.url }}/public/images/schema_istex.png)


## Exemple de métadonnées

<https://api.istex.fr/document/55420CDEEA0F6538E215A511C72E2E5E57570138/metadata/mods>

{% highlight xml %}

<mods version="3.6">
    <titleInfo>
        <title>Abolishing a sinus arrest resistant to atropine by aminophylline</title>
    </titleInfo>
    <titleInfo type="alternative" contentType="CDATA">
        <title>Abolishing a sinus arrest resistant to atropine by aminophylline</title>
    </titleInfo>
    <name type="personal">
        <namePart type="given">János</namePart>
        <namePart type="family">Tomcsányi</namePart>
        <affiliation>Department of Cardiology and Internal Medicine, National Korányi Institute for Tuberculosis and Pulmonology, Budapest, Hungary</affiliation>
        <description>Correspondence to: J. Tomcsányi M.D., National Korányi Institute for Tuberculosis and Pulmonology, Budapest 124, H-1529, Hungary.</description>
        <role>
            <roleTerm type="text">author</roleTerm>
        </role>
    </name>
    <name type="personal">
        <namePart type="given">Andrea</namePart>
        <namePart type="family">Grósz</namePart>
        <affiliation>Department of Cardiology and Internal Medicine, National Korányi Institute for Tuberculosis and Pulmonology, Budapest, Hungary</affiliation>
        <role>
            <roleTerm type="text">author</roleTerm>
        </role>
    </name>
    <name type="personal">
        <namePart type="given">Kristóf</namePart>
        <namePart type="family">Karlócai</namePart>
        <affiliation>Department of Cardiology and Internal Medicine, National Korányi Institute for Tuberculosis and Pulmonology, Budapest, Hungary</affiliation>
        <role>
            <roleTerm type="text">author</roleTerm>
        </role>
    </name>
    <typeOfResource>text</typeOfResource>
    <genre displayLabel="sco">Short communication</genre>
    <originInfo>
        <publisher>ELSEVIER</publisher>
        <dateIssued encoding="w3cdtf">1990</dateIssued>
        <dateValid encoding="w3cdtf">1990-04-24</dateValid>
        <copyrightDate encoding="w3cdtf">1990</copyrightDate>
    </originInfo>
    <physicalDescription>
        <internetMediaType>text/html</internetMediaType>
    </physicalDescription>
    <abstract lang="en">A 66-year-old patient is presented in whom sinus arrest resistant to atropine was abolished by aminophylline, a competitive antagonist of adenosine.</abstract>
    <note type="content">Section title: Brief report</note>
    <subject>
        <genre>Keywords</genre>
        <topic>Sinus arrest</topic>
        <topic>Adenosine</topic>
        <topic>Aminophylline</topic>
    </subject>
    <relatedItem type="host">
        <titleInfo>
            <title>International Journal of Cardiology</title>
        </titleInfo>
        <titleInfo type="abbreviated">
            <title>IJCA</title>
        </titleInfo>
        <originInfo>
            <dateIssued encoding="w3cdtf">199010</dateIssued>
        </originInfo>
        <identifier type="ISSN">0167-5273</identifier>
        <identifier type="PII">S0167-5273(00)X0244-6</identifier>
        <part>
            <date>199010</date>
            <detail type="volume">
                <number>29</number>
                <caption>vol.</caption>
            </detail>
            <detail type="issue">
                <number>1</number>
                <caption>no.</caption>
            </detail>
            <extent unit="issue pages">
                <start>1</start>
                <end>104</end>
            </extent>
            <extent unit="pages">
                <start>96</start>
                <end>98</end>
            </extent>
        </part>
    </relatedItem>
    <relatedItem type="isReferencedBy" displayLabel="BIB1">
        <titleInfo>
            <title>The physiological activity of adenosine compounds with special reference to their action upon the mammalian heart</title>
        </titleInfo>
        <name type="personal">
            <namePart type="given">AN</namePart>
            <namePart type="family">Drury</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <name type="personal">
            <namePart type="given">A</namePart>
            <namePart type="family">Szent-Györgyi</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <relatedItem type="host">
            <titleInfo>
                <title>J Physiol</title>
            </titleInfo>
            <part>
                <date>1929</date>
                <detail type="volume">
                    <number>68</number>
                </detail>
                <extent unit="pages">
                    <start>213</start>
                    <end>237</end>
                </extent>
            </part>
        </relatedItem>
    </relatedItem>
    <relatedItem type="isReferencedBy" displayLabel="BIB2">
        <titleInfo>
            <title>Adenosine receptors in frog sinus venosus: slow inhibitory potentials produced by adenosine compounds and acetylcholine</title>
        </titleInfo>
        <name type="personal">
            <namePart type="given">HC</namePart>
            <namePart type="family">Hartzell</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <relatedItem type="host">
            <titleInfo>
                <title>J Physiol</title>
            </titleInfo>
            <part>
                <date>1979</date>
                <detail type="volume">
                    <number>293</number>
                </detail>
                <extent unit="pages">
                    <start>23</start>
                    <end>49</end>
                </extent>
            </part>
        </relatedItem>
    </relatedItem>
    <relatedItem type="isReferencedBy" displayLabel="BIB3">
        <titleInfo>
            <title>Evidence for an adenosine receptor on the surface of dog coronary myocytes</title>
        </titleInfo>
        <name type="personal">
            <namePart type="given">RA</namePart>
            <namePart type="family">Olson</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <name type="personal">
            <namePart type="given">JD</namePart>
            <namePart type="family">Charles</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <name type="personal">
            <namePart type="given">EM</namePart>
            <namePart type="family">Khouri</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <name type="personal">
            <namePart type="given">RE</namePart>
            <namePart type="family">Patterson</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <relatedItem type="host">
            <titleInfo>
                <title>Circ Res</title>
            </titleInfo>
            <part>
                <date>1976</date>
                <detail type="volume">
                    <number>39</number>
                </detail>
                <extent unit="pages">
                    <start>93</start>
                    <end>98</end>
                </extent>
            </part>
        </relatedItem>
    </relatedItem>
    <relatedItem type="isReferencedBy" displayLabel="BIB4">
        <titleInfo>
            <title>Correlation of sinus slowing and hyperpolarisation caused by adenosine in sinus node</title>
        </titleInfo>
        <name type="personal">
            <namePart type="given">GA</namePart>
            <namePart type="family">West</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <name type="personal">
            <namePart type="given">L</namePart>
            <namePart type="family">Belardinelli</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <relatedItem type="host">
            <titleInfo>
                <title>Pflügers Arch</title>
            </titleInfo>
            <part>
                <date>1985</date>
                <detail type="volume">
                    <number>403</number>
                </detail>
                <extent unit="pages">
                    <start>75</start>
                    <end>81</end>
                </extent>
            </part>
        </relatedItem>
    </relatedItem>
    <relatedItem type="isReferencedBy" displayLabel="BIB5">
        <titleInfo>
            <title>Mechanism of atropine-resistant atrioventricular block during inferior myocardial infarction: possible rule of adenosine</title>
        </titleInfo>
        <name type="personal">
            <namePart type="given">RC</namePart>
            <namePart type="family">Wesley</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <name type="personal">
            <namePart type="given">BB</namePart>
            <namePart type="family">Lerman</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <name type="personal">
            <namePart type="given">JP</namePart>
            <namePart type="family">Dimarco</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <name type="personal">
            <namePart type="given">RM</namePart>
            <namePart type="family">Berne</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <name type="personal">
            <namePart type="given">L</namePart>
            <namePart type="family">Belardinelli</namePart>
            <role>
                <roleTerm type="text">author</roleTerm>
            </role>
        </name>
        <relatedItem type="host">
            <titleInfo>
                <title>J Am Coll Cardiol</title>
            </titleInfo>
            <part>
                <date>1986</date>
                <detail type="volume">
                    <number>8</number>
                </detail>
                <extent unit="pages">
                    <start>1232</start>
                    <end>1234</end>
                </extent>
            </part>
        </relatedItem>
    </relatedItem>
    <identifier type="istex">55420CDEEA0F6538E215A511C72E2E5E57570138</identifier>
    <identifier type="DOI">10.1016/0167-5273(90)90281-9</identifier>
    <identifier type="PII">0167-5273(90)90281-9</identifier>
    <recordInfo>
        <recordOrigin>ELSEVIER</recordOrigin>
    </recordInfo>
</mods>
{% endhighlight %}
