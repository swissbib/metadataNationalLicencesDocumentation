---
layout: page
title: Thieme
---

# Thieme

## Description de l'échantillon

Des instructions pdf pour accéder à l'interface OAI de Thieme.


## Remarques sur l'interace OAI

Accès via <https://www.thieme-connect.de/oai/oaisearch.do> (ouvert)

Au 4.11.2015 :

 * 106'873 book chapters
 * 1820 books
 * 360'554 journal articles

## Harvesting du 13.12.2015

* temps de harvesting : 1 heure
* nombre d'articles : 76'141
* from: 2014-12-09T09:55:59Z
* metadataPrefix: nlm
* taille du fichier xml.gz : 33.7 Mo
* taille du fichier : 201.3 Mo

## Structure des fichiers

par oai

## Remarques

 * 3 DTD pour articles : Thieme-export-DTD (enlarged PubMed-DTD), NLM-DTD, Dublin Core
 * 2 formats pour livres et chapitres : MarcXML, DublinCore

## Exemple

Exemple pour un  [article](10.1055/s-0034-1395791)

{% highlight xml %}
<article xsi:noNamespaceSchemaLocation="http://dtd.nlm.nih.gov/publishing/3.0/xsd/journalpublishing3.xsd" xml:lang="en" article-type="scientific">
    <front>
        <journal-meta>
            <journal-id/>
            <journal-title-group>
                <journal-title>Int Arch Otorhinolaryngol</journal-title>
            </journal-title-group>
            <issn pub-type="print">1809-9777</issn>
            <issn pub-type="e-issn">1809-4864</issn>
            <publisher>
                <publisher-name>Georg Thieme Verlag Stuttgart, New York</publisher-name>
            </publisher>
        </journal-meta>
        <article-meta>
            <article-id pub-id-type="doi">10.1055/s-0034-1395791</article-id>
            <article-categories>
                <subj-group>
                    <subject>Case Report</subject>
                </subj-group>
            </article-categories>
            <title-group>
                <article-title xml:lang="en">Cochlear Implantation in Isolated Large Vestibular Aqueduct Syndrome: Report of Three Cases and Literature Review</article-title>
            </title-group>
            <contrib-group>
                <contrib>
                    <name>
                        <surname>Pradhananga</surname>
                        <given-names>Rabindra</given-names>
                    </name>
                    <aff>
                        <institution>Department of ENT-Head and Neck Surgery, Tribhuvan University Teaching Hospital, Kathmandu, Nepal</institution>
                    </aff>
                </contrib>
                <contrib>
                    <name>
                        <surname>Natarajan</surname>
                        <given-names>Kiran</given-names>
                    </name>
                    <aff>
                        <institution>Department of Otorhinolaryngology, Madras ENT Research Foundation, Chennai, Tamil Nadu, India</institution>
                    </aff>
                </contrib>
                <contrib>
                    <name>
                        <surname>Devarasetty</surname>
                        <given-names>AmarNath</given-names>
                    </name>
                    <aff>
                        <institution>Department of Otorhinolaryngology, Madras ENT Research Foundation, Chennai, Tamil Nadu, India</institution>
                    </aff>
                </contrib>
                <contrib>
                    <name>
                        <surname>Kameswaran</surname>
                        <given-names>Mohan</given-names>
                    </name>
                    <aff>
                        <institution>Department of Implantation Otology, Madras ENT Research Foundation, Chennai, Tamil Nadu, India</institution>
                    </aff>
                </contrib>
            </contrib-group>
            <pub-date pub-type="online">
                <day>14</day>
                <month>11</month>
                <year>2014</year>
            </pub-date>
            <volume>19</volume>
            <issue>04</issue>
            <fpage>359</fpage>
            <lpage>363</lpage>
            <abstract xml:lang="en">
                <p>
            Introduction Large vestibular aqueduct syndrome (LVAS) is characterized by the enlargement of the vestibular aqueduct associated with sensorineural hearing loss. It is the most common radiographically detectable inner ear anomaly in congenital hearing loss. LVAS may occur as an isolated anomaly or in association with other inner ear malformations.
            Objective To report three cases of isolated LVAS with a focus on preoperative assessment, surgical issues, and short-term postoperative follow-up with preliminary auditory habilitation outcomes.
            Resumed Report One girl and two boys with LVAS were assessed and cochlear implantation was performed for each. Various ways of intraoperative management of cerebrospinal fluid gusher and postoperative care and outcomes are reported.
            Conclusion Cochlear implantation in the deaf children with LVAS is feasible and effective.</p>
            </abstract>
            <kwd-group xml:lang="en">
                <kwd>large vestibular aqueduct</kwd>
                <kwd>cochlear implantation</kwd>
                <kwd>CSF gusher</kwd>
            </kwd-group>
        </article-meta>
    </front>
</article>
{% endhighlight %}

Exemple pour un [livre](http://dx.doi.org/10.1055/b-002-46968)
{% highlight xml %}
<record>
    <leader>00747nam a2200241n  4500</leader>
    <controlfield tag="001">1411479571808</controlfield>
    <controlfield tag="003">Georg Thieme Verlag</controlfield>
    <controlfield tag="005">20140923153931.0</controlfield>
    <controlfield tag="007">cr</controlfield>
    <controlfield tag="008">990101s1999||||gw|a||||s|||||00||||ger||</controlfield>
    <datafield tag="020" ind1=" " ind2=" ">
        <subfield code="a">9783131874511</subfield>
    </datafield>
    <datafield tag="024" ind1="7" ind2=" ">
        <subfield code="a">10.1055/b-002-46968</subfield>
        <subfield code="2">doi</subfield>
    </datafield>
    <datafield tag="050" ind1=" " ind2="4">
        <subfield code="a">RB45</subfield>
    </datafield>
    <datafield tag="100" ind1="1" ind2=" ">
        <subfield code="a">Begemann, Michael</subfield>
    </datafield>
    <datafield tag="245" ind1="1" ind2="0">
        <subfield code="a">Praktische Hämatologie</subfield>
        <subfield code="c">Michael Begemann</subfield>
        <subfield code="p">Klinik · Therapie · Methodik</subfield>
    </datafield>
    <datafield tag="250" ind1=" " ind2=" ">
        <subfield code="a">11. vollständig überarbeitete Auflage</subfield>
    </datafield>
    <datafield tag="260" ind1=" " ind2=" ">
        <subfield code="a">Stuttgart</subfield>
        <subfield code="b">Georg Thieme Verlag</subfield>
        <subfield code="c">1999</subfield>
    </datafield>
    <datafield tag="542" ind1="1" ind2=" ">
        <subfield code="f">© 1999 Georg Thieme Verlag KG</subfield>
    </datafield>
    <datafield tag="650" ind1="1" ind2="4">
        <subfield code="a">Haematology, Transfusion Medicine</subfield>
    </datafield>
    <datafield tag="650" ind1=" " ind2="0">
        <subfield code="a">Hematology</subfield>
    </datafield>
    <datafield tag="776" ind1="0" ind2="8">
        <subfield code="i">Print</subfield>
        <subfield code="z">9783133062114</subfield>
    </datafield>
    <datafield tag="856" ind1="4" ind2="0">
        <subfield code="u">http://dx.doi.org/10.1055/b-002-46968</subfield>
        <subfield code="q">pdf</subfield>
    </datafield>
    <datafield tag="912" ind1=" " ind2=" ">
        <subfield code="a">ZDB-34-THI</subfield>
    </datafield>
</record>
{% endhighlight %}

Exemple pour un [chapitre de livre](http://dx.doi.org/10.1055/b-0034-47800)

{% highlight xml %}
<record>
    <leader>00830naa a2200253n  4500</leader>
    <controlfield tag="001">1411479572080</controlfield>
    <controlfield tag="003">Georg Thieme Verlag</controlfield>
    <controlfield tag="005">20140923153932.0</controlfield>
    <controlfield tag="007">cr</controlfield>
    <controlfield tag="008">990101s1999||||gw|a||||s|||||00||||ger||</controlfield>
    <datafield tag="020" ind1=" " ind2=" ">
        <subfield code="a">9783131874511</subfield>
    </datafield>
    <datafield tag="024" ind1="7" ind2=" ">
        <subfield code="a">10.1055/b-0034-47800</subfield>
        <subfield code="2">doi</subfield>
    </datafield>
    <datafield tag="050" ind1=" " ind2="4">
        <subfield code="a">RB45</subfield>
    </datafield>
    <datafield tag="100" ind1="1" ind2=" ">
        <subfield code="a">Begemann, Michael</subfield>
    </datafield>
    <datafield tag="245" ind1="1" ind2="4">
        <subfield code="a">Das rote Blutbild</subfield>
        <subfield code="c">Michael Begemann</subfield>
    </datafield>
    <datafield tag="250" ind1=" " ind2=" ">
        <subfield code="a">11. vollständig überarbeitete Auflage</subfield>
    </datafield>
    <datafield tag="260" ind1=" " ind2=" ">
        <subfield code="a">Stuttgart</subfield>
        <subfield code="b">Georg Thieme Verlag</subfield>
        <subfield code="c">1999</subfield>
    </datafield>
    <datafield tag="542" ind1="1" ind2=" ">
        <subfield code="f">© 1999 Georg Thieme Verlag KG</subfield>
    </datafield>
    <datafield tag="650" ind1="1" ind2="4">
        <subfield code="a">Haematology, Transfusion Medicine</subfield>
    </datafield>
    <datafield tag="650" ind1=" " ind2="0">
        <subfield code="a">Hematology</subfield>
    </datafield>
    <datafield tag="773" ind1="0" ind2=" ">
        <subfield code="a">Michael Begemann</subfield>
        <subfield code="t">Praktische Hämatologie</subfield>
        <subfield code="d">Stuttgart: Georg Thieme Verlag, 2014</subfield>
        <subfield code="o">10.1055/b-002-46968</subfield>
    </datafield>
    <datafield tag="776" ind1="0" ind2="8">
        <subfield code="i">Print</subfield>
        <subfield code="z">9783133062114</subfield>
    </datafield>
    <datafield tag="856" ind1="4" ind2="0">
        <subfield code="u">http://dx.doi.org/10.1055/b-0034-47800</subfield>
        <subfield code="q">pdf</subfield>
    </datafield>
    <datafield tag="912" ind1=" " ind2=" ">
        <subfield code="a">ZDB-34-THI</subfield>
    </datafield>
</record>
{% endhighlight %}
