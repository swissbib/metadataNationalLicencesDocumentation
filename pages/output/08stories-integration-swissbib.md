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

## Story B : Construct the url to access the content (for authorized IP addresses)

If I am in an authorized network, the link to the fulltext goes directly to the content. Example :

Article : ABI-Technik. Volume 27, Issue 3, Pages 160–168, ISSN (Online) 2191-4664, ISSN (Print) 0720-6763, DOI: 10.1515/ABITECH.2007.27.3.160, March 2011

URL : <https://www.degruyter.com/openurl?genre=article&issn=2191-4664&volume=27&issue=3&spage=160>



## Story C : Construct the url to access the content (for private users - unauthorized IP addresses)

If I am not in an authorized network, the url to access the content changes. It requires a Shibboleth authentication first.

The url is the same as in Story B, but :

 * needs to prepend `https://www.degruyter.com/applib/openathens?entityID=https%3A%2F%2Feduid.ch%2Fidp%2Fshibboleth&openAthens2Redirect=`
 * needs to url-encode the url from Story B

Result :
<https://www.degruyter.com/applib/openathens?entityID=https%3A%2F%2Feduid.ch%2Fidp%2Fshibboleth&openAthens2Redirect=https%3A%2F%2Fwww.degruyter.com%2Fopenurl%3Fgenre%3Darticle%26issn%3D2191-4664%26volume%3D27%26issue%3D3%26spage%3D160>

Note : this url doesn't work right now, but it is possible to use unibas shibboleth endpoint instead :

<https://www.degruyter.com/applib/openathens?entityID=https%3A%2F%2Faai-logon.unibas.ch%2Fidp%2Fshibboleth&openAthens2Redirect=https%3A%2F%2Fwww.degruyter.com%2Fopenurl%3Fgenre%3Darticle%26issn%3D2191-4664%26volume%3D27%26issue%3D3%26spage%3D160>


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
