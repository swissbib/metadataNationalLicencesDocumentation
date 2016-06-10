---
layout: page
title: Crossref
---

# Crossref

## Liens

 * <http://crossref.org>


## Sources

Total number of participating publishers and societies: 5322 - See more at: <http://www.crossref.org/01company/06publishers.html>


## Remarques

C'est le schéma unixref1.0.xsd qui est utilsé. Unified CrossRef XML schema. [Faire une demande pour un doi précis](http://www.crossref.org/guestquery/).

On a le droit d'importer ces métadonnées :

>  a. The Library may retrieve DOIs and metadata by **batch** or one at a time. The Library may use retrieved DOIs and metadata to make persistent links to full-text works online, to make link resolvers function better and clean up its own indices, abstracts and record locators, the Library may cache the DOIs and metadata and incorporate DOIs and metadata into their content and library systems. The Library may use the DOIs and metadata for scholarly, research, educational, personal or non-commercial purposes.

> b. Any other use of metadata is prohibited. The Library may not, and may not permit others to, redistribute, copy, print, archive, backup, reserve or loan any of the metadata (**except incidentally where DOIs and metadata have been incorporated into the Library's content and/or systems**.)

> c. The Library **may not charge fees** for access to the CrossRef system or retrieval of DOIs and metadata. Likewise, the Library may not re-license or sell the DOIs and metadata or access to the service, including but not limited to bulk reproduction or distribution of the DOIs and metadata.

On peut récupérer les métadonnées par OAI, mais c'est un **service payant**. Il faut le membership *Basic CMS Affiliate* pour télécharger via FTP et le *Enhanced CMS Affiliate* pour télécharger des métadonnées par OAI. Compter 2000$ / an pour le premier et 3000$ / an pour le deuxième. Le contrôle se fait par adresse IP. De plus, les éditeurs ont le droit de ne pas diffuser leurs métadonnées par ce biais.

Information à ce sujet, mail de crossref du 2.12.2015 :

> Publishers have the option of opting out of metadata delivery for each organization who applies for CMS. They may chose to opt out of one but another.  A statement of intended use is provided by each applicant and sent to our membership; the members have 30 days to let us know if they would like to withhold their metadata from the applicant's account.

>The Enhanced CMS is the only type of query account that allows for bulk queries for a particular journal title and publisher.

> Kind regards,
> Susan

> Susan Collins
> Associate Membership Manager | Crossref




## Accès OAI

 * il faut d'abord récupérer le préfix doi de l'éditeur, par exemple `10.1002` pour Wiley
 * Puis on fait ListSets pour cet éditeur en préfixant avec `J:` pour les journaux, `B:` pour les livres et proceedins, `S:` pour les séries :
  * Une [liste de journaux Wiley](http://oai.crossref.org/OAIHandler?verb=ListSets&set=J:10.1002) (944 journaux)
  * Une [liste de séries Wiley](http://oai.crossref.org/OAIHandler?verb=ListSets&set=S:10.1002) (159 séries)
  * Une [liste de livres Wiley](http://oai.crossref.org/OAIHandler?verb=ListSets&set=B:10.1002) (1000 livres avec resumption token)

Puis au deuxième niveau

 * [Résultat pour un journal](http://oai.crossref.org/OAIHandler?verb=ListIdentifiers&metadataPrefix=cr_unixml&set=J:10.1002:264227). On a la liste des doi, mais pas les métadonnées. Il faudrait ensuite lancer une query avec chaque doi pour récupérer les métadonnées, mais c'est interdit par la charte crossref

## Exemple XML

Exemple pour cet article <http://dx.doi.org/10.1007/s002619900002>

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<crossref_result xmlns="http://www.crossref.org/qrschema/3.0" version="3.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.crossref.org/qrschema/3.0 http://www.crossref.org/schemas/crossref_query_output3.0.xsd">
  <query_result>
    <head>
      <email_address>test@crossref.org</email_address>
      <doi_batch_id>test</doi_batch_id>
    </head>
    <body>
      <query key="key" status="resolved">
        <doi type="journal_article">10.1007/s002619900002</doi>
        <crm-item name="publisher-name" type="string">Springer Science + Business Media</crm-item>
        <crm-item name="prefix-name" type="string">Springer-Verlag</crm-item>
        <crm-item name="member-id" type="number">297</crm-item>
        <crm-item name="citation-id" type="number">572263</crm-item>
        <crm-item name="journal-id" type="number">1040</crm-item>
        <crm-item name="deposit-timestamp" type="number">20040319013112</crm-item>
        <crm-item name="owner-prefix" type="string">10.1007</crm-item>
        <crm-item name="last-update" type="date">2013-03-20T20:39:25Z</crm-item>
        <crm-item name="created" type="date">2002-07-25T07:09:18Z</crm-item>
        <crm-item name="citedby-count" type="number">7</crm-item>
        <doi_record>
          <crossref xmlns="http://www.crossref.org/xschema/1.0" xsi:schemaLocation="http://www.crossref.org/xschema/1.0 http://doi.crossref.org/schemas/unixref1.0.xsd">
            <journal>
              <journal_metadata>
                <full_title>Abdominal Imaging</full_title>
                <abbrev_title>Abdominal Imaging</abbrev_title>
                <issn media_type="print">0942-8925</issn>
                <issn media_type="electronic">1432-0509</issn>
                <coden>261</coden>
              </journal_metadata>
              <journal_issue>
                <publication_date media_type="print">
                  <month>1</month>
                  <day>1</day>
                  <year>1996</year>
                </publication_date>
                <journal_volume>
                  <volume>21</volume>
                </journal_volume>
                <issue>1</issue>
              </journal_issue>
              <journal_article publication_type="full_text">
                <titles>
                  <title>Ultrasonography of the gastrointestinal tract in infants and children</title>
                </titles>
                <contributors>
                  <person_name sequence="first" contributor_role="author">
                    <given_name>C. K. Hayden</given_name>
                    <surname>Jr.</surname>
                  </person_name>
                </contributors>
                <publication_date media_type="print">
                  <month>1</month>
                  <day>1</day>
                  <year>1996</year>
                </publication_date>
                <pages>
                  <first_page>9</first_page>
                  <last_page>20</last_page>
                </pages>
                <publisher_item>
                  <identifier id_type="pii">90RVQUFA7JVJMBTE</identifier>
                </publisher_item>
                <doi_data>
                  <doi>10.1007/s002619900002</doi>
                  <timestamp>20040319013112</timestamp>
                  <resource>http://link.springer.com/10.1007/s002619900002</resource>
                  <collection property="crawler-based" setbyID="springer">
                    <item crawler="iParadigms">
                      <resource>http://www.springerlink.com/index/pdf/10.1007/s002619900002</resource>
                    </item>
                  </collection>
                </doi_data>
              </journal_article>
            </journal>
          </crossref>
        </doi_record>
      </query>
    </body>
  </query_result>
</crossref_result>

{% endhighlight %}


## Exemple Linked data

Via *Content Negotiation*, crossref propose aussi ces documents en RDF/XML (JSON-LD). La requête

```
curl -LH "Accept: application/rdf+xml;q=0.5" http://dx.doi.org/10.1515/TEXT.2006.011
```

Donne comme résultat :

{% highlight xml %}
<rdf:RDF
    xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
    xmlns:j.0="http://purl.org/ontology/bibo/"
    xmlns:j.1="http://xmlns.com/foaf/0.1/"
    xmlns:owl="http://www.w3.org/2002/07/owl#"
    xmlns:j.2="http://purl.org/dc/terms/"
    xmlns:j.3="http://prismstandard.org/namespaces/basic/2.1/">
  <rdf:Description rdf:about="http://dx.doi.org/10.1007/s002619900002">
    <j.2:creator>
      <j.1:Person rdf:about="http://id.crossref.org/contributor/c-k-hayden-jr-3d9gtfkgdnnrs">
        <j.1:name>C. K. Hayden Jr.</j.1:name>
        <j.1:familyName>Jr.</j.1:familyName>
        <j.1:givenName>C. K. Hayden</j.1:givenName>
      </j.1:Person>
    </j.2:creator>
    <j.0:pageStart>9</j.0:pageStart>
    <j.3:endingPage>20</j.3:endingPage>
    <j.0:volume>21</j.0:volume>
    <owl:sameAs rdf:resource="doi:10.1007/s002619900002"/>
    <j.2:identifier>10.1007/s002619900002</j.2:identifier>
    <j.0:pageEnd>20</j.0:pageEnd>
    <j.2:title>Ultrasonography of the gastrointestinal tract in infants and children</j.2:title>
    <j.2:publisher>Springer Science + Business Media</j.2:publisher>
    <j.2:isPartOf>
      <j.0:Journal rdf:about="http://id.crossref.org/issn/0942-8925">
        <j.3:issn>1432-0509</j.3:issn>
        <j.0:issn>1432-0509</j.0:issn>
        <owl:sameAs>urn:issn:1432-0509</owl:sameAs>
        <owl:sameAs>urn:issn:0942-8925</owl:sameAs>
        <j.2:title>Abdominal Imaging</j.2:title>
        <j.3:issn>0942-8925</j.3:issn>
        <j.0:issn>0942-8925</j.0:issn>
      </j.0:Journal>
    </j.2:isPartOf>
    <j.3:startingPage>9</j.3:startingPage>
    <j.0:doi>10.1007/s002619900002</j.0:doi>
    <j.2:date rdf:datatype="http://www.w3.org/2001/XMLSchema#date"
    >1996-1-1</j.2:date>
    <j.3:volume>21</j.3:volume>
    <j.3:doi>10.1007/s002619900002</j.3:doi>
    <owl:sameAs rdf:resource="info:doi/10.1007/s002619900002"/>
  </rdf:Description>
</rdf:RDF>
{% endhighlight %}


## Test sur la validité des DOI

### Old API

Documentation :

Query xml schema :

On peut faire un test de cette façon là

```
curl -F 'operation=doQueryUpload' -F 'login_id=XXX' -F 'login_passwd=XXX' -F 'fname=@query.xml' https://doi.crossref.org/servlet/deposit
```

avec un fichier query.xml ainsi

{% highlight xml %}
<?xml version = "1.0" encoding="UTF-8"?>
<query_batch version="2.0" xmlns = "http://www.crossref.org/qschema/2.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <head>
      <email_address>lionel.walter@unibas.ch</email_address>
      <doi_batch_id>Sample multi resolve</doi_batch_id>
  </head>
  <body>

	<query key="1">
           <doi>10.1006/jmbi.2000.4282</doi>
       </query>
	<query key="2">
           <doi>10.1017/S0022112001003639</doi>
       </query>
	<query key="3">
           <doi>10.1017/S026134090001941X</doi>
       </query>  
   </body>
</query_batch>
{% endhighlight %}

On reçoit la réponse par email et cela ressemble à ceci

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<crossref_result xmlns="http://www.crossref.org/qrschema/2.0" version="2.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.crossref.org/qrschema/2.0 http://www.crossref.org/schema/queryResultSchema/crossref_query_output2.0.xsd">
  <query_result>
    <head>
      <email_address>lionel.walter@unibas.ch</email_address>
      <doi_batch_id>Sample multi resolve</doi_batch_id>
    </head>
    <body>
      <query key="1" status="resolved" fl_count="0">
        <doi type="journal_article">10.1006/jmbi.2000.4282</doi>
        <issn type="print">00222836</issn>
        <journal_title>Journal of Molecular Biology</journal_title>
        <author>Jiang</author>
        <volume>305</volume>
        <issue>3</issue>
        <first_page>377</first_page>
        <year media_type="print">2001</year>
        <publication_type>full_text</publication_type>
      </query>
      <query key="2" status="resolved" fl_count="0">
        <doi type="journal_article">10.1017/S0022112001003639</doi>
        <issn type="print">0022-1120</issn>
        <issn type="electronic">1469-7645</issn>
        <journal_title>Journal of Fluid Mechanics</journal_title>
        <author>IERLEY</author>
        <volume>435</volume>
        <year media_type="online">2001</year>
        <year media_type="print">2001</year>
        <publication_type>full_text</publication_type>
      </query>
      <query key="3" status="**unresolved**" fl_count="0">
        <doi>10.1017/S026134090001941X</doi>
      </query>
    </body>
  </query_result>
</crossref_result>
{% endhighlight %}

Pas moyen de recevoir le résultat d'une batch query autrement que par email ???

### New API

Là on peut faire une query ainsi

<http://api.crossref.org/works?rows=3&filter=doi:10.1006/jmbi.2000.4282,doi:10.1017/S0022112001003639,doi:10.1017/S026134090001941X>

Malheureusement, on ne sait pas vraiment quels doi's ne sont pas enregistrés.

De plus on est limité à 4096 caractères dans l'url. Exemple

<http://api.crossref.org/works?rows=0&filter=doi:10.1016/j.ejcts.2008.02.027,doi:10.1016/j.ejcts.2008.07.030,doi:10.1016/S0895-7061%2898%2900070-3,doi:10.1017/asb.2014.15,doi:10.1017/hor.2013.23,doi:10.1017/idm.2014.17,doi:10.1017/jan.2014.5,doi:10.1017/mdh.2013.22,doi:10.1017/S0003055400140146,doi:10.1017/S0003161500003795,doi:10.1017/S0003598X00079722,doi:10.1017/S0003598X00085884,doi:10.1017/S0007485300000419,doi:10.1017/S0008423905339977,doi:10.1017/S0008423906459965,doi:10.1017/S0008423910000272,doi:10.1017/S0008938900021427,doi:10.1017/S0009640700010234,doi:10.1017/S0009838800003578,doi:10.1017/S0009838800003748,doi:10.1017/S0009840X00282097,doi:10.1017/S0009840X05000892,doi:10.1017/S0009840X15000724,doi:10.1017/S0016756800060696,doi:10.1017/S0016756800067625,doi:10.1017/S0016756800174710,doi:10.1017/S0016756800177726,doi:10.1017/S0016756800183438,doi:10.1017/S0016756800183529,doi:10.1017/S0017816005001045,doi:10.1017/S0017816009000030,doi:10.1017/S0018246X00025140,doi:10.1017/S0020589309990091,doi:10.1017/S0021853712000102,doi:10.1017/S0021932000017703,doi:10.1017/S002193200002143X,doi:10.1017/S0022046900013440,doi:10.1017/S0022046902302562,doi:10.1017/S0022046913000870,doi:10.1017/S002211207300056X,doi:10.1017/S0022149X00003047,doi:10.1017/S0022149X00003084,doi:10.1017/S0022215100054876,doi:10.1017/S0022215100067669,doi:10.1017/S002221510010739X,doi:10.1017/S0022215100111685,doi:10.1017/S0022215100112472,doi:10.1017/S002221510011254X,doi:10.1017/S0022215100116640,doi:10.1017/S0022215107001636,doi:10.1017/S0022216X08004422,doi:10.1017/S0024282906005810,doi:10.1017/S0028688500001764,doi:10.1017/S0028688500003866,doi:10.1017/S0028688500005592,doi:10.1017/S0028688500010262,doi:10.1017/S0028688500012492,doi:10.1017/S0028688500016271,doi:10.1017/S0028688500016581,doi:10.1017/S0028688500017562,doi:10.1017/S0028688500017574,doi:10.1017/S0028688500018014,doi:10.1017/S002868850001835X,doi:10.1017/S0028688500018476,doi:10.1017/S0028688500018798,doi:10.1017/S0028688500020853,doi:10.1017/S0028688500021627,doi:10.1017/S0029665113000037,doi:10.1017/S0030605315001374,doi:10.1017/S003118200007373X,doi:10.1017/S0033291700010400,doi:10.1017/S0033291700025344,doi:10.1017/S0033291700026489,doi:10.1017/S0033291700032797,doi:10.1017/S003329170003395X,doi:10.1017/S0033291700052090,doi:10.1017/S0033291700052910,doi:10.1017/S0041977X14000044,doi:10.1017/S0047404500007958,doi:10.1017/S0066477400000526,doi:10.1017/S0066477400000848,doi:10.1017/S0080455X00001843,doi:10.1017/S0140525X00080778,doi:10.1017/S0144686X13000639,doi:10.1017/S0165115300013516,doi:10.1017/S0195941700003398,doi:10.1017/S0195941700071939,doi:10.1017/S0195941700080164,doi:10.1017/S0261127912000046,doi:10.1017/S0263034600004985,doi:10.1017/S0268416000000655,doi:10.1017/S0268416000001247,doi:10.1017/S026972700000765X,doi:10.1017/S0269727000007661,doi:10.1017/S026988890000669X,doi:10.1017/S0305004100041918,doi:10.1017/S0308210500020850,doi:10.1017/S0315489000025524,doi:10.1017/S0317167100007459,doi:10.1017/S0362502800003679,doi:10.1017/S0370164600012852,doi:10.1017/S0376892900000746,doi:10.1017/S0376892900001156,doi:10.1017/S0376892900001211,doi:10.1017/S0376892900001399,doi:10.1017/S0376892900001430,doi:10.1017/S037689290000151X,doi:10.1017/S0376892900001612,doi:10.1017/S0376892900001879,doi:10.1017/S0376892900002010,doi:10.1017/S0376892900002034,doi:10.1017/S0376892900002204,doi:10.1017/S0376892900002320,doi:10.1017/S037689290000240X,doi:10.1017/S0376892900002782,doi:10.1017/S0376892900002903,doi:10.1017/S0376892900002940,doi:10.1017/S0376892900002976,doi:10.1017/S0376892900003647,doi:10.1017/S0376892900003659,doi:10.1017/S0376892900003660,doi:10.1017/S0376892900003994,doi:10.1017/S0376892900004057,doi:10.1017/S0376892900004094,doi:10.1017/S0376892900004707,doi:10.1017/S0376892900005245,doi:10.1017/S0376892900005622,doi:10.1017/S0376892900005750,doi:10.1017/S0376892900005919,doi:10.1017/S0376892900005932,doi:10.1017/S0376892900006251,doi:10.1017/S0376892900006305,doi:10.1017/S0376892900006895,doi:10.1017/S0376892900006901,doi:10.1017/S0376892900006913,doi:10.1017/S0376892900006937>

On reçoit :

{% highlight json %}
{
  "status": "ok",
  "message-type": "work-list",
  "message-version": "1.0.0",
  "message": {
    "query": {
      "search-terms": null,
      "start-index": 0
    },
    "items-per-page": 3,
    "items": [
      {
        "indexed": {
          "date-parts": [
            [
              2015,
              12,
              26
            ]
          ],
          "date-time": "2015-12-26T08:50:53Z",
          "timestamp": 1451119853212
        },
        "reference-count": 0,
        "publisher": "Cambridge University Press (CUP)",
        "published-print": {
          "date-parts": [
            [
              2001,
              5
            ]
          ]
        },
        "DOI": "10.1017/s0022112001003639",
        "type": "journal-article",
        "created": {
          "date-parts": [
            [
              2002,
              7,
              27
            ]
          ],
          "date-time": "2002-07-27T13:19:50Z",
          "timestamp": 1027775990000
        },
        "source": "CrossRef",
        "title": [
          "On Townsend's rapid-distortion model of the turbulent-wind-wave problem"
        ],
        "prefix": "http://id.crossref.org/prefix/10.1017",
        "volume": "435",
        "author": [
          {
            "affiliation": [],
            "family": "IERLEY",
            "given": "GLENN"
          },
          {
            "affiliation": [],
            "family": "MILES",
            "given": "JOHN"
          }
        ],
        "member": "http://id.crossref.org/member/56",
        "published-online": {
          "date-parts": [
            [
              2001,
              6,
              22
            ]
          ]
        },
        "container-title": [
          "J. Fluid Mech.",
          "Journal of Fluid Mechanics"
        ],
        "deposited": {
          "date-parts": [
            [
              2011,
              6,
              26
            ]
          ],
          "date-time": "2011-06-26T08:39:14Z",
          "timestamp": 1309077554000
        },
        "score": 1,
        "subtitle": [],
        "issued": {
          "date-parts": [
            [
              2001,
              5
            ]
          ]
        },
        "alternative-id": [
          "S0022112001003639"
        ],
        "URL": "http://dx.doi.org/10.1017/s0022112001003639",
        "ISSN": [
          "0022-1120",
          "1469-7645"
        ],
        "subject": [
          "Mechanical Engineering",
          "Mechanics of Materials",
          "Condensed Matter Physics"
        ]
      },
      {
        "indexed": {
          "date-parts": [
            [
              2016,
              5,
              16
            ]
          ],
          "date-time": "2016-05-16T01:40:02Z",
          "timestamp": 1463362802408
        },
        "reference-count": 31,
        "publisher": "Elsevier BV",
        "issue": "3",
        "license": [
          {
            "content-version": "tdm",
            "delay-in-days": 0,
            "start": {
              "date-parts": [
                [
                  2001,
                  1,
                  1
                ]
              ],
              "date-time": "2001-01-01T00:00:00Z",
              "timestamp": 978307200000
            },
            "URL": "http://www.elsevier.com/tdm/userlicense/1.0/"
          }
        ],
        "published-print": {
          "date-parts": [
            [
              2001,
              1
            ]
          ]
        },
        "DOI": "10.1006/jmbi.2000.4282",
        "type": "journal-article",
        "created": {
          "date-parts": [
            [
              2002,
              9,
              18
            ]
          ],
          "date-time": "2002-09-18T19:24:54Z",
          "timestamp": 1032377094000
        },
        "page": "377-388",
        "source": "CrossRef",
        "title": [
          "Specific interaction between anticodon nuclease and the tRNALys wobble base11Edited by D. Draper"
        ],
        "prefix": "http://id.crossref.org/prefix/10.1006",
        "volume": "305",
        "author": [
          {
            "affiliation": [],
            "family": "Jiang",
            "given": "Yue"
          },
          {
            "affiliation": [],
            "family": "Meidler",
            "given": "Roberto"
          },
          {
            "affiliation": [],
            "family": "Amitsur",
            "given": "Michal"
          },
          {
            "affiliation": [],
            "family": "Kaufmann",
            "given": "Gabriel"
          }
        ],
        "member": "http://id.crossref.org/member/78",
        "container-title": [
          "Journal of Molecular Biology"
        ],
        "link": [
          {
            "intended-application": "text-mining",
            "content-version": "vor",
            "content-type": "text/xml",
            "URL": "http://api.elsevier.com/content/article/PII:S0022283600942827?httpAccept=text/xml"
          },
          {
            "intended-application": "text-mining",
            "content-version": "vor",
            "content-type": "text/plain",
            "URL": "http://api.elsevier.com/content/article/PII:S0022283600942827?httpAccept=text/plain"
          }
        ],
        "deposited": {
          "date-parts": [
            [
              2016,
              5,
              16
            ]
          ],
          "date-time": "2016-05-16T00:15:24Z",
          "timestamp": 1463357724000
        },
        "score": 1,
        "subtitle": [],
        "issued": {
          "date-parts": [
            [
              2001,
              1
            ]
          ]
        },
        "alternative-id": [
          "S0022283600942827"
        ],
        "URL": "http://dx.doi.org/10.1006/jmbi.2000.4282",
        "ISSN": [
          "0022-2836"
        ],
        "subject": [
          "Molecular Biology"
        ]
      }
    ],
    "total-results": 2,
    "facets": {}
  }
}
{% endhighlight %}
