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

### Compatibility

NLM 2.1 est valide par rapport à NLM 2.2., ...

Mais à partir de 3.0, cela ne marche plus. Les principaux changements :

 * New container elements (exemple les titres sont regroupés dans <title-group>). For example, all translated titles used to be followed by all translated subtitles. Now, a translated title and its subtitle are grouped into a single, overarching container so that a title and its subtitle can be distinguished from all other title/subtitle pairs.
 * Other example : for example, the <copyright-statement> inside <article-meta> is now allowed only inside <permissions> and not also as a direct child of <article-meta>.

NLM 3.1 = JATS 0.4


### Way to deal with affiliations

Publishers are really creative with this respect. Here are various ways :

Aff within the same contrib-group :

{% highlight xml %}
<contrib-group>
<contrib contrib-type="author" corresp="yes" xlink:type="simple">
<name name-style="western"><surname>Chen</surname><given-names>Zhihua</given-names></name>
</contrib>
<aff>Shanghai University of Finance and Economics</aff>
</contrib-group>
<contrib-group>
<contrib contrib-type="author" xlink:type="simple">
<name name-style="western"><surname>Lookman</surname><given-names>Aziz A.</given-names></name>
</contrib>
<aff>AIG</aff>
</contrib-group>

{% endhighlight %}

Aff with rid

{% highlight xml %}
<contrib-group>
<contrib contrib-type="author" xlink:type="simple">
<name name-style="western"><surname>Freitas</surname><given-names>Sandra</given-names></name>
<xref ref-type="aff" rid="af1">1</xref>
<xref ref-type="aff" rid="af2">2</xref>
<xref ref-type="aff" rid="af3">3</xref>
</contrib>
<contrib contrib-type="author" xlink:type="simple">
<name name-style="western"><surname>Prieto</surname><given-names>Gerardo</given-names></name>
<xref ref-type="aff" rid="af4">4</xref>
</contrib>
<contrib contrib-type="author" xlink:type="simple">
<name name-style="western"><surname>Simões</surname><given-names>Mário R.</given-names></name>
<xref ref-type="aff" rid="af2">2</xref>
<xref ref-type="aff" rid="af3">3</xref>
</contrib>
<contrib contrib-type="author" xlink:type="simple">
<name name-style="western"><surname>Santana</surname><given-names>Isabel</given-names></name>
<xref ref-type="aff" rid="af1">1</xref>
<xref ref-type="aff" rid="af5">5</xref>
<xref ref-type="aff" rid="af6">6</xref>
</contrib>
<aff id="af1"><label>1</label><addr-line>Centre for Neuroscience and Cell Biology (CNC)</addr-line>, <institution xlink:type="simple">University of Coimbra</institution>, <addr-line>Coimbra</addr-line>, <country>Portugal</country></aff>
<aff id="af2"><label>2</label><institution xlink:type="simple">Centro de Investigação do Núcleo de Estudos e Intervenção Cognitivo Comportamental (CINEICC)</institution>, <institution xlink:type="simple">University of Coimbra</institution>, <addr-line>Coimbra</addr-line>, <country>Portugal</country></aff>
<aff id="af3"><label>3</label><addr-line>Psychological Assessment Lab., Faculty of Psychology and Educational Sciences</addr-line>, <institution xlink:type="simple">University of Coimbra</institution>, <addr-line>Coimbra</addr-line>, <country>Portugal</country></aff>
<aff id="af4"><label>4</label><addr-line>Departamento de Psicología Básica, Psicobiología y Metodología de las Ciencias del Comportamiento</addr-line>, <institution xlink:type="simple">Universidad de Salamanca</institution>, <addr-line>Salamanca</addr-line>, <country>Spain</country></aff>
<aff id="af5"><label>5</label><addr-line>Neurology Department</addr-line>, <institution xlink:type="simple">Centro Hospitalar e Universitário de Coimbra</institution>, <addr-line>Coimbra</addr-line>, <country>Portugal</country></aff>
<aff id="af6"><label>6</label><addr-line>Faculty of Medicine</addr-line>, <institution xlink:type="simple">University of Coimbra</institution>, <addr-line>Coimbra</addr-line>, <country>Portugal</country></aff>
</contrib-group>
{% endhighlight %}

Aff separated by ;

{% highlight xml %}
<contrib-group>
<contrib contrib-type="author" corresp="yes" xlink:type="simple">
<name name-style="western"><surname>Chung</surname><given-names>Kyuil</given-names></name>
</contrib>
<contrib contrib-type="author" xlink:type="simple">
<name name-style="western"><surname>Lee</surname><given-names>Jong-Eun</given-names></name>
</contrib>
<contrib contrib-type="author" xlink:type="simple">
<name name-style="western"><surname>Loukoianova</surname><given-names>Elena</given-names></name>
</contrib>
<contrib contrib-type="author" xlink:type="simple">
<name name-style="western"><surname>Park</surname><given-names>Hail</given-names></name>
</contrib>
<contrib contrib-type="author" xlink:type="simple">
<name name-style="western"><surname>Shin</surname><given-names>Hyun Song</given-names></name>
<xref ref-type="fn" rid="eiv002-FN1"><sup>1</sup></xref>
</contrib>
<aff>Bank of Korea; Sejong University; Statistics Department, IMF; Bank of Korea; Princeton University</aff>
</contrib-group>
{% endhighlight %}

All the same affiliation <http://dx.doi.org/10.1093/chemse/bju026>:

{% highlight xml %}
<contrib-group>
<contrib contrib-type="author" corresp="no" xlink:type="simple">
<name name-style="western">
<surname>Spiers</surname>
<given-names>Jereme G.</given-names>
</name>
</contrib>
<contrib contrib-type="author" corresp="no" xlink:type="simple">
<name name-style="western">
<surname>Chen</surname>
<given-names>Hsiao-Jou Cortina</given-names>
</name>
</contrib>
<contrib contrib-type="author" corresp="no" xlink:type="simple">
<name name-style="western">
<surname>Sernia</surname>
<given-names>Conrad</given-names>
</name>
</contrib>
<contrib contrib-type="author" corresp="yes" xlink:type="simple">
<name name-style="western">
<surname>Lavidis</surname>
<given-names>Nickolas A.</given-names>
</name>
</contrib>
<aff id="AF0001">
<institution xlink:type="simple">School of Biomedical Sciences, The University of Queensland</institution>, <addr-line>St Lucia</addr-line>, <addr-line>Brisbane, Queensland 4072</addr-line>, <country>Australia </country>
</aff>
</contrib-group>
{% endhighlight %}

Only the order has some importance <http://dx.doi.org/10.1093/jos/16.1.1>:

{% highlight xml %}
<contrib-group>
    <contrib contrib-type="author" xlink:type="simple">
        <name name-style="western"><surname>DE SWART</surname><given-names>HENRIËTTE</given-names></name>
    </contrib>
    <contrib contrib-type="author" xlink:type="simple">
        <name name-style="western"><surname>MOLENDIJK</surname><given-names>ARIE</given-names></name>
    </contrib>
    <aff><institution xlink:type="simple">Utrecht University</institution></aff>
    <aff><institution xlink:type="simple">University of Groningen</institution></aff>
</contrib-group>

{% endhighlight %}

Plusieurs adresses dans le même `<aff>``

{% highlight xml %}
<aff>
    <target id="AFF1" target-type="aff"/>
    <label>1</label>
    Mathematics Department, University of British Columbia, Vancouver, BC V6T 1Z2, Canada
      
    <target id="AFF2" target-type="aff"/>
    <label>2</label>
    Seminar für Angewandte Mathematik, ETH Zürich, Rämistrasse 101, 8092 Zürich, Switzerland
</aff>
{% endhighlight %}
