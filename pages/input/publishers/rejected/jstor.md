---
layout: page
title: JSTOR
---

# JSTOR

## Description de l'échantillon

* Un seul article [RUSSIA. Anthrax in Odessa, and Aksai, Astrakhan](http://www.jstor.org/stable/41471087).  Public Health Reports (1896-1970)
Vol. 17, No. 38 (September 19, 1902), pp. 2189-2190

## Structure des fichiers

Un fichier

## Remarques

 * Il semble que c'est une DTD propre à JSTOR (mais cela ressemble à NLM)
 * Pas de DOI

## Exemple

Exemple pour cet article <http://dx.doi.org/10.1146/annurev-polisci-053013-041156>

{% highlight xml %}
<article dtd-version="1.0" article-type="research-article">
   <front>
      <journal-meta>
         <journal-id xmlns:xlink="http://www.w3.org/1999/xlink" journal-id-type="jstor">publhealrepo1896</journal-id>
         <journal-id xmlns:xlink="http://www.w3.org/1999/xlink" journal-id-type="jstor">j101449</journal-id>
         <journal-title-group xmlns:xlink="http://www.w3.org/1999/xlink">
            <journal-title>Public Health Reports (1896-1970)</journal-title>
         </journal-title-group>
         <publisher>
            <publisher-name>Public Health and Marine Hospital Service</publisher-name>
         </publisher>
         <issn xmlns:xlink="http://www.w3.org/1999/xlink" pub-type="ppub">00946214</issn>
      </journal-meta>
      <article-meta>
         <article-id xmlns:xlink="http://www.w3.org/1999/xlink" pub-id-type="jstor">41471087</article-id>
         <article-categories>
            <subj-group>
               <subject>FOREIGN AND INSULAR</subject>
            </subj-group>
         </article-categories>
         <title-group>
            <article-title>RUSSIA. Anthrax in Odessa, and Aksai, Astrakhan</article-title>
         </title-group>
         <contrib-group>
            <contrib>
               <string-name xmlns:xlink="http://www.w3.org/1999/xlink">
                  <given-names>Thos. E.</given-names>
                  <surname>Heenan</surname>
               </string-name>
            </contrib>
         </contrib-group>
         <pub-date xmlns:xlink="http://www.w3.org/1999/xlink">
            <day>19</day>
            <month>9</month>
            <year>1902</year>
         </pub-date>
         <volume>17</volume>
         <issue>38</issue>
         <issue-id xmlns:xlink="http://www.w3.org/1999/xlink">i40071610</issue-id>
         <fpage>2189</fpage>
         <lpage>2190</lpage>
         <self-uri xmlns:xlink="http://www.w3.org/1999/xlink"
                   xlink:href="http://www.jstor.org/stable/41471087"/>
         <custom-meta-group xmlns:xlink="http://www.w3.org/1999/xlink">
            <custom-meta>
               <meta-name>lang</meta-name>
               <meta-value>eng</meta-value>
            </custom-meta>
         </custom-meta-group>
      </article-meta>
   </front>
</article>
{% endhighlight %}
