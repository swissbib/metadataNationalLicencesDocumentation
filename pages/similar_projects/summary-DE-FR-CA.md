---
layout: page
title: Summary Canada - France - Germany
---

# National Licences  and article metadata in Germany, Canada, France and Switzerland

See the blogpost <http://swissbib.blogspot.ch/2016/03/national-licences-and-article-metadata.html> for the published version.

## Summary National Licences

||Germany|Ontario/Canada|France|Planned for Switzerland|
| ------------- | :-------------: | :-------------: | :-------------: | :-------------: |
|Link|<http://nationallizenzen.de>|<http://scholarsportal.info>|<http://istex.fr>||
|Start year|2004|2006|2012|2015|
|Number of articles in the platform|25 million|44 million|20 million|3.5 million|
|Budget|> 120 million €||60 million €|10 million CHF|
|Main focus|access|preservation|text and data mining|access|
|Participating Publishers|~30|30|20|4|
|Pivot Format|OCLC PICA+|NLM JATS|MODS|NLM JATS|
|Fulltext (pdf) delivery on the project platform|yes, but via a proxy to the publisher's platform|yes|yes|no|
|Access for private users|yes|no|no|yes|
|Rights to share the metadata|yes|no|yes|yes|
|Language for transformation|C and Java|Java in the past, XSLT now|XSLT|XSLT|
|Document store|OCLC CBS|MarkLogic||OCLC CBS|
|Search engine technology|SOLR|MarkLogic|Elasticsearch|SOLR|
|Front-end technology|VuFind|MarkLogic|no Front-end|VuFind|

## Summary Article Indexes

Articles indexes are not bound to national licences. They contain plenty of journal articles, which can then be matched with library e-journals holdings.

||GBV Zentral|Finc|
| ------------- | :-------------: |  :-------------: |
|Link|<http://findex.gbv.de>|<http://finc.info>|
|Start year|2012|2014|
|Number of articles in the platform|130 million|80 million|
|Participating Publishers|~40|mostly via crossref|
|Pivot Format|marc21|local format|
|Rights to share the metadata|yes|yes|
|Language for transformation|C and Java|go|
|Search engine technology|SolrCloud|SOLR|
|Front-end technology|no Front-end|VuFind|



## Introduction - the Swiss Context

In 2015, Switzerland launched a [Swiss National Licences project](http://www.swissuniversities.ch/fileadmin/swissuniversities/Dokumente/DE/UH/SUK_P-2/Abstract_Nationallizenzen.pdf). This is a 2-year project, funded by [swissuniversities / program SUK-P2 "Scientific information : Access, processing and storage"](http://www.swissuniversities.ch/isci) with a total amount of 10 million Swiss Francs. 7.5 million to buy contents from publishers, 2 million to ensure preservation for the whole Switzerland (probably with Portico and LOCKSS) and 0.5 million for the negotiations of contracts, the overall management and the metadata management. The project is led by the Consortium of Swiss University Libraries (at ETH Zurich). The metadata management subproject has been allocated to the Swissbib team at the University of Basel.

Access will be possible for every partner of the Consortium : universities, universities of applied sciences, state libraries, research institutes... One of the goal is therefore to bridge the gap between "rich" and "poor" institutions in Switzerland. Interested private persons living in Switzerland can also access the content, directly from their home, after following a suitable registration.

The Swiss National licences will be coupled together with the current content licences. This process can be summarized as follows. Let's say Switzerland has a national licence for journal articles for a given publisher covering the years 1947-2008. At the same time, some universities in Switzerland have a licence for current content covering 2009-2016. At the beginning of 2017, if some universities sign for 2017 content for this publisher, then one more year will be available as part of the national licence (meaning the national license is expanding to 1947-2009). The details (when a new year is added and under which conditions) may vary from publisher to publisher, but that's the main idea.

The goals of the metadata management subproject are the following :

 * **Private users**. Build a search engine to allow private users in Switzerland to search and access the content which is licensed for them. This will be done using the Swissbib existing infrastructure. The registration and authentication mechanism will be created together with SWITCH.
 * **Integration in Library Discovery tools**. For participating libraries which already have some kind of discovery tools, the integration of content should be seamless, for example with the creation of dedicated targets in ExLibris SFX or Proquest Intota
 * **Gain experience in article metadata management**. The management of publisher's metadata at the article level didn't happen yet in Switzerland. The goal is to gain experience with this to deliver additional services later on (for example within the SLSP project) : text and data mining, discovery tools for smaller institutions (university of applied sciences) as well as a collaboration with international partners.

The contracts are not signed yet, but the goal is to sign them in Spring 2016 and have the portal live at the end of 2016. The negotiations are still happening and the contracts will be evaluated by an independent board ("Evalutionsgremium") in the coming weeks.

At the start of the project, the goal was to gather what has been done abroad with this respect. There was a telephone call with the people from Toronto, a meeting in Göttingen with the people from GBV and Finc and a meeting in Nancy with the people from INIST. All that happened in January 2016.

## Germany Nationallizenzen & Allianzlizenzen

Germany was a pioneer in national licensing. The DFG (Deutsche Forschung Gesellschaft) project [German National Licences](http://www.nationallizenzen.de/) was launched in 2004 and followed in 2011 by the so called Allianz-Lizenzen. The National Licences were funded only by the DFG. The content licensed is accessible in the whole Germany. The Allianz-Lizenzen are funded at 25% by the DFG and at 75% by participating universities. The contents licensed are available only to participating institutions. After a couple of years (so called Moving Walls whose duration depends on the publishers), an Allianz Licence becomes a National Licence, and access is then granted to the whole Germany. Since the beginning of the project, Germany has been spending more than 120 million Euros on the various projects. The negotiations are done by 8 libraries in Germany and the metadata handling is done by the GBV (Gemeinsamer Bibliotheksverbund) in Göttingen.

Currently, they have managed the metadata of **~25 million** journal articles (and other kind of content like book chapters). They got the metadata directly from the publishers. In the first years, processing this metadata was really a pain, but it has improved in recent years. They transform all metadata in OCLC PICA+ format and store it in OCLC CBS software. Access is done through the [Suchkiste](http://finden.nationallizenzen.de) via a VuFind interface and a SOLR index. They loaded all content in the Suchkiste in 2010, but haven't updated yet because this wasn't a priority.

Interested libraries can download article metadata in MARC21 format (as an export from OCLC CBS) from the GBV. They can also access directly the [GBV Zentral Index (SOLR)](http://findex.gbv.de). The metadata is available to everybody. The description of the collections (journal holdings) is in EZB, the German electronic journals database.

Regarding the fulltexts (pdf), access is done on the Publisher's Platform directly, but the GBV store the pdf as well in case of failure. This amounts yet to 60 TB of data. In the contract for national licences, it was mandatory for the publishers to deliver the pdf on their own platform for the next 10 years.

The access is also possible for private users who live in Germany. The person needs to register online and give its private home address. The registration is than quickly checked by one of the 8 libraries (depending on the first letter of the last name) which subsequently sends a letter by post to the person. Password for login is enclosed in the letter. This process can last up to 10 days. At the time of the registration, the user must say which publisher he is interested in, because each of them have different conditions. Access is then done via a Shibboleth authentication to a proxy at GBV to access the National Licences content. On some publishers platform, it is also possible to login directly via Shibboleth. Since the beginning of the project, there has been more or less every year **8000 private active users**. Every year 2000 more are added, and 2000 are removed because they are inactive.

### Links

 * [Suchkiste : search engine for German national licenses](http://finden.nationallizenzen.de)
 * [GBV Zentral Index](http://findex.gbv.de)
 * [List of partner publishers](https://www.gbv.de/wikis/cls/Findex.gbv.de#Nationallizenzen:_GBV_Zentral_Produkt.C3.BCbersicht)
 * [How to search national licences in EZB](http://www.zeitschriftendatenbank.de/de/suche/zdb-katalog/national-und-allianz-lizenzen/)
 * [Description of a specific package in EZB](http://dispatch.opac.dnb.de/DB=1.2/SET=1/TTL=4/CMD?ACT=SRCHA&IKT=8521&SRT=LST_os&TRM=+ZDB-1-SOJ+)


## Ontario/Canada ScholarsPortal project
[The ScholarsPortal project from Ontario/Canada](http://journals2.scholarsportal.info) started in 2006. They deliver content (metadata + fulltext) to the members of all universities in the province of Ontario, in Canada. Meanwhile, they have worked with over 35 academic publishers and aggregators that are able to deliver article metadata and fulltext. After a focus on access in the first years, recently they invested more in the preservation aspects. They are now an audited *trustworthy digital repository* and act as a preservation agent for all university libraries of Ontario (ISO 16363, known as the Trusted Digital Repository Checklist). Currently ~3 persons (rather 3 FTE) are working for the journals part of Scholars Portal.


They have managed the metadata and fulltext of **~44 million** journal articles. They get the metadata directly from publishers. They transform everything into NLM JATS format using either plain Java programming or XSLT stylesheets (in the recent years). Data is then stored in a MarkLogic Server, which is also used to search (via xQuery) and deliver content. For the last couple of years, they have also been processing eBooks, using the NLM BITS format. They even provide a [navigation by Volume/Issue](http://journals1.scholarsportal.info/browse/01678094/v19i0002), using additional normalization rules. For libraries, they create dedicated targets in ExLibris SFX link resolver as well as in Serial Solutions knowledgebase, 360 Core. A researcher in Ontario can access the fulltexts (pdf or XML) either on the publisher’s platform or directly in the Scholars Portal. They observed differences in behavior between small and big universities. Users from larger universities tend to prefer publisher’s platforms whereas  users from smaller institutions download a majority of content directly from Scholars Portal. On Scholars Portal, even the links (citations) between articles can be resolved internally in the portal.

They don’t have the rights to share metadata with libraries outside the consortium, but if a specific publisher agrees, on their side they are ready to share.

### Links


* [ScholarsPortal](http://journals2.scholarsportal.info)
* [Internal wiki with a lot of information](https://spotdocs.scholarsportal.info/)
* [List of publishers loaded](https://spotdocs.scholarsportal.info/display/EJournals/Loaded+content)
* [Article about their processes](http://www.balisage.net/Proceedings/vol9/print/Zhao01/BalisageVol9-Zhao01.html)
* [Model for a licence](http://www.ocul.on.ca/node/114)


## France ISTEX project

The [ISTEX](http://istex.fr) project started in 2012. It is planned until 2017 and funded with 60 million Euros (55 are allocated to buy content). It is a collaboration between :

 * the [Couperin](http://www.couperin.org/) consortium which focus on collecting researchers and libraries needs
 * the [ABES](http://abes.fr) in Montpellier which does the negotiations with the publishers, as well as the signing of contracts. The integration in Knowledge Bases from Library IT Providers (such as ExLibris SFX) is also done by the ABES via the BACON project
 * the [University of Lorraine](http://www.univ-lorraine.fr/) in Nancy which is the representative of universities in the project
 * the [INIST](http://inist.fr) (from CNRS) in Nancy which is building the platform and processing publisher's metadata

They have no plans to build a portal, but really to be a data hub, with a strong focus on **Text and Data Mining**. Currently ~15 persons are working at INIST for the ISTEX project. There are 16 million documents currently in ISTEX and this will go up to **~20 million** until the end of the project. They get the metadata and fulltext directly from the publishers. They deliver the fulltext (pdf's) to the researchers as well (which is not the case in the German project for example). In the contracts with publishers, the publishers only need to deliver the fulltext on their own platform for the next five years. The ISTEX team even analyzes the text content of pdf files, using among others the GROBID software. They enrich the contents (for example with geoNames from France). They have had a lot of problems with metadata and fulltexts from publishers : invalid XML with respect to the attached DTD's, undocumented formats, strong heterogeneity of formats (even within the same journal over time), pdf of very poor quality, missing contents... In the last months, they asked the publishers to deliver the full content before signing the contract, to make sure that it is possible to work with the delivered content. They also ask the publishers to deliver a whole data package at once : metadata, fulltexts, description of the structure of the directories and filenames, list of journals with years and number of articles published, DTD's, contact of a person responsible for technical details. In some cases, it was impossible to match the metadata and pdf's. The preservation is done by another institution : the [CINES](http://cines.fr). Everything received from Publisher is kept.

They offer all the content (metadata + fulltext) via a REST API. Researchers can then mine the whole content, or a specific collection. The first users are in the domain of automated text analysis or in the history of sciences. Up to know, the usage and interest is still timid, but this is growing. Libraries can also use these API to integrate the content directly in their online tools, or using the widgets provided by the project. They plan to insert all ISTEX metadata in tools like Ebsco Discovery Service or ExLibris Primo Central.

They analyze the incoming metadata with elasticsearch and Kibana, reporting the problems to the publishers. After that, they transform everything to MODS for metadata (using XSLT stylesheets) and TEI for fulltext. If the XML is invalid, they make what is necessary to deliver valid XML at the end. Indeed, the researchers who do text and data mining can use the original format from publisher as well.

Almost all metadata is licensed with an Etalab licence (a French licence very similar to Creative Commons Zero). This means that it is possible to share metadata with other libraries, even outside France.

![Diagram ISTEX]({{ site.github.url }}/public/images/schema_istex.png "istex_diagram")


### Links

 * [Demo for istex rest api](http://demo.istex.fr)
 * [ISTEX project](http://istex.fr)
 * [ISTEX blog](http://blog.istex.fr)
 * [Politique de signalement des licences ISTEX](http://punktokomo.abes.fr/2014/02/25/politique-de-signalement-des-licences-nationales-istex/)
 * [Integration in KOHA via REST API : University of St-Etienne](https://brisees-opac.univ-st-etienne.fr/)
 * [Integration in DRUPAL via REST API : University of Rennes 2](http://www.bu.univ-rennes2.fr/istex/results?lookfor=*&type=All)
 * [Git server](https://git.istex.fr/istex)
 * [GitHub account ISTEX](https://github.com/istex)
 * [GitHub account INIST](https://github.com/Inist-CNRS)


## Article Index : GBV Zentral

After building the suchkiste for the German national licences, the GBV went one step further and decided to build an article index that contains current content as well. In 2012, they launched GBV Zentral. Now, there are 130 million articles available in GBV Zentral. There is no front-end in GBV Zentral, it is an index based on the SolrCloud technology. The print collections of all the libraries of GBV are also included in GBV Zentral. Therefore, in total there are 158 million documents in GBV Zentral. 51 million of them have some kind of searchable enrichments (table of contents, reviews, front or back matters from publishers). If a library manage its journal holdings in EZB (the German electronic journal library), then it is possible to match GBV Zentral content with the electronic collections of a specific library to add a filter in the search. 76 libraries are using GBV Zentral (either for print collections, online contents or both), for example

* [Max Planck Institute for Research on Collective Goods](http://core.coll.mpg.de) with 207 million searches per year
* [Technische Universität Ilmenau](https://find.bibliothek.tu-ilmenau.de) with 157 million searches per year
* [Universität Hamburg](https://beluga.sub.uni-hamburg.de) with 40 million searches per year

Every year more than **1.8 billion** searches are done in GBV Zentral. All the metadata comes from the publishers or some databases (like Pubmed). The process is more or less the same as for the German National Licences. The GBV Zentral is also used as a central place to deliver content to ExLibris Primo, Summon and Ebsco Discovery Service. GBV Zentral is updated daily.

Every interested institution in the world can use GBV Zentral at no cost.

![Diagram GBV Zentral]({{ site.github.url }}/public/images/GBV_Zentral_Architektur.png "GBV_Zentral_diagram")

### Links

 * [GBV Zentral Index](http://findex.gbv.de)

## Article Index : the Finc Project (Leipzig / Germany)

The [Finc](http://finc.info) Project (from the University of Leipzig in Germany) is not bound to national licences in any ways. It has a very different focus : the goal was to build a local article index, without buying one (for example ExLibris Primo Central or Proquest Summon). The focus was really on efficiency and current availability, without having to take care on preservation or that much on metadata quality. There are ~3 persons working on the project.

With this in mind, they decided to get all metadata from Crossref. Crossref is the organization which delivers DOI to scientific publishers. It means that Crossref has some metadata for every journal article which has a DOI. The main advantage is that all metadata is already in a common format (crossref unified schema) and there is only one provider to take care of. The disadvantage is that the metadata is somehow poorer than the metadata which is directly available from the publishers. For example, abstracts are often missing. After this initial step, Finc decided to get the metadata from other sources directly as well (for example from JSTOR or DeGruyter).

Currently, the finc project has gathered more than **~80 million** journal articles from crossref. They transform everything to a very simple internal flat format, using the *go* programming language. They index then all the metadata in Apache SOLR and show it to users using VuFind. There is a growing interest in Germany for the finc article index. Indeed, a library which uses VuFind as an online discovery tool can use it without too much complications. The Finc index is updated more or less on a monthly basis.

### Links

* [Project description](http://finc.info)
* [Use in Leipzig University Library online portal](https://katalog.ub.uni-leipzig.de/)
* [GitHub Finc](https://github.com/finc)
* [GitHub UB Leipzig](https://github.com/ubleipzig)
* [GitHub Martin Czygan, one of the developer](https://github.com/miku)
* [Internal format](https://github.com/miku/span/blob/master/schema/is-0.9.json)
* [Conversion from JATS in go](https://github.com/miku/span/blob/master/sources/jats/article.go)


## Implications for Switzerland

As the coverage dates for Swiss national licences (probably going up to 2015) won't completely overlap with the projects from the other countries, we will need to process at least some metadata on our side. We can count on international partners for specific problems (a very bad metadata set that has already been processed or a publisher specific format that has already been transformed to a more standard one).

Here are what we plan to do for Switzerland. First, we set up a collection of metadata requirements for publishers. Here are some of the important points :

 * all metadata should be delivered using a Creative Commons Zero Licence to allow Switzerland to process it as needed (this allows for example the transformation towards linked open data at a later standpoint)
 * the publisher needs to deliver the whole metadata set before signing the contract. This allows the swissbib team to check the quality of metadata. Experience has shown that after signature, it is often too late

On the technical side, the plans are the following : Incoming metadata will be processed using Metafacture from the German National Library and analyzed with elasticsearch. It will be then transformed using XSLT towards a standardized NLM JATS format, with some additional requirements on mandatory metadata. The documents will then be stored in OCLC CBS and delivered to the users using SOLR and VuFind (same as the currenct swissbib architecture).

Additionnally, the metadata will be available via an OAI-PMH interface, an SRU web service as well as maybe a REST API. At the journal level, holdings in KBART format will be created and delivered to Vendors of Library Software for the creation of dedicated targets in Link Resolvers and Discovery tools.



## Examples of metadata (JATS, MODS, MARC21, Crossref, finc)

As an example, here is the same article in various formats.

### NLM JATS

From De Gruyter sample data.

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<article>
    <front
        xmlns:xlink="http://www.w3.org/1999/xlink">
        <journal-meta>
            <journal-id journal-id-type="publisher-id">JMC</journal-id>
            <abbrev-journal-title abbrev-type="full">Journal of Mathematical Cryptology</abbrev-journal-title>
            <abbrev-journal-title abbrev-type="publisher">JMC</abbrev-journal-title>
            <issn pub-type="ppub">1862-2976</issn>
            <issn pub-type="epub">1862-2984</issn>
            <publisher>
                <publisher-name>Walter de Gruyter</publisher-name>
                <publisher-loc>
                    <addr-line>Genthiner Strasse 13</addr-line>
                    <addr-line>10875 Berlin</addr-line>
                    <country>Germany</country>
                </publisher-loc>
            </publisher>
        </journal-meta>
        <article-meta>
            <article-id pub-id-type="publisher-id">JMC.2007.011</article-id>
            <article-id pub-id-type="doi">10.1515/JMC.2007.011</article-id>
            <title-group>
                <article-title>Probability distributions of correlation and differentials in block ciphers</article-title>
            </title-group>
            <contrib-group>
                <contrib contrib-type="author">
                    <name name-style="western">
                        <given-names>Joan</given-names>
                        <x></x>
                        <surname>Daemen</surname>
                        <x>, </x>
                    </name>
                    <aff>STMicroelectronics, Belgium. Email:
                        <email>Joan.Daemen@st.com</email>
                    </aff>
                </contrib>
                <contrib contrib-type="author">
                    <name name-style="western">
                        <given-names>Vincent</given-names>
                        <x></x>
                        <surname>Rijmen</surname>
                    </name>
                    <aff>Graz University of Technology, Austria. Email:
                        <email>Vincent.Rijmen@iaik.tugraz.at</email>
                    </aff>
                </contrib>
            </contrib-group>
            <pub-date pub-type="ppub">
                <day>21</day>
                <month>08</month>
                <year>2007</year>
                <string-date>2007</string-date>
            </pub-date>
            <pub-date pub-type="epub">
                <day>13</day>
                <month>08</month>
                <year>2007</year>
            </pub-date>
            <volume>1</volume>
            <issue>3</issue>
            <fpage>221</fpage>
            <lpage>242</lpage>
            <copyright-statement>Copyright 2007, Walter de Gruyter</copyright-statement>
            <copyright-year>2007</copyright-year>
            <related-article related-article-type="pdf" xlink.href="jmc.2007.011.pdf" />
            <abstract>
                <p>We study the probability distributions of difference propagation probabilities and input-output correlations for functions and block ciphers of given dimensions, for several of them for the first time. We show that these parameters have distributions that are well-studied in the field of probability such as the normal, Poisson and extreme value distributions. The results of this paper can be used to estimate how much effort will be required to generate functions satisfying certain criteria. The distributions we derive for block ciphers illustrate the significant difference between fixed-key parameters and averaged parameters.</p>
            </abstract>
            <kwd-group>
                <title>Key Words</title>
                <kwd>Block ciphers,</kwd>
                <x></x>
                <kwd>probability distributions,</kwd>
                <x></x>
                <kwd>differential cryptanalysis,</kwd>
                <x></x>
                <kwd>linear cryptanalysis.</kwd>
            </kwd-group>
            <counts>
                <page-count count="22" />
            </counts>
        </article-meta>
    </front>
</article>
{% endhighlight %}

### MODS

From [ISTEX](https://api.istex.fr/document/3DA4BA1D4E0D5C558E2CF677084098CE690C9662/metadata/mods)

{% highlight xml %}
<mods
    xmlns="http://www.loc.gov/mods/v3"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:xlink="http://www.w3.org/1999/xlink" version="3.6">
    <titleInfo lang="en">
        <title>Probability distributions of correlation and differentials in block ciphers</title>
    </titleInfo>
    <titleInfo type="alternative" lang="en" contentType="CDATA">
        <title>
            <![CDATA[Probability distributions of correlation and differentials in block ciphers]]>
        </title>
    </titleInfo>
    <name type="personal">
        <namePart type="given">Joan</namePart>
        <namePart type="family">Daemen</namePart>
        <affiliation>STMicroelectronics, Belgium. Email: Joan.Daemen@st.com</affiliation>
        <affiliation>E-mail: Joan.Daemen@st.com</affiliation>
        <role>
            <roleTerm type="text">author</roleTerm>
        </role>
    </name>
    <name type="personal">
        <namePart type="given">Vincent</namePart>
        <namePart type="family">Rijmen</namePart>
        <affiliation>Graz University of Technology, Austria. Email: Vincent.Rijmen@iaik.tugraz.at</affiliation>
        <affiliation>E-mail: Joan.Daemen@st.com</affiliation>
        <role>
            <roleTerm type="text">author</roleTerm>
        </role>
    </name>
    <typeOfResource>text</typeOfResource>
    <genre type="research-article">research-article</genre>
    <originInfo>
        <publisher>Walter de Gruyter</publisher>
        <place>
            <placeTerm type="text">Genthiner Strasse 13 10875 Berlin Germany</placeTerm>
        </place>
        <dateIssued encoding="w3cdtf">2007-08-21</dateIssued>
        <dateCreated encoding="w3cdtf">2007-08-13</dateCreated>
        <copyrightDate encoding="w3cdtf">2007</copyrightDate>
    </originInfo>
    <language>
        <languageTerm type="code" authority="iso639-2b">eng</languageTerm>
        <languageTerm type="code" authority="rfc3066">en</languageTerm>
    </language>
    <physicalDescription>
        <internetMediaType>text/html</internetMediaType>
    </physicalDescription>
    <abstract lang="en">We study the probability distributions of difference propagation probabilities and input-output correlations for functions and block ciphers of given dimensions, for several of them for the first time. We show that these parameters have distributions that are well-studied in the field of probability such as the normal, Poisson and extreme value distributions. The results of this paper can be used to estimate how much effort will be required to generate functions satisfying certain criteria. The distributions we derive for block ciphers illustrate the significant difference between fixed-key parameters and averaged parameters.</abstract>
    <subject>
        <genre>Key Words</genre>
        <topic>Block ciphers,</topic>
        <topic>probability distributions,</topic>
        <topic>differential cryptanalysis,</topic>
        <topic>linear cryptanalysis.</topic>
    </subject>
    <relatedItem type="host">
        <titleInfo>
            <title>Journal of Mathematical Cryptology</title>
        </titleInfo>
        <titleInfo type="abbreviated">
            <title>Journal of Mathematical Cryptology</title>
        </titleInfo>
        <identifier type="ISSN">1862-2976</identifier>
        <identifier type="eISSN">1862-2984</identifier>
        <identifier type="JournalID">JMC</identifier>
        <part>
            <date>2007</date>
            <detail type="volume">
                <caption>vol.</caption>
                <number>1</number>
            </detail>
            <detail type="issue">
                <caption>no.</caption>
                <number>3</number>
            </detail>
            <extent unit="pages">
                <start>221</start>
                <end>242</end>
                <total>22</total>
            </extent>
        </part>
    </relatedItem>
    <relatedItem type="reviewOf">
        <genre>pdf</genre>
        <identifier type="pdf">jmc.2007.011.pdf</identifier>
    </relatedItem>
    <identifier type="istex">3DA4BA1D4E0D5C558E2CF677084098CE690C9662</identifier>
    <identifier type="DOI">10.1515/JMC.2007.011</identifier>
    <identifier type="ArticleID">JMC.2007.011</identifier>
    <identifier type="Related-article-Href">jmc.2007.011.pdf</identifier>
    <accessCondition type="use and reproduction" contentType="Copyright">Copyright 2007, Walter de Gruyter</accessCondition>
    <recordInfo>
        <recordContentSource>De Gruyter</recordContentSource>
    </recordInfo>
</mods>

{% endhighlight %}

### MARC21

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8" ?>
<marc:collection
    xmlns:marc="http://www.loc.gov/MARC21/slim"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.loc.gov/MARC21/slim http://www.loc.gov/standards/marcxml/schema/MARC21slim.xsd">
    <marc:record>
        <marc:leader>00957    a2200145   4500</marc:leader>
        <marc:datafield tag="024" ind1="7" ind2=" ">
            <marc:subfield code="a">10.1515/jmc.2007.011</marc:subfield>
            <marc:subfield code="2">doi</marc:subfield>
        </marc:datafield>
        <marc:datafield tag="041" ind1=" " ind2=" ">
            <marc:subfield code="a">eng</marc:subfield>
        </marc:datafield>
        <marc:datafield tag="100" ind1="1" ind2=" ">
            <marc:subfield code="a">Joan Daemen</marc:subfield>
        </marc:datafield>
        <marc:datafield tag="700" ind1="1" ind2=" ">
            <marc:subfield code="a">Vincent Rijmen</marc:subfield>
        </marc:datafield>
        <marc:datafield tag="245" ind1="0" ind2="0">
            <marc:subfield code="a">Probability Distributions of Correlation and Differentials in Block Ciphers.</marc:subfield>
        </marc:datafield>
        <marc:datafield tag="260" ind1=" " ind2=" ">
            <marc:subfield code="a">Berlin</marc:subfield>
            <marc:subfield code="b">Walter de Gruyter</marc:subfield>
            <marc:subfield code="c">2005</marc:subfield>
        </marc:datafield>
        <marc:datafield tag="520" ind1=" " ind2=" ">
            <marc:subfield code="a">We study the probability distributions of difference propagation probabilities and input-output correlations for functions and block ciphers of given dimensions, for several of them for the first time. We show that these parameters have distributions that are well-studied in the field of probability such as the normal, Poisson and extreme value distributions. The results of this paper can be used to estimate how much effort will be required to generate functions satisfying certain criteria. The distributions we derive for block ciphers illustrate the significant difference between fixed-key parameters and averaged parameters.</marc:subfield>
        </marc:datafield>
        <marc:datafield tag="773" ind1=" " ind2=" ">
            <marc:subfield code="g">Vol. 1, no. 3 (Aug. 2007), p. 221-242</marc:subfield>
            <marc:subfield code="t">Journal of Mathematical Cryptology</marc:subfield>
            <marc:subfield code="x">1862-2984</marc:subfield>
        </marc:datafield>
        <marc:datafield tag="856" ind1="4" ind2=" ">
            <marc:subfield code="u">http://dx.doi.org/10.1515/jmc.2007.011</marc:subfield>
        </marc:datafield>
    </marc:record>
</marc:collection>

{% endhighlight %}

### Crossref unixref

From [Crossref](http://www.crossref.org/guestquery/)

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<doi_records>
  <doi_record key="key" owner="10.1515" timestamp="2013-06-05 13:48:18">
    <crossref>
      <journal>
        <journal_metadata>
          <full_title>Journal of Mathematical Cryptology</full_title>
          <issn media_type="print">1862-2976</issn>
          <issn media_type="electronic">1862-2984</issn>
        </journal_metadata>
        <journal_issue>
          <publication_date>
            <month>01</month>
            <day>21</day>
            <year>2007</year>
          </publication_date>
          <journal_volume>
            <volume>1</volume>
          </journal_volume>
          <issue>3</issue>
        </journal_issue>
        <journal_article>
          <titles>
            <title>Probability distributions of correlation and differentials in block ciphers</title>
          </titles>
          <contributors>
            <person_name sequence="first" contributor_role="author">
              <given_name>Joan</given_name>
              <surname>Daemen</surname>
            </person_name>
            <person_name sequence="additional" contributor_role="author">
              <given_name>Vincent</given_name>
              <surname>Rijmen</surname>
            </person_name>
          </contributors>
          <publication_date>
            <month>01</month>
            <day>21</day>
            <year>2007</year>
          </publication_date>
          <doi_data>
            <doi>10.1515/JMC.2007.011</doi>
            <resource>http://www.degruyter.com/view/j/jmc.2007.1.issue-3/jmc.2007.011/jmc.2007.011.xml</resource>
          </doi_data>
        </journal_article>
      </journal>
    </crossref>
  </doi_record>
</doi_records>

{% endhighlight %}

### finc internal format

From [finc](https://katalog.ub.uni-leipzig.de/Record/ai-49-aHR0cDovL2R4LmRvaS5vcmcvMTAuMTUxNS9qbWMuMjAwNy4wMTE/Details#tabnav)

field name | value
---|---
finc.format|	ElectronicArticle
finc.mega_collection| 	Walter de Gruyter GmbH (CrossRef)
finc.record_id| 	ai-49-aHR0cDovL2R4LmRvaS5vcmcvMTAuMTUxNS9qbWMuMjAwNy4wMTE
finc.source_id| 	49
ris.type| 	EJOUR
rft.atitle| 	Probability distributions of correlation and differentials in block ciphers
rft.epage| 	0
rft.genre| 	article
rft.issn| 	1862-2976
   | 1862-2984
rft.issue| 	3
rft.jtitle| 	Journal of Mathematical Cryptology
rft.tpages| 	0
rft.pub| 	Walter de Gruyter GmbH
rft.date| 	2007-01-21
x.date| 	2007-01-21T00:00:00Z
rft.spage| 	0
rft.volume| 	1
authors| 	Daemen Joan
 | Rijmen Vincent
doi| 	10.1515/jmc.2007.011
languages| 	eng
url| 	http://dx.doi.org/10.1515/jmc.2007.011
version| 	0.9
x.type| 	journal-article
