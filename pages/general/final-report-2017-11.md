---
layout: page
title: Final Report, November 2017
numbering: yes
---

# Metadata Management & User Authentication, Swiss National Licences, Final Report
{:.no_toc}

Lionel Walter, Swissbib project, Basel University Library, 20 November 2017<br>
<lionel.walter@unibas.ch>


<h2 class="nonumber">Table of contents</h2>
{:.no_toc}


1. TOC
{:toc}

---


## Management summary

In 2015, Switzerland launched a [Swiss National Licences project](http://www.nationallizenzen.ch). This is a 2-year project funded by the [swissuniversities' program "Scientific information: Access, processing and safeguarding"](http://www.swissuniversities.ch/isci) to the tune of CHF 9 million. CHF 7.5 million was allocated to buy content from publishers, CHF 1 million to ensure that this content is preserved for the whole of Switzerland, and CHF 0.5 million for the negotiation of contracts, overall management, metadata management and user authentication. The project is led by the Consortium of Swiss Academic Libraries (at ETH Zurich). The metadata management and user authentication subprojects were allocated to the Swissbib team at the University of Basel. The subproject started on November 1, 2015 and ended on June 30, 2017.

More than 6 million journal articles from 4 publishers were bought (Cambridge University Press, De Gruyter, Oxford University Press and Springer).

The following goals were achieved:

 * **Private users**. Every private person living in Switzerland can access the content covered by National Licences via the [Swissbib](https://www.swissbib.ch/Search/Results?filter%5B%5D=union%3A%22NATIONALLICENCE%22) platform after registering online.
 * **Integration into library systems**. The integration of the content was simplified for Swiss libraries that already have discovery tools with the central creation of a KBART journals title list and dedicated targets in various tools (like ExLibris SFX).
 * **Implementation of green open access conditions**. The National Licences contracts permit the secondary publication (green open access) of articles by authors from Swiss institutions with the publisher's pdf. Each licence has specific terms and embargoes. 15,700 publications that fulfill the licence conditions have been published open access in the [RERO DOC](http://doc.rero.ch/collection/NATIONAL_LICENCES) repository. They are also ready for integration into the various institutional repositories in Switzerland.
 * **Open and raw metadata**. Working with raw metadata from publishers (not via vendors) allowed us to redistribute this metadata via the standard Swissbib channel: the SRU API and as Linked Open Data. It also allowed us to deliver new services, such as the mining of author affiliations to implement green open access conditions.

Most of these goals were achieved using existing infrastructures like Swissbib, SWITCH edu-ID or RERO DOC, but with closer collaboration. All implementations were open source. Therefore, these new services can be reused, for example:

 * to provide remote access to digital collections for private users (for example, registered users of a specific library)
 * to ease the integration of digital collections licensed by the Consortium into the various library systems
 * to implement open access conditions from upcoming consortial licences

---

## Facts and figures


### Journal articles
 * **6,250,000** journal articles available nationwide via [National Licences in Swissbib](https://www.swissbib.ch/Search/Results?filter%5B%5D=union%3A%22NATIONALLICENCE%22)
 * **15,700** journal articles available open access in [RERO Doc](http://doc.rero.ch/collection/NATIONAL_LICENCES)

### Publishers

|Publisher       |Number of journals       |Number of articles      |Years available (as of 30.8.2017)     |Moving wall|Next addition|Metadata licence|
| :------------- | -------------: | -------------: | :---------: | ---| -- |------------- | ------------- | ------------- | ---|
|Cambridge University Press|390|1,100,000|1770-2015|5 years|1.1.2022: year 2016 available|CC0 with special mentions|
|De Gruyter|352|450,000|1826-2015|2 years|1.1.2019: year 2016 available|CC0|
|Oxford University Press|292|1,200,000|1895-2015|3 years|1.1.2020: year 2016 available|CC-BY-NC|
|Springer|1,590|3,500,000|1832-2011|4 years|fall 2017: year 2012 available, 1.1.2018: year 2013 available|restrictive licence from Springer|
|**Total**|2,624|6,250,000|||||


### Private users

#### Registered private users via Swissbib

 * **1,143** private users have or have had access to National Licence content from the start (as of 3.10.2017)
 * **805** private users requested temporary access
 * **721** private users have permanent access
 * **338** private users have permanent access without any temporary access
 * **422** private users activated temporary access but never verified their home postal address


#### Private users' downloads

 * **1,903** downloads of full-text (without Cambridge University Press, where numbers are missing)

Publisher's details :
 * De Gruyter: **648** full-text article requests (COUNTER 4 JR1, as of 22.8.2017)
 * Oxford University Press: **884** full-text article requests (COUNTER 4 JR1, as of 31.7.2017)
 * Springer:  **371** full-text article requests (COUNTER 4 JR1, as of 31.7.2017, only 4 months)
 * Cambridge: numbers missing



---


## Authentication

There were two main questions on this topic:

 1. How can private users authenticate themselves on publishers' platforms?
 2. How can we verify that they live in Switzerland, as required by the contracts?

The starting point was a meeting with Switch on February 2, 2016, which made it possible to write requirements for publishers relating to these topics.

The answer to the first question was as follows: Private users will use the new SWITCH edu-ID Identity Provider from Switch to authenticate themselves (using SAML/Shibboleth) on publishers' platforms. The publishers need to support the value `urn:mace:dir:entitlement:common-lib-terms` in the SAML attribute `eduPersonEntitlement`. This ensures maximum privacy for the users. The publishers know almost nothing about the users.

Another option considered was to set up a proxy (for example EZ Proxy) for the National Licences' content. This was the option chosen by the German National Licences. The main drawbacks of this solution are as follows:

 * An EZProxy server must be built and maintained
 * Private users can not authenticate themselves directly on the publisher's platform. They need to come to the proxy before doing so.

The main advantage is that there are no specific requirements or additional work to be done on the publisher's platform. For example, it can cover platforms which are not Shibboleth-compatible.

For the second question, we explored various options:

 * Check that the IP address of the device is based in Switzerland (as is done by the Cochrane National Licence of the Swiss Academy of Medical Sciences (SAMW)). This was rejected by publishers, mainly because it is too easy to bypass.
 * Check that the person has a Swiss mobile phone number by sending an SMS with a code
 * Check that the person has an address in Switzerland by sending a letter by post

After negotiations with publishers, they agreed to a 14-day temporary access based on the verification of a Swiss mobile phone number and permanent access after checking the person's residency by post. This way, immediate access is possible for a user who wants to read the content as soon as they discover it.

We then had two additional meetings with Switch to see whether the SWITCH edu-ID framework fulfills all the needs of the Swiss National Licences. We concluded that the main authentication features (user management, passwords, verified mobile phone number, verified post address, attribute `eduPersonEntitlement`) are dealt with by Switch. But some of the requirements are specific to National Licences. Indeed, the following conditions need to be met to access content of Swiss National Licences:

  - User needs to accept the terms and conditions of Swiss National Licences
  - User must have a SWITCH edu-ID account
  - User must have a verified Swiss mobile phone number in their SWITCH edu-ID account and must have requested their unique temporary access in the last 14 days **OR** User has a verified postal address in Switzerland
  - User must not have been blocked by National Licences administrators
  - User must have used their SWITCH edu-ID account in the last 12 months

This could not be implemented directly in SWITCH edu-ID, which remains a generic identity provider. The duties of Swissbib, SWITCH edu-ID and the Consortium were clarified and the implementation was carried out between June and December 2016.

![Registration Flow Chart]({{ site.github.url }}/public/images/flow-chart.png)

### The registration process in a video

Watch the video :

[![Video]({{ site.github.url }}/public/images/video.png)](https://www.youtube.com/watch?v=dKN0u6wxGbE)

### Technical details

The whole process is best described in the [slides from the AAI & Swiss edu-ID Update 2016](https://www.switch.ch/aai/support/presentations/update2016/04_Nationallicences.pdf).

The details on how to set up `eduPersonEntitlement` via SWITCH API for SWITCH edu-ID users are available in [Swissbib Documentation](http://www.swissbib.org/wiki/index.php?title=Switch-Edu-ID).

![Architecture]({{ site.github.url }}/public/images/swissbib-switch-edu-id.png)

Every night, we update the attributes (for example, to check whether a user has received the verification letter) using the [Shibboleth Back-Channel](http://www.swissbib.org/wiki/index.php?title=Switch_Shibboleth_Backchannel_and_Attribute_Query_Plugin).

Moreover, we implemented two features of SWITCH to better integrate services (like Swissbib) within the SWITCH edu-ID framework, where most of the user information is stored, to improve the user experience. First, we implemented [customized SWITCH edu-ID forms](https://forge.switch.ch/projects/edu-id/wiki/Swiss_edu-ID_Registration_Form_Parameters) so that login and registration forms have some explanations from the service:

![Customized SWITCH edu-ID Menu]({{ site.github.url }}/public/images/switch-edu-id-customizations.png)

Additionally, when we did not have one of the user's attributes (for example, the home postal address), we used the [SWITCH edu-ID Attribute Completion Flow](https://forge.switch.ch/projects/edu-id/wiki/Swiss_edu-ID_Attribute_Completion_Flow) to simplify the user's travels between Swissbib and the SWITCH edu-ID interface, where they can add new attributes. This can be seen in the above video, when the user adds their mobile number (starting at 2'09).

### Improvements made in 2017

After the go-live in December 2016, the system was reviewed by an external company which specializes in User Experience. Switch and Swissbib implemented most of their recommendations in spring 2017. The user experience was then much improved. Some of the improvements include:

 * Better user guidance (better hint texts, better information about the next steps, ...)
 * Consistent wording between SWITCH and Swissbib
 * Better handling of the terms of use
 * No requirement to enter the password multiple times (in SWITCH and Swissbib)
 * Support in 4 languages (German, French, English, Italian)
 * No requirement to activate the temporary or permanent access manually. If a Swiss phone number is available, temporary access is automatically activated. As soon as the postal address has been verified, permanent access is granted.
 * After receiving the letter and verifying the code, the user is automatically redirected to Swissbib


### Perspectives

This system allows private users to access subscription content on the Internet with a Shibboleth/SAML authentication. For National Licences, the rule was that the person must live in Switzerland. But this framework with Switch edu-ID and a registration service can be extended to other use cases, for example to allow patrons registered at a specific library to access content on publishers' platforms. The Zentralbibliothek Zürich, the BCU Fribourg and the ZHB Luzern have already expressed interest in such a solution for their patrons. This is currently under evaluation.

---

## Metadata management

### Work on the publisher's side

#### Metadata requirements, negotiation with publishers, and metadata quality control

This was covered extensively in the [mid-project report](http://swissbib.github.io/metadataNationalLicencesDocumentation/pages/general/summary-2016-06/#work-on-the-publisher-side).



### Work on the technical side

The code for this part was released on [Github](https://github.com/swissbib/metadataNationalLicences) and in the [technical documentation](https://github.com/swissbib/metadataNationalLicencesDocumentation).

#### Pivot format

The goal was to transform all incoming metadata into a common format (pivot format). Once we have the metadata in the pivot format, we can process it using a unique workflow.

We analyzed potential candidates for a pivot format: MODS, NLM JATS, MARC21, DataCite Metadata Schema, ...

We finally decided to use the MODS format for the following main reasons:
 * It is a standard maintained by the Library of Congress
 * The ISTEX project, which looks after the French National Licences, uses it as a pivot format
 * Various library systems can handle it

The main disadvantage:

 * It is sometimes not as precise as NLM JATS for journal articles

#### Workflow

Click on the following image for a hyperlinked version with all the details and links to the code and data samples:


[![Big Picture]({{ site.github.url }}/public/images/big-picture.svg)]({{ site.github.url }}/public/images/big-picture.svg)


#### Workflow for the analysis

 1. Extract the files from the zip and tar files (via shell scripts)
 1. Do an initial analysis with shell scripts (which DTD are used, which encoding, ...)
 1. Transform the metadata into JSON with metafacture (by either taking everything or only certain fields)
 1. Index all data in elasticsearch
 1. Analyze the data in elasticsearch
 1. Export the results and the title lists with python


#### Workflow for import into swissbib

1. **[same as above]** Extract the files from the zip and tar files (via shell scripts)
1. **[same as above]** Do an initial analysis with shell scripts (which DTD are used, which encoding, ...)
1. Transform the metadata towards the pivot format MDOS with XSLT
1. Tansform the metadata to pica+ format with fcv stylesheets (OCLC proprietary language), and import it into the OCLC CBS document store
1. **[same as swissbib standard workflow]** Export pica+ to solr format for swissbib search engine (using [content2SearchDocs](https://github.com/swissbib/content2SearchDocs))
1. **[same as swissbib standard workflow]** Use VuFind as the front-end: <http://swissbib.ch>

As a result, the metadata from Cambridge University Press, De Gruyter and Oxford University Press was available in Swissbib on December 5, 2016. The metadata from Springer was available on March 31, 2017 (the contract with Springer was signed later than the three other contracts).


---





### Work on the customer side

#### For private persons (in Swissbib)

All articles from National Licences were integrated into the standard <http://www.swissbib.ch>. Access to the National Licences content is gained through a specific facet.

![Mock-up with a facet]({{ site.github.url }}/public/images/swissbib-nl-facet.png)

----



#### For private persons (in Google Scholar)

To make it easier for private users to discover National Licences and at the same time offer additional services from libraries (like document delivery), we offer personalized links for Swiss residents in Google Scholar. They look like this:

![Mockup Google Scholar]({{ site.github.url }}/public/images/google_scholar.png)

To have such a display, interested users must specify that they are Swiss residents in their Google Scholar personal settings. This was done using IDS SFX guest instance.


#### For private persons (other means)

Some libraries in Switzerland already have several remote services for private users. For example:

 * The University of Bern library has a service for [people living in Bern state](http://www.unibe.ch/universitaet/dienstleistungen/universitaetsbibliothek/recherche/datenbanken/ezproxy/index_ger.html). Authentication technology: EZProxy.
 * The ETH library has a service called [E-Lending](http://www.library.ethz.ch/en/Services/Using-ordering-resources/E-Lending) for its external patrons. Authentication technology: Shibboleth via the specific Identity Provider libraries.ch
 * The EPFL has a service for its [alumni](https://www.epflalumni.ch/scientific-informations/). Authentication technology: Shibboleth via the EPFL Identity provider.

The various institutions want their patrons to be able to access the content through these means as well. For Shibboleth authentication, these institutions must be in the Switch federation, which is usually the case. For EZProxy authentication, the IP address of the EZProxy server must be declared in the National Licences. This is often the case because these servers are normally in the standard IP range of the universities.

Additionally, care must be taken to ensure that the conditions of the contracts are met by these various services (for example, residency in Switzerland). This is usually the case as well.

#### Journal title lists (for example, for library discovery tools)

Title lists at journal level in Excel and KBART formats extracted from the article metadata were generated and published on the [Consortium website](http://www.consortium.ch/title-lists-for-swiss-national-licences/?lang=en). These lists facilitate integration into the various tools.

[![Title lists on the Consortium website]({{ site.github.url }}/public/images/title-lists.png)](http://www.consortium.ch/title-lists-for-swiss-national-licences/?lang=en)

As ExLibris SFX is one of the main tools used in Switzerland, we contacted ExLibris to be able to create dedicated targets for Swiss National Licences in the SFX KnowledgeBase. In this way, the updates can be applied centrally and take effect for all libraries which use SFX. ExLibris requested title lists in KBART format. We complied and the targets were created at the beginning of June 2016:


![Swiss targets in SFX]({{ site.github.url }}/public/images/4_swiss_targets_SFX.png)

We can update Swiss national collections centrally by depositing KBART files on the ExLibris FTP server.

With the help of various libraries in Switzerland, it was also possible to create dedicated "packages" in other tools:

 * Proquest Intota (with the UB Bern)
 * Elektronische Zeitschriftenbibliothek EZB (with the UZH-Hauptbibliothek, Zentralbibliothek Zürich and HSG Bibliothek)            
 * Ebsco Discovery (with the PHSG Bibliothek)

##### Discussion

The centralization and standardization of journal title lists from Consortium licences were viewed very positively by the libraries. Up to now, every library has needed to process the lists provided by the publishers to the Consortium. On top of that, there are addendums and changes to the contracts every year, which usually makes it a relatively time-consuming task. With the centralization, this can be done by every library with a single click.

This process is also gaining momentum in other countries. The pioneer is the [Knowledge Base+ Project](https://www.kbplus.ac.uk/kbplus/) of JISC in the UK. The Swedish consortium BIBSAM has a partnership with Knowledge Base+ to have standardized title lists and targets. The French project [Bacon](https://bacon.abes.fr/) of ABES is similar. They used the lists of Knowledge Base+ for international publishers and provided KBART lists and specific targets for French publishers in close collaboration with the publishers (see [this post](https://fil.abes.fr/2016/06/20/bacon-bilan-detape-sur-le-perimetre-couvert/) for more information).

The main difficulty when creating journal title lists based on publisher's article metadata is the history of journal titles.

Here is an example:


> Sprachliche Bedingungen der Wortwahl  
> STUF-Language Typology and Universals, 1966  
> Georg Michel  
> http://dx.doi.org/10.1524/stuf.1966.19.16.213

On the publisher's platform (De Gruyter), you can see the following as "citation information":
STUF - Language Typology and Universals. Volume 19, Issue 1-6, Pages 213–240, ISSN (Online) 2196-7148, ISSN (Print) 1867-8319

But if you look more closely (looking at the pdf of the front matter), at that time
the name of the journal was Zeitschrift für Phonetik Sprachwissenschaft und Kommunikationsforschung. The ISSN at that time was 0044-331X.

You can never find the journal Zeitschrift für Phonetik Sprachwissenschaft und Kommunikationsforschung and the ISSN 0044-331X in De Gruyter's article metadata or on the platform.
In Primo Central, the article is described as part of "STUF - Language Typology and Universals"
<http://www.library.ethz.ch/DADS:Primo_Central:TN_crossref10.1524/stuf.1966.19.16.103>

In Google Scholar, the article is also described as part of "STUF - Language Typology and Universals":
<https://scholar.google.ch/scholar?hl=fr&q=Sprachliche+Bedingungen+der+Wortwahl&btnG=&lr=>

Therefore, we did the same for Swissbib: <https://www.swissbib.ch/Search/Results?lookfor=nationallicencegruyter101524stuf19661916213>

Is that the right thing to do? What is correct: print or online? This question remains unanswered...

This might be more important for journal title lists than for the article metadata (for example, to compare print and online holdings). The current journal title lists for Swiss National Licences correctly reflect the print history, but they are an indication of what is on the publisher's platform.

The best way to have a better title history for journal lists would be to use the [public master lists of Knowledge Base+](https://www.kbplus.ac.uk/kbplus/publicExport) and to apply the years licensed in the frame of Swiss National Licences to those lists. Unfortunately, it was not possible to do this during the project. But it is something to keep in mind for the future.

In the future, it might be a good idea to have centralized management of title lists and specific targets/packages for all consortial licences, as is the case in the UK and in France.


### Other means of delivering metadata

All the metadata at article level can be retrieved via the [Swissbib SRU API](http://sru.swissbib.ch/) in various formats:

*   xml marc: [one record](http://sru.swissbib.ch/sru/search/defaultdb?query=+dc.id+%3D+379420546&operation=searchRetrieve&recordSchema=info%3Asrw%2Fschema%2F1%2Fmarcxml-v1.1-light&maximumRecords=10&startRecord=0&recordPacking=XML&availableDBs=defaultdb&sortKeys=Submit+query), [whole collection](http://sru.swissbib.ch/sru/search/defaultdb?query=+dc.xNetwork+%3D+NATIONALLICENCE&operation=searchRetrieve&recordSchema=info%3Asrw%2Fschema%2F1%2Fmarcxml-v1.1-light&maximumRecords=10&startRecord=0&recordPacking=XML&availableDBs=defaultdb&sortKeys=Submit+query)
*   marc in json: [one record](http://sru.swissbib.ch/sru/search/defaultdb?query=+dc.id+%3D+379420546&operation=searchRetrieve&recordSchema=info%3Asru%2Fschema%2Fjson&maximumRecords=10&startRecord=0&recordPacking=XML&availableDBs=defaultdb&sortKeys=Submit+query), [whole collection](http://sru.swissbib.ch/sru/search/defaultdb?query=+dc.xNetwork+%3D+NATIONALLICENCE&operation=searchRetrieve&recordSchema=info%3Asru%2Fschema%2Fjson&maximumRecords=10&startRecord=0&recordPacking=XML&availableDBs=defaultdb&sortKeys=Submit+query)
*   dublin core: [one record](http://sru.swissbib.ch/sru/search/defaultdb?query=+dc.id+%3D+379420546&operation=searchRetrieve&recordSchema=info%3Asru%2Fschema%2F1%2Fdc-v1.1-light&maximumRecords=10&startRecord=0&recordPacking=XML&availableDBs=defaultdb&sortKeys=Submit+query), [whole collection](http://sru.swissbib.ch/sru/search/defaultdb?query=+dc.xNetwork+%3D+NATIONALLICENCE&operation=searchRetrieve&recordSchema=info%3Asru%2Fschema%2F1%2Fdc-v1.1-light&maximumRecords=10&startRecord=0&recordPacking=XML&availableDBs=defaultdb&sortKeys=Submit+query)

The metadata is also available using the Swissbib Linked Open Data portal:

*   [html](http://data.swissbib.ch/bibliographicResource/379420546)
*   [rdfxml](http://data.swissbib.ch/bibliographicResource/379420546.rdfxml)
*   [turtle](http://data.swissbib.ch/bibliographicResource/379420546.turtle)
*   [json-ld](http://data.swissbib.ch/bibliographicResource/379420546.jsonld)
*   [n-triples](http://data.swissbib.ch/bibliographicResource/379420546.ntriples)

On top of that, upon request, the Swissbib team can deliver the metadata in MODS or JATS (except for Springer) format.

Publication of a full export on the <http://opendata.swiss> portal is under consideration.

---

### Collaborations


#### Discussion with international partners

In January 2016, we had discussions with colleagues from Canada, France and Germany who are dealing with similar projects. A summary of the findings was published on [swissbib blog](http://swissbib.blogspot.ch/2016/03/national-licences-and-article-metadata.html).

The French project ISTEX helped us considerably by sharing their XSLT transformations of publishers' metadata so we could use it directly.


---

## Green open access

### Defining related publications

The National Licences contracts permit the secondary publication (green open access) of articles by authors from Swiss insitutions using the publisher's pdf. Each licence has specific terms and embargoes. Therefore, the first task was to identify the publications where these conditions apply.

It was very helpful to have processed raw metadata from the publishers as it meant we had all the affiliation information from the publishers. Here is the percentage of articles which have affiliation fields for all publishers:

|Cambridge|De Gruyter|Oxford|Springer|
| :-------------: | :-------------: | :-------------: | :----: |
|58%|18%|83%|78%|

The first step was to match the affiliations with Swiss universities. A small [algorithm](https://github.com/swissbib/metadataNationalLicences/blob/1.0/python/extractAndMatchSwissPublications.py#L37) was developed to match the publications, based on the name variants of the institutions as well as the email address of authors. This was based on in-depth discussions with the members of Arbeitskreis Open Access (AKOA). On top of the that, the authors of the study:

>Alexander Machado, Laura Hoppmann, Johannes Knaus, Margit Palzenberger.
>Bibliometric study of the Swiss Publication System, 2016.
><http://doi.org/10.5281/zenodo.167381>

shared their algorithms with us.

Such algorithms are never 100% accurate; there are always some publications missing or wrongly matched. On top of that, there is [really not a standardized](http://swissbib.github.io/metadataNationalLicencesDocumentation/pages/input/021jats/#way-to-deal-with-affiliations) way to deal with publications on the publishers' side. Nonetheless, it was possible to identify more than 15,700 publications from authors from Swiss institutions that could be published open access. 2,000 of them have an embargo that will expire at the latest in 2020.

Please note that this applies only to Cambridge, De Gruyter and Oxford. The Springer Green Open Access clause was only signed in July 2017 and the full-texts were not delivered. This might happen in the next stage of this project. We estimate that 15,000 articles from Springer might be published open access.


### Delivery of full-texts

To implement green open access with the publishers' pdf, we needed pdfs to be delivered by the publishers.

#### Cambridge University Press

Cambridge University Press allowed us to automatically download the full-texts from "Swiss" authors directly from their web platform. This is a very convenient method. The disadvantage is that there is a watermark on the pdf.

#### De Gruyter

De Gruyter delivered all the pdfs of the Swiss National Licences to us via an FTP server. As the structure of the folders and files was exactly the same as for the metadata which they had delivered the previous year, it was very easy to match the publications with the full-texts.

#### Oxford University Press

Oxford University Press sent us a 1 Gb harddrive by post which contained all the pdfs of the Swiss National Licences. The difficulty here is that they used a completely different structure for the full-texts than the one used for the metadata. Here is an example:

For the following article *Culley, T. M., Sbita, S. J., & Wick, A. (2007). Population Genetic Effects of Urban Habitat Fragmentation in the Perennial Herb Viola pubescens (Violaceae) using ISSR Markers. Annals of Botany, 100(1), 91–100. https://doi.org/10.1093/aob/mcm077*

 * The metadata was described in the file `/ANNBOT/annbot100-1/abstracts/mcm070.xml`
 * The full-text was in the file  `/Annals of Botany/annbot_100_1/mcm070.pdf`

There was no consistency with the `-` and `_` in the folder names. Only the file names were consistent, but not unique. In the end, we used the journal name and the file name for the matching, but this was time-consuming.

#### Springer

Springer had not delivered the full-texts at the time of this writing.

### Publication in RERO DOC, OAI sets and lists for each institution

After discussion with the AKOA, the publishers and RERO, it was decided that the first step would be to publish these 15,700 publications open access in the RERO DOC open-access respository. From there, every institution can harvest its own content and import it into its repository.

The process was the following:

1. Export the metadata from Swissbib for the matching publications
1. Add the full-text, the date when the embargo ends and the matching institution(s)
1. Import into RERO DOC
1. Create dedicated OAI sets for each institution in RERO DOC

---

In July 2017, the publications were added to [RERO DOC](http://doc.rero.ch/collection/NATIONAL_LICENCES).

![Open Access Content from National Licences in RERO DOC]({{ site.github.url }}/public/images/rero-doc-national-licences.png)

---

After publication in RERO Doc, lists and OAI sets were made available on the dedicated open access page on the Consortium website:

[![Lists for each institution]({{ site.github.url }}/public/images/open-access-lists.png)](http://www.consortium.ch/open-access/?lang=en)

---

Use of a well-established repository like RERO Doc ensured excellent visibility. Several days later, the articles were referenced in Google Scholar.

![Open Access Content from National Licences in Google Scholar]({{ site.github.url }}/public/images/google-scholar-rero-doc.png)


### Related projects & perspectives

This problem is very relevant for academic libraries right now. Germany has a similar project called [Deep Green](https://www.oa-deepgreen.de/) and the UK as well with [PubRouter](https://pubrouter.jisc.ac.uk/). Deep Green has partnerships with the publishers Karger, Sage, De Gruyter. PubRouter has partnerships with eLife, PLOS and SpringerNature. Deep Green is in its pilot phase. Closer collaboration with these projects might be very useful in the future.

Additionally, the infrastructure used for National Licences could be reused for upcoming Consortium licences with open access conditions.



---



## Publications & documentation

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
