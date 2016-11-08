---
layout: page
title: Stories - Swissbib Integration
numbering: yes
---

# Stories - Swissbib Integration

This is a list of Stories (from the SCRUM method) for the integration of NL content in swissbib

They are sorted by priority and are written with a user point-of-view.

## Story A : Check if a user has an authorized IP address

When I open Swissbib in my browser, the system can recognize if I am in the network of a Swiss University (or any other authorized organization from the Konsortium). This check is based on IP address and the list of authorized IP addresses provided by the consortium.

## Story I : Decide how the article metadata are encoded in marc

Especially, how to represent

```
<volume>27</volume>
<issue>3</issue>
<fpage>160</fpage>
<lpage>168</lpage>
```

in marc (using 773$q) ?



## Story B : Construct the url to access the content (for authorized IP addresses)

If I am in an authorized network, the link to the fulltext goes directly to the content. Example :

**De Gruyter**

Article : ABI-Technik. Volume 27, Issue 3, Pages 160–168, ISSN (Online) 2191-4664, ISSN (Print) 0720-6763, DOI: 10.1515/ABITECH.2007.27.3.160, March 2011

URL : <https://www.degruyter.com/openurl?genre=article&issn=2191-4664&volume=27&issue=3&spage=160>

**Cambridge**

Article : Africa, Volume 85, Issue 3, pp. 385-394,  ISSN: 0001-9720 (Print), 1750-0184 (Online), DOI: 10.1017/S0001972015000248

URL (using article identifier) : <http://www.cambridge.org/core/product/identifier/S0001972015000248/type/JOURNAL_ARTICLE>
Not working : URL (openurl) : <http://www.cambridge.org/core/openurl?genre=article&issn=1750-0184&volume=85&issue=3&spage=385>


**Oxford**

Article :  Acta Biochim Biophys Sin (2016) volume 48 issue 9, pp 856-858. Online ISSN 1745-7270 - Print ISSN 1672-9145.  doi: 10.1093/abbs/gmw069.
The code after the http:// is a url-code which is not part of the metadata delievered by Oxford. But Oxford provides a mapping on its website <http://www.oxfordjournals.org/en/help/tech-info/linking.html>

URL : <http://abbs.oxfordjournals.org/lookup/doi/10.1093/abbs/gmw069>



## Story J : Send private users to registration process if needed

If I am not in an authorized network, the link requires a Swissbib registration (same as save in list for example). If the person already registered for national licences (using the new national_licence_user table), we send it back to the publishers platform using link from Story C.

If the person didn't register we send her to the tab National Licences (https://test.swissbib.ch/NationalLicences from branch feature/nationalLicence) in the user account to activate its National Licence account.


## Story C : Construct the url to access the content (for private users - unauthorized IP addresses)

If I am not in an authorized network, the url to access the content changes. It requires a Shibboleth authentication on the publisher platform first.

The url is the same as in Story B, but :

 * needs to prepend `https://www.degruyter.com/applib/openathens?entityID=https%3A%2F%2Feduid.ch%2Fidp%2Fshibboleth&openAthens2Redirect=`
 * needs to url-encode the url from Story B
 * needs to add some parameters at the end (for oxford)

Result :

 * De Gruyter : <https://www.degruyter.com/applib/openathens?entityID=https%3A%2F%2Feduid.ch%2Fidp%2Fshibboleth&openAthens2Redirect=https%3A%2F%2Fwww.degruyter.com%2Fopenurl%3Fgenre%3Darticle%26issn%3D2191-4664%26volume%3D27%26issue%3D3%26spage%3D160>
 * Cambridge : <https://shibboleth.cambridge.org/Shibboleth.sso/discovery?entityID=https%3A%2F%2Feduid.ch%2Fidp%2Fshibboleth&target=https://shibboleth.cambridge.org/CJOShibb2/index?app=https://www.cambridge.org/core/shibboleth?ref=%2Fcore%2Fproduct%2Fidentifier%2FS0001972015000248%2Ftype%2FJOURNAL_ARTICLE>
 * Oxford New Platform: <https://shibboleth.highwire.org/session/init?entityID=https%3A%2F%2Feduid.ch%2Fidp%2Fshibboleth&hw-shib-return-uri=http%3A%2F%2Fbrain.oxfordjournals.org%2Flookup%2Fdoi%2F10.1093%2Fbrain%2Fawv301&subcode=oupjournals&env=prod>


For Oxford Old platform, it is the same, but it might be useful to test these url's from time to time :

  * Oxford Old Platform: <https://shibboleth.highwire.org/session/init?entityID=https%3A%2F%2Feduid.ch%2Fidp%2Fshibboleth&hw-shib-return-uri=http%3A%2F%2Fabbs.oxfordjournals.org%2Flookup%2Fdoi%2F10.1093%2Fabbs%2Fgmw069&subcode=oupjournals&env=prod>




## Story D : Initial integration

The NL content available as unified JATS XML is integrated in CBS and pushed to SOLR

## Story E : ongoing integration

The NL content is updated weekly based on the publisher's deliveries.


## Story F : create a facet/collection for NL

It is possible to restrict content to NL with a facet (at the same level as the ZORA or e-Periodica for example)

## Story G : Covers

I have found an article from a specific journal in Swissbib. The thumbnail of this article is the journal cover.

Example : <https://test.swissbib.ch/Record/NLoxford> should have <http://acn.oxfordjournals.org/content/31/5.cover.gif> as a thumbnail. The matching is done based on the value of the marc field 773$x.


## Story H : Landing Page

Create a good looking landing page for national licences :

 * similar to <http://www.e-periodica.ch/>
 * based on the covers
 * maybe with journal title on top
 * and maybe with subject browsing as in
