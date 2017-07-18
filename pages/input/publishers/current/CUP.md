---
layout: page
title: Cambridge University Press
---

# Cambridge University Press (CUP)

## Description de l'échantillon

2 articles : <http://dx.doi.org/10.1017/sjp.2014.2> et <http://dx.doi.org/10.1017/S0031182011000941>.

## Structure des fichiers

Un fichier XML par article


## Remarque de l'éditeur

Email de ameulekamp@cambridge.org, 28.9.2015.

> Please note that not all Journal Archive content is available with XML metadata. We cannot supply XML metadata for the whole of the archive. Our journals were created with SGML instead of XML until 2007 so a large number of titles have at least some content without XML metadata. Nor is all XML content available in a single XML DTD. We have used NLM2.2, JATS0.4 and JATS1.

## Remarques

 * cela utilise la DTD NLM version 2.2 (2006) <http://dtd.nlm.nih.gov/publishing/2.2/>
 * mais aussi d'autres DTD
 * ils déposent les métadonnées sur notre serveur ftp www.swissbib.org dans le répertoire cambridge avec le user `247159-9-cambridge`
 * Juillet 2016 : mise en place du dépôt par SFTP sur cambridge@sb-coai1.swissbib.unibas.ch. L'adresse IP de Cambridge a dû être ajoutée au firewall de URZ.
 * message Alyssa 5.2.2016 : ils acceptent la clause CC0 ainsi :


  > **9. Metadata Licence**. Publisher delivers the Metadata for bibliographic materials under a Creative Commons Zero licence (CC0 see http://creativecommons.org/publicdomain/zero/1.0/) with special reference to the following uses:
  >
  > ·        To transform all metadata to a common format to ingest it in Swiss Libraries Information Systems (for example http://www.swissbib.ch). After processing this metadata, the metadata will be provided to university libraries in Switzerland to integrate it in their own information systems using this common format (e.g. JATS 1.0).
  >
  > ·        To transform all bibliographic metadata from Swiss libraries towards linked open data (RDF/XML). The objective is to provide better search possibilities for users.

Remarque du service juridique UB Basel : "die beiden Erklärungen oder Ergänzungen haben aus meiner Sicht keine einschränkende Bedeutung, die Metadaten sind urheberrechtsfrei und Ihr könnt sie verwenden"

 *  Transfertitel kommen ab 2015 dazu, aber die Archive werden dafür nicht freigeschaltet.
 * Exemple Wayfless link <https://shibboleth.cambridge.org/Shibboleth.sso/discovery?entityID=https://aai-logon.unibas.ch/idp/shibboleth&target=https://shibboleth.cambridge.org/CJOShibb2/index?app=journals.cambridge.org/action/loginShibb> : ne marche pas en juillet 2016 mais Cambridge y travaille.
 * Sur la nouvelle plateforme (core). Dans l'admin, on peut configurer le wayfless pour avoir un raccourci. Cela donne ceci <https://www.cambridge.org/core/idp/unibas>. Mais en fait c'est seulement un lien vers la homepage qui est shibbolethisé.
 * Lien wayfless confirmé par Cambridge le 12.12.2016 (using PII) :  <http://www.cambridge.org/core/product/identifier/S0001972015000248/type/JOURNAL_ARTICLE>

## Réception des données le 18.2.2016

 * 31 dossiers (a priori un journal par dossier)
 * chaque dossier contient une série de zip représentant chaque issue
 * 4905 fichiers zip
 * le tout fait 208.3 Mo
 * Extraction : `find . -name "*.zip" | while read filename; do unzip  -o -d ../extracted/ "$filename"; done;`
 * Une fois extrait : 108'699 fichiers xml et 19'246 fichiers sgm.

## Réception des données le 22.2.2016
 * 20 journaux de plus

## Réception des données : final
 * en plusieurs étapes successives, par journaux cela semble être terminé le 26.2
 * 391 dossiers (un par journal). 51777 fichiers zip. 1.8 Go.
 * Une fois dézippé : 1'212'415 éléments (y compris répertoires), totalisant 4.1 Go
 * Parfois il y a des fichier `*.xml` qui sont en fait des fichiers SGML (qui ont normalement une extension .sgm). Exemple `app/cjo/content/AGS/AGS136_04`. Chaque fichier est dupliqué. Pour les retrouver : `grep -rL "<?xml" --include="*.xml"`. Il y a plus de 27301 fichiers de ce type. Ils sont dans `files.txt` et je les ai déplacé dans un le répertoire `sgml-in-xml-files`. J'ai laissé les fichiers .sgm à l'endroit initial.
 * Il manque des informations par rapport à la plateforme éditeur. Par exemple pour <http://journals.cambridge.org/action/displayAbstract?fromPage=online&aid=8630253&fileId=S0021223700012425>, impossible de trouver la online date dans les métadonnées.
 * Il y a parfois 2003-2004 dans le champ year.
 * Les métadonnées ont été livrées pour tous les journaux qui sont dans le contrat à l'exception de LER et GLO qui sont en cours de traitement.
 * Il y a des doi qui ne se résolvent pas : 10.1017/S026134090001941X, 10.1017/S0261340900019469, 10.1017/S0261340900019536
 * Il y a seulement 1601 articles qui ont des informations de licences (sur la plateforme 2256 sont en open-access)
 * L'ISSN print de Queensland Journal of Guidance and Counselling est manquant. Il y a toujours le même pissn et eissn.
 * Il y a des articles avec des années erronées (c'est des front et back matter)
   * <http://journals.cambridge.org/action/displayAbstract?fromPage=online&aid=9513174&fulltextType=XX&fileId=S0066477400000654>
   * <http://journals.cambridge.org/action/displayAbstract?fromPage=online&aid=9513416&fulltextType=XX&fileId=S0066477400000976>
   * front et back matter de <http://journals.cambridge.org/action/displayIssue?decade=2000&jid=ICE&volumeId=28&issueId=05&iid=9376757>
   * 1895 au lieu de 1985 :
     *        **"_id": "10.2307/3171719"**
     *       "journal-title": "History in Africa",
     *     "article-title": "Power and Dynastic Conflict in Mampon",
     *     "contributor": "T.C. McCaskie",
     *         **"_id": "10.2307/3171723",**
     *  "journal-title": "History in Africa",
     *    "article-title": "The Late Great Plot: The Official Delusion Concerning the Xhosa Cattle Killing 1856-1857",  
   * il y a des doi qui résolvent sur JSTOR (l'exemple ci-dessus)
   * il y a des journaux complètement gratuits dans le paquet (MTO, MIJ, ...). les informations sur la gratuité ne sont pas dans les métadonnées.

## Réception des données : 7.9.2016

 * delivery on basel ftp server : sb-coai1.swissbib.unibas.ch
 * 997 éléments, totalisant 29.4 Mo
 * 293 dossiers, mais certains sont vides
 * 704 fichiers zip
 * Contient les métadonnées pour les articles 2016 (ou fin 2015).
 * N'a plus la structure des directory cjo/app/volume/issue comme auparavant

## Réception des données : 13.9.2016

 * the journals GLO and LER are delivered this time


## Processing des fichiers sgml

 * il y a 145'463 fichiers SGML dont 27'301 ont une extension `xml` et le reste ont une extension `sgm`. Il y a 177 journaux qui ont une partie de leur contenu en SGML.
 * il y a un script `cambridge_convert_sgml.sh` qui fait la conversion à l'aide de l'utilitaire `osx`
 * cela prend environ 1h de convertir tous les sgml en xml
 * il y a 4681 fichiers qui ne passent pas dans ES, je reçois une erreur `Entity starts and ends are not balanced' while processing object: /media/lionel/Data/swissbib-data/cambridge/extracted/app/cjo/sgml-in-xml-converted/multiple_journals/S0007087400004179h.xml` mais les fichiers ont l'air corrects. J'ignore ce point. Le problème semble être une arborescence header/article/header ??? Mais ils sont quand même indexés en fait. C'est un peu étrange...

## Transformation vers Swissbib-jats

 * 22.9.2016 : transformation vers swissbib-jats. *55'134* files don't pass xml validation. Most common errors
 * wrong order for permissions tag. It's an error in the delivery of xml

```
5702  element article-meta: validity error : Element article-meta content does not follow the DTD, expecting (article-id* , article-categories? , title-group? , (contrib-group | aff | aff-alternat
ives | x)* , author-notes? , pub-date* , volume* , volume-id* , volume-series? , issue* , issue-id* , issue-title* , issue-sponsor* , issue-part? , volume-issue-group* , isbn* , supplement? , (((fpag
e , lpage?)? , page-range?) | elocation-id)? , (email | ext-link | uri | product | supplementary-material)* , history? , permissions? , self-uri* , (related-article | related-object)* , abstract* , t
rans-abstract* , kwd-group* , funding-group* , conference* , counts? , custom-meta-group?), got (article-id article-id article-id title-group contrib-group aff pub-date volume issue fpage lpage histo
ry abstract counts custom-meta-group permissions )
```

  * idref in abstract to references but no references in the xml

```
./SJP/SJP18/S1138741615000372h.xml:58: element xref: validity error : IDREFS attribute rid references an unknown ID "ref24"
```


## Ongoing delivery

 * cambridge livre régulièrement les updates sur /swissbib/harvesting/cambridge sur sb-coai1 depuis mars 2017

## Commercial Use

Conditions générales :

> **Commercial Use** for the purposes of monetary reward (whether by or for Licensee, a Consortium Member, an Authorised User, or any other person or entity) by means of sale, resale, loan, transfer, hire or other form of exploitation of the Product(s). For the avoidance of doubt, use by a Consortium Member or Authorised User of the Product(s) in the course of research funded by a commercial organisation is not deemed to constitute Commercial Use. Recovery of costs is not deemed as Commercial Use;


## Contact technique

The technical coordinator on this project is Peter White.

Peter White  
Online Systems Manager, Journals  
Cambridge University Press  
University Printing House  
Shaftesbury Road  
Cambridge  
CB2 8BS  

pwhite@cambridge.org  
01223 325506  



## Exemples (XML and SGML)

Exemple (XML) pour cet article <http://dx.doi.org/10.1017/S0031182011000941>

{% highlight xml %}
<?xml version="1.0" encoding="US-ASCII"?>
<!DOCTYPE article
  PUBLIC "-//NLM//DTD Journal Publishing DTD v2.2 20060430//EN" "journalpublishing.dtd">
<article
    xmlns:xlink="http://www.w3.org/1999/xlink" dtd-version="2.2" article-type="research-article" xml:lang="EN">
    <front>
        <journal-meta>
            <journal-id journal-id-type="publisher-id">PAR</journal-id>
            <journal-title>Parasitology</journal-title>
            <abbrev-journal-title>Parasitology</abbrev-journal-title>
            <issn pub-type="ppub">0031-1820</issn>
            <issn pub-type="epub">1469-8161</issn>
            <publisher>
                <publisher-name>Cambridge University Press</publisher-name>
                <publisher-loc>Cambridge, UK</publisher-loc>
            </publisher>
        </journal-meta>
        <article-meta>
            <article-id pub-id-type="doi">10.1017/S0031182011000941</article-id>
            <article-id pub-id-type="pii">S0031182011000941</article-id>
            <article-id pub-id-type="publisher-id">00094</article-id>
            <title-group>
                <article-title>Male gametocyte fecundity and sex ratio of a malaria parasite,
                    <italic>Plasmodium mexicanum</italic>
                </article-title>
                <alt-title alt-title-type="left-running">A. T. Neal</alt-title>
                <alt-title alt-title-type="right-running">
                    <italic>Plasmodium</italic> fecundity and sex ratio
                </alt-title>
            </title-group>
            <contrib-group>
                <contrib corresp="yes">
                    <name>
                        <surname>NEAL</surname>
                        <given-names>A. T.</given-names>
                    </name>
                    <xref ref-type="aff" rid="aff1"/>
                    <xref ref-type="corresp" rid="cor1">*</xref>
                </contrib>
            </contrib-group>
            <aff id="aff1">
                <addr-line>Department of Biology</addr-line>,
                <institution>University of Vermont</institution>,
                <addr-line>Burlington, VT 05405</addr-line>,
                <country>USA</country>
            </aff>
            <author-notes>
                <corresp id="cor1">
                    <label>*</label>Corresponding author: Tel:
                    <phone>001 802 656 0702</phone>. Fax:
                    <fax>001 802 656 2914</fax>. E-mail:
                    <email xlink:href="aneal@uvm.edu">aneal@uvm.edu</email>
                </corresp>
            </author-notes>
            <pub-date pub-type="ppub">
                <month>09</month>
                <year>2011</year>
            </pub-date>
            <pub-date pub-type="epub">
                <day>15</day>
                <month>07</month>
                <year>2011</year>
            </pub-date>
            <volume>138</volume>
            <issue>10</issue>
            <fpage seq="3">1203</fpage>
            <lpage>1210</lpage>
            <history>
                <date date-type="received">
                    <day>31</day>
                    <month>01</month>
                    <year>2011</year>
                </date>
                <date date-type="rev-recd">
                    <day>25</day>
                    <month>03</month>
                    <year>2011</year>
                </date>
                <date date-type="rev-recd">
                    <day>28</day>
                    <month>04</month>
                    <year>2011</year>
                </date>
                <date date-type="rev-recd">
                    <day>10</day>
                    <month>05</month>
                    <year>2011</year>
                </date>
                <date date-type="accepted">
                    <day>11</day>
                    <month>05</month>
                    <year>2011</year>
                </date>
            </history>
            <permissions>
                <copyright-statement>Copyright &#169; Cambridge University Press 2011</copyright-statement>
                <copyright-year>2011</copyright-year>
                <copyright-holder>Cambridge University Press</copyright-holder>
            </permissions>
            <abstract abstract-type="normal">
                <title>SUMMARY</title>
                <p>Evolutionary theory predicts that the sex ratio of
                    <italic>Plasmodium</italic> gametocytes will be determined by the number of gametes produced per male gametocyte (male fecundity), parasite clonal diversity and any factor that reduces male gametes' ability to find and combine with female gametes. Despite the importance of male gametocyte fecundity for sex ratio theory as applied to malaria parasites, few data are available on gamete production by male gametocytes. In this study, exflagellating gametes, a measure of male fecundity, were counted for 866 gametocytes from 26 natural infections of the lizard malaria parasite,
                    <italic>Plasmodium mexicanum</italic>. The maximum male fecundity observed was 8, but most gametocytes produced 2&#8211;3 gametes, a value consistent with the typical sex ratio observed for
                    <italic>P. mexicanum</italic>. Male gametocytes in infections with higher gametocytaemia had lower fecundity. Male fecundity was not correlated with gametocyte size, but differed among infections, suggesting genetic variation for fecundity. Fecundity and sex ratio were correlated (more female gametocytes with higher fecundity) as predicted by theory. Results agree with evolutionary theory, but also suggest a possible tradeoff between production time and fecundity, which could explain the low fecundity of this species, the variation among infections, and the correlation with gametocytaemia.
                </p>
            </abstract>
            <kwd-group kwd-group-type="">
                <title>Key words</title>
                <kwd>malaria</kwd>
                <kwd>sex ratio</kwd>
                <kwd>male fecundity</kwd>
                <kwd>
                    <italic>Plasmodium</italic>
                </kwd>
                <kwd>gamete production</kwd>
            </kwd-group>
            <counts>
                <page-count count="8"/>
            </counts>
            <custom-meta-wrap>
                <custom-meta>
                    <meta-name>pdf</meta-name>
                    <meta-value>S0031182011000941a.pdf</meta-value>
                </custom-meta>
            </custom-meta-wrap>
        </article-meta>
    </front>
</article>
{% endhighlight %}



Exemple (SGML) pour cet article <http://dx.doi.org/10.1017/S0022112056000226>

{% highlight xml %}
<!DOCTYPE article SYSTEM "cupjnl2_1.dtd">
<article dtdver="2.1">
    <header>
        <issue>
            <pinfo>
                <pnm>Cambridge University Press</pnm>
                <loc>Cambridge, UK</loc>
            </pinfo>
            <jinfo>
                <jid>FLM</jid>
                <jtl>Journal of Fluid Mechanics</jtl>
                <jabt>J. Fluid Mech.</jabt>
                <issn>0022-1120</issn>
                <eissn>1469-7645</eissn>
            </jinfo>
            <pubinfo>
                <vid>1</vid>
                <iid>4</iid>
                <cd year="1956" month="10">
            </pubinfo>
        </issue>
        <artcon>
            <genhdr language="EN">
                <artinfo>
                    <aid>22</aid>
                    <doi>10.1017/S0022112056000226</doi>
                    <altid>
                        <pii>S0022112056000226</pii>
                    </altid>
                    <artty artty="RA">
                        <ppct count="22">
                        <ppf>366</ppf>
                        <ppl>387</ppl>
                        <crn crt="full">1956 Cambridge University Press</crn>
                        <hst>
                            <re year="1956" month="4" day="24">
                        </hst>
                </artinfo>
                <tig>
                    <atl>On the theory of hypersonic flow past plane and axially symmetric bluff bodies</atl>
                    <atl purpose="recto" abbrev="abatl">On the theory of hypersonic flow past bluff bodies</atl>
                    <atl purpose="verso" abbrev="abau">N. C. Freeman</atl>
                </tig>
                <aug>
                    <au>
                        <fnms>N. C.</fnms>
                        <snm>Freeman</snm>
                        <norm>Freeman NC</norm>
                        <orf rid="a1">
                    </au>
                    <aff>
                        <oid id="a1">
                        <onm>Department of Mathematics</onm>, University of Manchester
                    </aff>
                </aug>
                <abs source="PR">
                    <p>The &lsquo;Newtonian-plus-centrifugal&rsquo; approximate solution (Busemann (1933) and Ivey (1948)) for hypersonic flow past plane and axially symmetric bluff bodies in gases with the ratio of the specific heats &lambda; constant and equal to unity is rederived using &lsquo;boundary layer&rsquo; techniques together with the von Mises variables
                        <e1>x</e1> and &psi;. A method of successive approximations then gives a closer approximation to this solution for &epsi; (&lambda; &minus; 1)&sol;(&lambda; + 1) small and the free-strea Mach number infinite. Formulae for the streamlines, shock shape and pressure distribution are determined to this approximation. These formulae are valid for any plane or axially symmetric shape, giving the &lsquo;stand-off&rsquo; distance of the shock wave from the body as &half;&epsi;log(4|3&epsi;) and &epsi; times the nose radius of curvature for plane and axially-symmetric flows respectively. Particular results are computed for a number of special shapes. For certain shapes, the theory has a singular point where the first approximation to the pressure vanishes (&theta; = 60&deg; for a sphere). Actually, the theory is not applicable where the pressure becomes too small. The corresponding theory for gases of general thermodynamic properties is deduced, the approximation being valid provided the total energy of the gas is large compared with the energy contained in the translational modes of the gas molecules.
                    </p>
                </abs>
            </genhdr>
        </artcon>
    </header>
</article>

{% endhighlight %}
