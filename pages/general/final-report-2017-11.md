---
layout: page
title: Final Report, November 2017
numbering: yes
---

# Metadata Management & User Authentication, Swiss National Licences, Final Report
{:.no_toc}

Lionel Walter, Project Swissbib, Basel University Library, November 13th 2017<br>
<lionel.walter@unibas.ch>


<h2 class="nonumber">Table of contents</h2>
{:.no_toc}


1. TOC
{:toc}

---


## Management Summary

In 2015, Switzerland launched a [Swiss National Licences project](http://www.nationallizenzen.ch). This is a 2-year project, funded by [swissuniversities' program "Scientific information : Access, processing and safeguarding"](http://www.swissuniversities.ch/isci) with a total amount of 9 million Swiss Francs. 7.5 million to buy contents from publishers, 1 million to ensure preservation for the whole Switzerland and 0.5 million for the negotiations of contracts, the overall management, the metadata management and the user authentication. The project is led by the Consortium of Swiss Academic Libraries (at ETH Zurich). The metadata management and user authentication subproject have been allocated to the Swissbib team at the University of Basel. The subproject started on November 1st 2015 and ended on June 30th 2017.

More than 6 million journal articles from 4 publishers were bought (Cambridge University Press, De Gruyter, Oxford University Press and Springer).

The following goals were reached :

 * **Private users**. Every private person living in Switzerland can access the content covered by national licences, after an online registration, via the [Swissbib](https://www.swissbib.ch/Search/Results?filter%5B%5D=union%3A%22NATIONALLICENCE%22) platform.
 * **Integration in Library Systems**. For Swiss libraries which already have some kind of discovery tools, the integration of the content was simplified with the central creation of KBART journals title list and the creation of dedicated targets in various tools (like ExLibris SFX).
 * **Implementation of Green Open Access conditions**. The National Licences contracts permit the secondary publication (green open access) of articles from Swiss Institution Authors, using the publisher's pdf. Each licence has specific terms and embargoes. 15'700 publications that fulfills the licences conditions have been published open access in the [RERO DOC](http://doc.rero.ch/collection/NATIONAL_LICENCES) repository. They are also ready for the integration in the various institutional repositories in Switzerland.
 * **Open and Raw Metadata**. Working with the raw metadata from the publishers (not via vendors) allowed us to redistribute this metadata via the standard Swissbib channel : the SRU API and as Linked Open Data. It also allowed us to deliver new services, like the mining of author affiliations to implement green open access conditions.

Most of these goals were achieved using existing infrastructures like Swissbib, SWITCH edu-ID or RERO DOC, but with reinforced collaboration. All implementations have been done open source. Therefore, these new services can be reused, for example :

 * to provide remote access to digital collections for private users (for example registered users of a specific library)
 * to ease the integration of digital collections licensed by the consortium in the various library systems
 * to implement open access conditions from upcoming consortial licences

---

## Facts and Figures


### Journal Articles
 * **6'250'000** journal articles available nationwide via [National Licences in Swissbib](https://www.swissbib.ch/Search/Results?filter%5B%5D=union%3A%22NATIONALLICENCE%22)
 * **15'700** journal articles available Open Access in [RERO Doc](http://doc.rero.ch/collection/NATIONAL_LICENCES)

### Publishers

|Publisher       |Number of journals       |Number of articles      |Years available (status 30.8.2017)     |Moving Wall|Next addition|Metadata licence|
| :------------- | -------------: | -------------: | :---------: | ---| -- |------------- | ------------- | ------------- | ---|
|Cambridge University Press|390|1’100’000|1770-2015|5 years|1.1.2022 : year 2016 available|CC0 with special mentions|
|De Gruyter|352|450'000|1826-2015|2 years|1.1.2019 : year 2016 available|CC0|
|Oxford University Press|292|1’200’000|1895-2015|3 years|1.1.2020 : year 2016 available|CC-BY-NC|
|Springer|1'590|3’500’000|1832-2011|4 years|fall 2017 : year 2012 available, 1.1.2018 : year 2013 available|restrictive licence from Springer|
|**Total**|2'624|6’250’000|||||


### Private Users

#### Registered private Users via Swissbib

 * **1'013** private users have or have had an access to national licences content since the beginning (status 22.8.2017)
 * **694** private users requested a temporary access
 * **651** private users have a permanent access
 * **319** private users have a permanent access without any temporary access
 * **362** private users activated a temporary access but never verified their home postal address


#### Private users Downloads

 * **1'903** Downloads of Full-Text (without Cambridge University Press where numbers are missing)

Publisher's details :
 * De Gruyter : **648** Full-Text Article Requests (COUNTER 4 JR1, status 22.8.2017)
 * Oxford University Press : **884** Full-Text Article Requests (COUNTER 4 JR1, status 31.7.2017)
 * Springer :  **371** Full-Text Article Requests (COUNTER 4 JR1, status 31.7.2017, only 4 months)
 * Cambridge : numbers missing



---


## Authentication

There were two main questions on this topic :

 1. How can private users authenticate themselves on publisher's platforms ?
 2. How can we verify that they live in Switzerland, as required by the contracts ?

The starting point was a meeting with Switch on February 2nd 2016. This made it possible to write requirements for publishers regarding these topics.

The answer to the first question was the following : private users will use the new SWITCH edu-ID Identity Provider from Switch to authenticate themselves (using SAML/Shibboleth) on publisher's platforms. The publishers need to support the value `urn:mace:dir:entitlement:common-lib-terms` in the SAML attribute `eduPersonEntitlement`. This ensures the maximum privacy of the users. The publishers know almost nothing about the user.

Another option considered was to set-up a proxy (for example EZ Proxy) for the national licences contents. This was the option chosen by the German National Licences. The main drawbacks of this solution are :

 * need to build and maintain an EZProxy server
 * private users can not authenticate themselves directly on the publisher's platform. They need first to come to the proxy.

The main advantage is that there are no specific requirements or additional work to be done on the publisher's platform. For example, it can cover platforms which are not Shibboleth compatible.

For the second question, we explored various ways :

 * check that the IP address of the device is based in Switzerland (as is done by the Cochrane National Licence from the SAMW). This was rejected by publishers, mainly because it is too easy to bypass.
 * check that the person has a Swiss mobile phone number by sending an SMS with a code
 * check that the person has an address in Switzerland by sending a letter per post

After negotiations with publishers, they agreed to a 14 days temporary access based on the verification of a Swiss mobile phone number and a permanent access delivered after checking the residency per post. This way, immediate access is possible for a user which wants to read the content at the moment he discovered it.

We had then two additional meetings with Switch to see if the SWITCH edu-ID framework fulfills all needs of the Swiss National Licences. The conclusion was that the main authentication features (user management, passwords, verified mobile phone number, verified post address, attribute `eduPersonEntitlement`) are dealt with by Switch. But some of the requirements are specific to National Licences. Indeed, the following conditions need to be met to access content from Swiss National Licences :

  - User needs to accept terms and conditions for Swiss National Licences
  - User must have a SWITCH edu-ID account
  - User must have in his SWITCH edu-ID account a verified Swiss mobile phone number and must have requested his unique temporary access in the last 14 days **OR** User has a verified postal address in Switzerland
  - User must not have been blocked by national licences administrators
  - User must have used his SWITCH edu-ID account in the last 12 months

This specific logic couldn't be implemented directly in SWITCH edu-ID, which remains a generic identity provider. The duties of Swissbib, SWITCH edu-ID and the Consortium were clarified and the implementation was done between June and December 2016.

![Registration Flow Chart]({{ site.github.url }}/public/images/flow-chart.png)

### The Registration Process in a Video

Watch the video :

[![Video]({{ site.github.url }}/public/images/video.png)](https://www.youtube.com/watch?v=dKN0u6wxGbE)

### Technical details

The whole process is best described in the [slides from the AAI & Swiss edu-ID Update 2016](https://www.switch.ch/aai/support/presentations/update2016/04_Nationallicences.pdf).

The details on how to set up `eduPersonEntitlement` via SWITCH API for SWITCH edu-ID users are available in [Swissbib Documentation](http://www.swissbib.org/wiki/index.php?title=Switch-Edu-ID).

![Architecture]({{ site.github.url }}/public/images/swissbib-switch-edu-id.png)

Every night, we update the attributes (for example to check if a user has received the verification letter) using the [Shibboleth Back-Channel](http://www.swissbib.org/wiki/index.php?title=Switch_Shibboleth_Backchannel_and_Attribute_Query_Plugin).

On top of that, to have a better user experience, we implemented two features from SWITCH for a better integration of Services (like Swissbib) within the SWITCH edu-ID framework, where most of the user information is stored. First, we implemented [customized SWITCH edu-ID forms](https://forge.switch.ch/projects/edu-id/wiki/Swiss_edu-ID_Registration_Form_Parameters), so that login and registration forms have some explanations from the service :

![Customized SWITCH edu-ID Menu]({{ site.github.url }}/public/images/switch-edu-id-customizations.png)

Additionally, when we missed an attribute from a user (for example the home postal address), we used the [SWITCH edu-ID Attribute Completion Flow](https://forge.switch.ch/projects/edu-id/wiki/Swiss_edu-ID_Attribute_Completion_Flow) to simplify the travels of the user between Swissbib and the SWITCH edu-ID interface, where he can adds new attributes. This can be seen in the above video, when the user adds his mobile number (starting at 2'09).

### Improvements done in 2017

After the go live in December 2016, the system was reviewed by an external company, specialized in User Experience. Switch and Swissbib implemented most of their recommendations in Spring 2017. The user experience was then much better. Some of the improvements include :

 * better user guidance (better hint texts, better information about the next steps, ...)
 * consistent wordings between SWITCH and Swissbib
 * better handling of terms of use
 * no need to enter the password multiple times (in SWITCH and Swissbib)
 * 3 languages support (german, french, english). Italian implemented in Swissbib but not yet in SWITCH.
 * no need to activate the temporary or permanent access manually. If a Swiss phone number is available, the temporary access is automatically activated. As soon as the postal address has been verified, the permanent access is granted.
 * after receiving the letter and verifying the code, the user is automatically redirected to Swissbib


### Perspectives

This system allows private users to access subscription content on the internet with a Shibboleth/SAML authentication. For National Licences, the rule was that the person must live in Switzerland. But this framework with Switch edu-ID and a registration service can be extended to other use cases, for example to allow patrons registered at a specific library to access content on publisher's platforms. The Zentralbibliothek Zürich, the BCU Fribourg and the ZHB Luzern have already expressed their interest for such a solution for their patrons. This is currently under evaluation.

---

## Metadata Management

### Work on the Publisher side

#### Metadata requirements, Negotiation with publishers, and Metadata Quality Control

This was covered extensively in the [mid-project report](http://swissbib.github.io/metadataNationalLicencesDocumentation/pages/general/summary-2016-06/#work-on-the-publisher-side).



### Work on the Technical side

The code for this part has been released on [Github](https://github.com/swissbib/metadataNationalLicences) as well as in the [technical documentation](https://github.com/swissbib/metadataNationalLicencesDocumentation).

#### Pivot format

The goal was to transform all incoming metadata into a common format (pivot format). Once we have the metadata in the pivot format, we can process them using a unique workflow.

We analyzed potential candidates for a pivot format : MODS, NLM JATS, MARC21, DataCite Metadata Schema, ...

We finally decided to use the MODS format. Here are the main reasons
 * it is a standard, maintained by the Library of Congress
 * the project ISTEX which takes care of the French national licences uses it as a pivot format
 * various library systems can handle it

The main disadvantage :

 * It's sometimes not as precise as NLM JATS for journal articles

#### Workflow

Click on the following image to have a hyperlinked version with all details and links to the code and data samples :


[![Big Picture]({{ site.github.url }}/public/images/big-picture.svg)]({{ site.github.url }}/public/images/big-picture.svg)


#### Workflow for the analysis

 1. extract the files from the zip and tar files (via shell scripts)
 1. do a first analysis with shell scripts (which DTD are used, which encoding, ...)
 1. with metafacture, transform the metadata into JSON (either taking everything or some specific field)
 1. index all data in elasticsearch
 1. analyze the data in elasticsearch
 1. export the results and the title lists with python


#### Workflow for the import into swissbib

1. **[same as above]** extract the files from the zip and tar files (via shell scripts)
1. **[same as above]** do a first analysis with shell scripts (which DTD are used, which encoding, ...)
1. with XSLT, transform the metadata towards the pivot format MDOS
1. with fcv stylesheets (OCLC proprietary language), transform the metadata to pica+ format and import it in OCLC CBS document store
1. **[same as swissbib standard workflow]** export pica+ to solr format for swissbib search engine (using [content2SearchDocs](https://github.com/swissbib/content2SearchDocs))
1. **[same as swissbib standard workflow]** use VuFind as the front-end : <http://swissbib.ch>

As a result, the metadata from Cambridge University Press, De Gruyter and Oxford University Press were available in Swissbib on December 5th 2016. The metadata from Springer was available on March 31st 2017 (the contract with Springer was signed later than the three other contracts)


---





### Work on the Customer side

#### For private persons (in Swissbib)

All articles from national licences were integrated in the standard <http://www.swissbib.ch>. Access to the National Licences content is done through a specific facet

![Mockup with a facet]({{ site.github.url }}/public/images/swissbib-nl-facet.png)

----



#### For private persons (in Google Scholar)

To ease the discovery of National Licences for private users and at the same time offer additional services from libraries (like document delivery), we offer personalized links for Swiss residents in Google Scholar. It looks like this :

![Mockup Google Scholar]({{ site.github.url }}/public/images/google_scholar.png)

To have such a display, interested users must set in their Google Scholar personal settings that they are Swiss Residents. This was achieved using IDS SFX guest instance.


#### For private persons (other means)

Some libraries in Switzerland already have some remote services for private users. For example :

 * the University of Bern library has a service for [people living in Bern state](http://www.unibe.ch/universitaet/dienstleistungen/universitaetsbibliothek/recherche/datenbanken/ezproxy/index_ger.html). Authentication technology : EZProxy.
 * the ETH library has a service called [E-Lending](http://www.library.ethz.ch/en/Services/Using-ordering-resources/E-Lending) for its external patrons. Authentication technology : Shibboleth via the specific Identity Provider libraries.ch
 * the EPFL has a service for its [alumni](https://www.epflalumni.ch/scientific-informations/). Authentication technology : Shibboleth via the EPFL Identity provider.

The various institutions want that their patrons can access the content through these means as well. For Shibboleth authentication, the requirement is to be in the Switch federation which is usually the case. For EZProxy authentication, the IP address of the EZProxy server must be declared in the national licences. This is often the case, because these servers are normally in the standard IP range of the universities.

Additionally, it must be ensured that the conditions of the contracts are met by these various services (for example residency in Switzerland). Usually this is the case as well.

#### Journals title lists (for example for Library Discovery tools)

Extracted from the article metadata, title lists at the journal level in Excel and KBART formats have been generated and published on the  [consortium website](http://www.consortium.ch/title-lists-for-swiss-national-licences/?lang=en). These lists make the integration in the various tools easier.

[![Title lists on the consortium website]({{ site.github.url }}/public/images/title-lists.png)](http://www.consortium.ch/title-lists-for-swiss-national-licences/?lang=en)

As ExLibris SFX is one of the main tool used in Switzerland, we took contact with ExLibris to have the possibility to create dedicated targets for Swiss National Licences in the SFX KnowledgeBase. This way, the updates can be applied centrally and take effect for all libraries which use SFX. The requirement from ExLibris was to have title lists in KBART format. We complied and the targets were created at the beginning of June 2016 :


![Swiss targets in SFX]({{ site.github.url }}/public/images/4_swiss_targets_SFX.png)

We can update Swiss National Collections centrally by depositing KBART files on ExLibris FTP server.

With the help of various libraries in Switzerland, it was also possible to create dedicated "packages" in different other tools :

 * Proquest Intota (with the UB Bern)
 * Elektronische Zeitschriftenbibliothek EZB (with the UZH-Hauptbibliothek, Zentralbibliothek Zürich and HSG Bibliothek)            
 * Ebsco Discovery (with the PHSG Bibliothek)

##### Discussion

The centralization and standardization of journals title lists from consortium licences gained very positive feed-back from the libraries. Up to now, every library needed to process the lists provided by the publishers to the consortium. On top of that, every year, there are addendums and changes to the contracts, therefore it is usually a quite time-consuming task. With the centralization, this becomes a one-click action for every library.

This process is also gaining momentum in other countries. The pioneer is the [Knowledge Base+ Project](https://www.kbplus.ac.uk/kbplus/) from JISC in the UK. The Swedish consortium BIBSAM has a partnership with Knowledge Base+ to have standardized title lists and targets. The French project [Bacon](https://bacon.abes.fr/) from the ABES is similar. They used the lists from Knowledge Base+ for international publishers and provided KBART lists and specific targets for French publishers, in strong cooperation with the publishers (see [this post](https://fil.abes.fr/2016/06/20/bacon-bilan-detape-sur-le-perimetre-couvert/) for more information).

The main problem in creating journal title lists based on publisher's article metadata is the history if journal titles.

To understand it more closely, let's take an example :


> Sprachliche Bedingungen der Wortwahl  
> STUF-Language Typology and Universals, 1966  
> Georg Michel  
> http://dx.doi.org/10.1524/stuf.1966.19.16.213

On the publisher's platform (De Gruyter), you can see as "citation information" :
STUF - Language Typology and Universals. Volume 19, Issue 1-6, Pages 213–240, ISSN (Online) 2196-7148, ISSN (Print) 1867-8319

But if you look more closely (looking at the pdf of the front matter), at that time :
the name of the journal was : Zeitschrift für Phonetik Sprachwissenschaft und Kommunikationsforschung. The ISSN at that time was : 0044-331X.

In the article metadata from De Gruyter as well as on the platform, you can never find the journal Zeitschrift für Phonetik Sprachwissenschaft und Kommunikationsforschung and the ISSN 0044-331X

In Primo Central, the article is described as part of "STUF - Language Typology and Universals"
<http://www.library.ethz.ch/DADS:Primo_Central:TN_crossref10.1524/stuf.1966.19.16.103>

In Google Scholar, the article is also described as part of "STUF - Language Typology and Universals" :
<https://scholar.google.ch/scholar?hl=fr&q=Sprachliche+Bedingungen+der+Wortwahl&btnG=&lr=>

Therefore we did the same for Swissbib : <https://www.swissbib.ch/Search/Results?lookfor=nationallicencegruyter101524stuf19661916213>

Is that right ? What is the truth : print or online ? This question remains unanswered...

But for Journals title lists, this might be more important than for the article metadata (for example to compare print and online holdings). The current journals title lists for Swiss National Licences don't reflect correctly the print history, but they reflect closely what is on the publisher's platform.

To have a better title history for journals list, the best way would be to use the [public master lists from Knowledge Base+](https://www.kbplus.ac.uk/kbplus/publicExport) and to apply on those lists the years licensed in the frame of Swiss National Licences. Unfortunately, it was not possible to achieve this task during the project. But we might switch to this process in the ongoing operation.

In the future, it might be a good idea to have centralized management of title lists and specific targets/packages for all consortial licences, as it is done in the UK and in France.


### Other means of delivering the metadata

All the metadata at the article level can be retrieved via the [Swissbib SRU API](http://sru.swissbib.ch/) in various formats :

*   xml marc : [one record](http://sru.swissbib.ch/sru/search/defaultdb?query=+dc.id+%3D+379420546&operation=searchRetrieve&recordSchema=info%3Asrw%2Fschema%2F1%2Fmarcxml-v1.1-light&maximumRecords=10&startRecord=0&recordPacking=XML&availableDBs=defaultdb&sortKeys=Submit+query), [whole collection](http://sru.swissbib.ch/sru/search/defaultdb?query=+dc.xNetwork+%3D+NATIONALLICENCE&operation=searchRetrieve&recordSchema=info%3Asrw%2Fschema%2F1%2Fmarcxml-v1.1-light&maximumRecords=10&startRecord=0&recordPacking=XML&availableDBs=defaultdb&sortKeys=Submit+query)
*   marc in json : [one record](http://sru.swissbib.ch/sru/search/defaultdb?query=+dc.id+%3D+379420546&operation=searchRetrieve&recordSchema=info%3Asru%2Fschema%2Fjson&maximumRecords=10&startRecord=0&recordPacking=XML&availableDBs=defaultdb&sortKeys=Submit+query), [whole collection](http://sru.swissbib.ch/sru/search/defaultdb?query=+dc.xNetwork+%3D+NATIONALLICENCE&operation=searchRetrieve&recordSchema=info%3Asru%2Fschema%2Fjson&maximumRecords=10&startRecord=0&recordPacking=XML&availableDBs=defaultdb&sortKeys=Submit+query)
*   dublin core : [one record](http://sru.swissbib.ch/sru/search/defaultdb?query=+dc.id+%3D+379420546&operation=searchRetrieve&recordSchema=info%3Asru%2Fschema%2F1%2Fdc-v1.1-light&maximumRecords=10&startRecord=0&recordPacking=XML&availableDBs=defaultdb&sortKeys=Submit+query), [whole collection](http://sru.swissbib.ch/sru/search/defaultdb?query=+dc.xNetwork+%3D+NATIONALLICENCE&operation=searchRetrieve&recordSchema=info%3Asru%2Fschema%2F1%2Fdc-v1.1-light&maximumRecords=10&startRecord=0&recordPacking=XML&availableDBs=defaultdb&sortKeys=Submit+query)

Using Swissbib Linked Open Data portal, the metadata is also available :

*   [html](http://data.swissbib.ch/bibliographicResource/379420546)
*   [rdfxml](http://data.swissbib.ch/bibliographicResource/379420546.rdfxml)
*   [turtle](http://data.swissbib.ch/bibliographicResource/379420546.turtle)
*   [json-ld](http://data.swissbib.ch/bibliographicResource/379420546.jsonld)
*   [n-triples](http://data.swissbib.ch/bibliographicResource/379420546.ntriples)

On top of that, upon request, the Swissbib team can deliver the metadata in MODS or JATS (except for Springer) formats.

A publication of a full export on the <http://opendata.swiss> portal is under consideration.

---

### Collaborations


#### Discussion with international partners

In January 2016, we had exchanges with colleagues from Canada, France and Germany dealing with similar projects. The summary of the findings has been published on [swissbib blog](http://swissbib.blogspot.ch/2016/03/national-licences-and-article-metadata.html).

The French project ISTEX helped us a lot by sharing their XSLT transformations of Publisher's metadata, that we could use directly.


---

## Green Open Access

### Defining what publications are concerned

The National Licences contracts permit the secondary publication (green open access) of articles from Swiss Institution Authors, using the publisher's pdf. Each licence has specific terms and embargoes. Therefore, the first task was to identify the publications, where these conditions apply.

Having processed the raw metadata from the publishers was very helpful with that matter, as we had all affiliations information from the publishers. Here is the percentage of articles which have affiliations fields for all publishers :

|Cambridge|De Gruyter|Oxford|Springer|
| :-------------: | :-------------: | :-------------: | :----: |
|58%|18%|83%|78%|

The first thing to do was to match the affiliations with the universities of Switzerland. A small [algorithm](https://github.com/swissbib/metadataNationalLicences/blob/1.0/python/extractAndMatchSwissPublications.py#L37) was developed to match the publications, based on the name variants of the institutions as well as the email address of authors. This was based on extensive discussion with the members of Arbeitskreis Open Access (AKOA). On top of the that the authors of the study :

>Alexander Machado, Laura Hoppmann, Johannes Knaus, Margit Palzenberger.
>Bibliometric study of the Swiss Publication System, 2016.
><http://doi.org/10.5281/zenodo.167381>

shared their algorithms with us.

Such an algorithm is never 100% accurate, there are always some publications missing or wrongly matched. On top of that, the way to deal with affiliations is [not really standardized](http://swissbib.github.io/metadataNationalLicencesDocumentation/pages/input/021jats/#way-to-deal-with-affiliations) on the publisher side. Nonetheless, it was possible to identify more than 15'700 publications from authors from Swiss Institutions that could be published open access. 2'000 of them have an embargo that will expire at the latest in 2020.

Please note that this applies only to Cambridge, De Gruyter and Oxford. The Springer Green Open Access clause was signed only in July 2017 and the fulltexts weren't delivered. This might happen at a next stage. A first estimation is that 15'000 articles from Springer might be published open access.


### Delivery of fulltexts

To implement green open access with the publisher's pdf, we needed a delivery of the pdfs from the publishers.

#### Cambridge University Press

Cambridge University Press allowed us to automatically download the fulltexts from "swiss" authors directly from their web platform. This is a very convenient method. The disadvantage is that there is a watermark on the pdf.

#### De Gruyter

De Gruyter delivered us all the pdf's of the Swiss National Licence via an FTP server. As the structure of the folders and files was exactly the same as for the metadata they delivered one year earlier, it was very easy to match the publications with the fulltexts.

#### Oxford University Press

Oxford University Press sent us per post a 1 Gb hard-drive containing all the pdf's of the Swiss National Licence. The problem with that delivery is that they used a completely different structure for the fulltexts as the one used for the metadata. To make it clearer, let's take an example.

For the following article *Culley, T. M., Sbita, S. J., & Wick, A. (2007). Population Genetic Effects of Urban Habitat Fragmentation in the Perennial Herb Viola pubescens (Violaceae) using ISSR Markers. Annals of Botany, 100(1), 91–100. https://doi.org/10.1093/aob/mcm077*

 * The metadata was described in the file `/ANNBOT/annbot100-1/abstracts/mcm070.xml`
 * The fulltext was in the file  `/Annals of Botany/annbot_100_1/mcm070.pdf`

There was no consistency with the `-` and `_` in the folders names. Only the filenames were consistent, but not unique. At the end we finally used the journal name and the filename for the matching, but this was time-consuming.

#### Springer

Springer hasn't delivered the fulltexts at the time of this writing.

### Publication in RERO DOC, OAI sets and lists for each institution

After discussion with the AKOA, the publishers and RERO, it was decided that the first step would be to publish these 15'700 publications open access in the RERO DOC open access respository. From there, every institution can harvest its own content and import in its repository.

The process was the following :

1. for the matching publications, export the metadata from Swissbib
1. add the fulltext, the end of embargo date and the matching institution(s)
1. import in RERO DOC
1. create dedicated OAI-sets for each institution in RERO DOC

---

In July 2017, the publications were added to [RERO DOC](http://doc.rero.ch/collection/NATIONAL_LICENCES).

![Open Access Content from National Licences in RERO DOC]({{ site.github.url }}/public/images/rero-doc-national-licences.png)

---

After the publication in RERO Doc, lists and OAI sets were made available on the dedicated open access page on the consortium website :

[![Lists for each institution]({{ site.github.url }}/public/images/open-access-lists.png)](http://www.consortium.ch/open-access/?lang=en)

---

Using a well established repository like RERO Doc ensured a very good visibility. A couple of days later, the articles were referenced in Google Scholar.

![Open Access Content from National Licences in Google Scholar]({{ site.github.url }}/public/images/google-scholar-rero-doc.png)


### Related projects & Perspectives

This problem is very relevant in the academic libraries right now. Germany has a similar project called [Deep Green](https://www.oa-deepgreen.de/) and UK as well with [PubRouter](https://pubrouter.jisc.ac.uk/). Deep Green has partnerships with the publishers Karger, Sage, De Gruyter. PubRouter has partnerships with eLife, PLOS and SpringerNature. Deep Green is in its pilot phase. A stronger collaboration with these projects might be very relevant in the future.

Additionally, the infrastructure used for National Licences could be reused for upcoming Consortium Licences with Open Access conditions.



---



## Publications & Documentation

**Code**

 * [Metadata Management National Licences](https://github.com/swissbib/metadataNationalLicences)
 * [Registration in VuFind](https://github.com/swissbib/vufind/blob/master/module/Swissbib/src/Swissbib/Services/NationalLicence.php)

**Presentations**

 * [AAI & Swiss edu-ID Update Event 2016](https://www.switch.ch/aai/support/presentations/update2016/04_Nationallicences.pdf)

**Reports**

 * [Mid-project report](http://swissbib.github.io/metadataNationalLicencesDocumentation/pages/general/summary-2016-06)

**Documentation**

 * [National Licences Technical Documentation](http://swissbib.github.io/metadataNationalLicencesDocumentation/)
 * [Connection between Swissbib and SWITCH edu-ID](http://www.swissbib.org/wiki/index.php?title=Switch-Edu-ID)
 * [Shibboleth Back-Channel](http://www.swissbib.org/wiki/index.php?title=Switch_Shibboleth_Backchannel_and_Attribute_Query_Plugin)
 * [Customized SWITCH edu-ID forms](https://forge.switch.ch/projects/edu-id/wiki/Swiss_edu-ID_Registration_Form_Parameters)
 * [SWITCH edu-ID Attribute Completion Flow](https://forge.switch.ch/projects/edu-id/wiki/Swiss_edu-ID_Attribute_Completion_Flow)
