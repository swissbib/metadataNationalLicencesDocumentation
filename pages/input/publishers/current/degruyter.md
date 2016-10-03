---
layout: page
title: De Gruyter
---

# De Gruyter

## Description de l'échantillon

 * 5 fichiers zip pour 5 journaux différents, totalisant 37 articles
  * Polish Journal of Surgery (9 articles)
  * Russian Journal of Numerical Analysis and Mathematical Modelling (5)
  * Statistical Applications in Genetics and Molecular Biology (6)
  * Text & Talk (4)
  * Zeitschrift für Physikalische Chemie (13)
 * 1 fichier marc qui contient 346 notices décrivant les périodiques

## Structure des fichiers

Pour chaque journal, il y a une arborescence

```
/pjs/pjs.2015.87.issue-6/issue-files
/pjs/pjs.2015.87.issue-6/pjs-2015-0055
```

 * `pjs` est pour le journal
 * `pjs.2015.87.issue-6` correspond au numéro 6 du volume 87 de 2015
 * `issue-files` contient un fichier xml qui fait office de table des matières
 * `pjs-2015-0055` contient un fichier xml avec les métadonnées de l'article no. 0055
 * idem pour `pjs-2015-0056`, `pjs-2015-0057`, `pjs-2015-0058`, ...

## Remarques

 * Nombre de pages 1826-2014 : 5.523.589 pages
 * Nombre d'articles 1826-2014 : ~280.385 articles
 * Pour le journal PJS, la DTD est NLM 2012
 * Pour le journal Text & Talk, la DTD est -//Atypon//DTD Atypon Systems Archival NLM DTD Suite v2.2.0 20090301//EN
 * Pour le journal RNAM, il y a aussi le fulltext
 * Mail de Mme Näkel du 17.12.2015 : *"we agree to a Creative Commons Zero licence for our metadata"*
 * Bei DeGruyter kommen keine Transertitel mehr dazu. Hier haben wir eine feste Kollektion, die sich abgesehen von den neuen Volumes nicht verändern wird

## Linking

 * il y a des infos ici [FAQ for librarians](http://www.degruyter.com/page/286)
 * Deep links that point directly to specific journal articles (eg originating in linkresolvers or other systems) must be changed to reflect the following link syntax of De Gruyter Online:
 `http://www.degruyter.com/JournalArticles?source=/j/[journal code]&volume=[volume number]&issue=[issue number]&page=[page number]`
 * In brackets [ ] is the information that has to be added from the source (without brackets). Accesing a specific article from volume 49, issue 11 and page 1873 from the journal Clinical Chemistry and Laboratory Medicine (CCLM) looks like this: <http://www.degruyter.com/JournalArticles?source=/j/cclm&volume=49&issue=11&page=1873>
 * Access via inbound OpenURL from linkresolvers on article level is also possible. The syntax is: `http://www.degruyter,com/openurl?genre=[Typ]&issn=[ISSN]&volume=[volume number]&issue=[issue number]&spage=[start page]&epage=[end page]` (individual parts can be omitted).
 * Which is for example: <http://www.degruyter.com/openurl?genre=article&issn=1612-703X&volume=90&issue=2&spage=396&epage=404>. **Remarque** : on ne peut pas mettre le DOI là-dedans, cela ne fonctionne pas
 * Exemple d'une SP-side WAYFLESS url
 <https://www.degruyter.com/applib/openathens?entityID=https%3A%2F%2Faai-logon.unibas.ch%2Fidp%2Fshibboleth&openAthens2Redirect=https%3A%2F%2Fwww.degruyter.com%2Fopenurl%3Fgenre%3Darticle%26issn%3D1612-703X%26volume%3D90%26issue%3D2%26spage%3D396%26epage%3D404>. Confirmé par De Gruyter en Juillet 2016. Il n'y a pas de liens WAYFLESS qui contiennent uniquement le doi pour la plateforme De Gruyter.


## Réception des données le 18 décembre 2015

 * Contenu : *all content from our Journal Archive package*
 * via FTP (Server: ftp.degruyter.de, login and password: in swissbib password safe)
 * 33'340 fichiers zip totalisant 8.1 Go
 * il y a le contenu intégral de la plateforme, y compris le fulltext dans le xml (qu'on n'a pas le droit d'exploiter)
 * il y a aussi parfois des "supplementary material" (environ 200 fichiers) comme par exemple pour <http://www.degruyter.com/view/j/ael.2012.2.issue-1/2152-2820.1042/2152-2820.1042.xml#supplementaryMaterialBlock> ou alors des images qui sont liées dans le xml
 * il y a deux fichiers pdf contenant de la documentation sur les formats, on y apprend notamment que les valeurs suivantes sont autorisées pour @article-type (mais ce champ est très peu rempli):
    * research-article
    * article-commentary
    * book-review
    * brief-report
    * calendar
    * case-report
    * erratum
    * corrigenda
    * editorial
    * interview
    * letter
    * news
    * proceedings-paper
    * rapid-communication
    * reply
    * retraction
    * review-article
    * miscellaneous
    * frontmatter
    * graphical-abstract
    * meeting-report
 * il y a aussi deux fichiers zip contenant les deux DTD utilisées : jats-publishing-dtd-1.0.zip et atypon_archive-interchange-dtd-3.0.2.zip
 * Pour extraire le tout sans les fichiers tables des matières, dans le répertoire "extracted" : `unzip "*.zip" -d extracted -x */issue-files/*`
 * malheureusement, il y a des cas où la table des matières n'est pas dans le répertoire `issue-files`, par [exemple](http://dx.doi.org/10.7788/annalen-1985-frontmatterjg) ou alors des condensés de [front matters](http://dx.doi.org/10.7788/annalen-1985-frontmatterjg). Le pire est qu'on ne peut pas les retrouver grâce aux métadonnées, car il n'y a pas de `article-type`. Il faudrait se baser sur le nom du fichier ou le titre ? Il y a aussi des [listes d'adresses](http://dx.doi.org/10.7788/annalen-1985-jg93)
 * Remarque étrange reçue dans l'email *For the older content (especially for the issues published in 2012 and 2013), the naming of the zip files is not always according to the guidelines. So, please do not rely on the zip names for information about which journal these belong to, but to the information within the XML – this should be correct.*
 * Une fois extrait : 21 Go, 517'000 fichiers xml plus un millier d'autres fichiers (eps, gif, ...) pour le matériel supplémentaire
 * il y a des éléments xml qui contiennent des `.` par exemple `xlink.href`, ce qui n'est pas vraiment une "best practice" et pose des problèmes par exemple avec elasticsearch
 * 25.2.2016 : mail robin, degruyter agreed to sms authentication for 48hours
 * Il y a des doi qui ne se résolvent pas : <http://dx.doi.org/10.1515/9783110192377.21>, <http://dx.doi.org/10.1524/hzhz.1937.156.jg.263>
 * Il y a des titres de périodiques erronés (par exemple 2007 comme titre)
 * Il y a deux périodiques pour lesquels les métadonnées ont été livrées mais qui ne sont pas dans la liste du contrat : Acta Geologica Polonica et Journal for Perspectives of Economic Political and Social Integration
 * Quand il n'y a pas d'indication de DTD alors la DTD est `<!DOCTYPE article  PUBLIC "-//Atypon//DTD Atypon Systems Archival NLM DTD Suite v2.2.0 20090301//EN" "nlm-dtd/archivearticle.dtd">` (mail de Katharina Rach du 13.5.2016)
 * il y parfois des `xlink.href` au lieu de `xlink:href` dans les métadonnées


Autres problèmes à notifier

 * il y a 3 doi avec des espaces : 10. 1515/dwir-2013-1061, 10. 1515/dwir-2013-1062, 10. 1515/jura-2013-0107. Les articles correspondants semblent absents de la plateforme.

## Transformation vers Swissbib-JATS

* Juillet 2016 : 1ère transformation totale vers Swissbib-JATS des ~480'000 articles de De Gruyter. 4'700 ne passent pas la validation JATS (taux d'erreur <1%). Voici les erreurs principales :

```
1014  element license: validity error : Element license content does not follow the DTD, expecting (ali:license_ref | license-p)+, got
 540  element article-meta: validity error : Element article-meta content does not follow the DTD, expecting (article-id* , article-categories? , title-group? , (contrib-group | aff | aff-alterna
tives | x)* , author-notes? , pub-date* , volume* , volume-id* , volume-series? , issue* , issue-id* , issue-title* , issue-sponsor* , issue-part? , volume-issue-group* , isbn* , supplement? , (((fp
age , lpage?)? , page-range?) | elocation-id)? , (email | ext-link | uri | product | supplementary-material)* , history? , permissions? , self-uri* , (related-article | related-object)* , abstract*
, trans-abstract* , kwd-group* , funding-group* , conference* , counts? , custom-meta-group?), got (article-id article-id article-categories title-group contrib-group pub-date pub-date volume issue
fpage lpage permissions permissions self-uri)
 468  element title-group: validity error : Element title-group content does not follow the DTD, expecting (article-title , subtitle* , trans-title-group* , alt-title* , fn-group?), got ()
 429  element name: validity error : Element name content does not follow the DTD, expecting (((surname , given-names?) | given-names) , prefix? , suffix?), got
 394  element article-meta: validity error : Element article-meta content does not follow the DTD, expecting (article-id* , article-categories? , title-group? , (contrib-group | aff | aff-alterna
tives | x)* , author-notes? , pub-date* , volume* , volume-id* , volume-series? , issue* , issue-id* , issue-title* , issue-sponsor* , issue-part? , volume-issue-group* , isbn* , supplement? , (((fp
age , lpage?)? , page-range?) | elocation-id)? , (email | ext-link | uri | product | supplementary-material)* , history? , permissions? , self-uri* , (related-article | related-object)* , abstract*
, trans-abstract* , kwd-group* , funding-group* , conference* , counts? , custom-meta-group?), got (article-id article-id article-categories title-group pub-date pub-date volume issue fpage lpage pe
rmissions permissions self-uri)
 373  element author-notes: validity error : Element author-notes content does not follow the DTD, expecting (label? , title? , (corresp | fn | p | x)+), got
 319  element permissions: validity error : Element permissions content does not follow the DTD, expecting (copyright-statement* , copyright-year* , copyright-holder* , (ali:free_to_read | licens
e)*), got (copyright-statement copyright-year license p )
 221  element author-notes: validity error : Element author-notes content does not follow the DTD, expecting (label? , title? , (corresp | fn | p | x)+), got ()
 166  element article-meta: validity error : Element article-meta content does not follow the DTD, expecting (article-id* , article-categories? , title-group? , (contrib-group | aff | aff-alterna
tives | x)* , author-notes? , pub-date* , volume* , volume-id* , volume-series? , issue* , issue-id* , issue-title* , issue-sponsor* , issue-part? , volume-issue-group* , isbn* , supplement? , (((fp
age , lpage?)? , page-range?) | elocation-id)? , (email | ext-link | uri | product | supplementary-material)* , history? , permissions? , self-uri* , (related-article | related-object)* , abstract*
, trans-abstract* , kwd-group* , funding-group* , conference* , counts? , custom-meta-group?), got (article-id article-id article-categories title-group contrib-group pub-date pub-date volume issue
fpage lpage permissions permissions self-uri abstract abstract abstract)
 159  element graphic: validity error : No declaration for attribute alt-version of element graphic
 120  element subscript: validity error : No declaration for element subscript
 105  element article-meta: validity error : Element article-meta content does not follow the DTD, expecting (article-id* , article-categories? , title-group? , (contrib-group | aff | aff-alterna
tives | x)* , author-notes? , pub-date* , volume* , volume-id* , volume-series? , issue* , issue-id* , issue-title* , issue-sponsor* , issue-part? , volume-issue-group* , isbn* , supplement? , (((fp
age , lpage?)? , page-range?) | elocation-id)? , (email | ext-link | uri | product | supplementary-material)* , history? , permissions? , self-uri* , (related-article | related-object)* , abstract*
, trans-abstract* , kwd-group* , funding-group* , conference* , counts? , custom-meta-group?), got (article-id article-id article-categories title-group pub-date pub-date volume issue permissions pe
rmissions self-uri)
```

La plupart sont dues a des fichiers invalides fournis par De Gruyter.




## Réception des données août 2016

 * De Gruyter a livré les métadonnées des articles 2015
 * Malheureusement, il y a quelques trous entre la première livraison et celle-ci (les issue de 2014 qui n'avaient pas encore été publiées fin 2015 manquent, par exemple lp)
 * A l'extraction : 1177 archives had warnings but no fatal errors. 2 archives had fatal errors. Mais impossible de trouver lesquelles ont des erreurs
 * cela fait 14678 fichiers xml
 * ils ont tous 2015 comme année de publication print
 * ils ont livré 4 journaux open access avec le reste.





## Commercial Use

4.6 The Licensee and the Authorized Users may use appropriate parts of the services to produce
printed teaching materials for use by the Authorized Users within the Licensee's Authorized Sites; these materials are not permitted to be used for re-sale or any other commercial purpose.

4.7 The Licensee and the Authorized Users are not permitted to use or exploit the services in whole or
in part by sale to third parties, rent, lease, loan or any other means for commercial or trade pur-
poses.
Walter de Gruyter GmbH. Genthiner Str. 13. 10785 Berlin.
Domicile Berlin. Amtsgericht Charlottenburg HRB 143490 B. Rechtsform: GmbH .
Executive Board: Dr. Anke Beck, Carsten Buhr
Chairman of the Supervisory Board : Rüdiger GebauerPage 4 from 30 of the General Ucense Agreement

4.8 The Licensee is not permitted to be a commercial party to paid documentation services and to
make the service available in whole or in part for this purpose. In exception to this, however, the
Licensee is allowed to respond to a request by another library to generate a print-out of part of
the service (e.g. an eJournal article or an eßook chapter) and to despatch this via non-commercial
inter-library loan services. This only applies to paper print-outs; electronic copies may not be
made. The use of the "Ariel Interlibrary Loan Software" for the transmission of a small proportion
of the service to a printer/fax of another library is allowed, a transmission to e-mail addresses is
not permitted . The transmission of whole eßooks via non-commercial inter-library loan services is
not allowed





## Contact

Personne responsable de la technique :

**Katharina Rach**  
Manager Publishing Technology and Applications  
DE GRUYTER  
Genthiner Str. 13  
10785 Berlin, Germany  
T +49 (0)30.260 05-354  
katharina.rach@degruyter.com  
www.degruyter.com  
Walter de Gruyter GmbH. Genthiner Str. 13. 10785 Berlin.


## Exemple

Exemple pour cet article <http://dx.doi.org/10.1515/pjs-2015-0058>


{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE article PUBLIC "-//NLM//DTD JATS (Z39.96) Journal Publishing DTD with OASIS Tables v1.0 20120330//EN" "JATS-journalpublishing-oasis-article1.dtd">
<article>
    <front>
        <journal-meta>
            <journal-id journal-id-type="publisher-id">pjs</journal-id>
            <journal-id journal-id-type="journal-code">pjs</journal-id>
            <journal-id journal-id-type="doi-code">pjs</journal-id>
            <journal-title-group>
                <journal-title>Polish Journal of Surgery</journal-title>
            </journal-title-group>
            <issn pub-type="epub">0032-373X</issn>
            <publisher>
                <publisher-name>De Gruyter Open</publisher-name>
            </publisher>
        </journal-meta>
        <article-meta>
            <article-id pub-id-type="publisher-id">pjs-2015-0058</article-id>
            <article-id pub-id-type="doi">10.1515/pjs-2015-0058</article-id>
            <article-categories/>
            <title-group>
                <article-title>The usefulness of the Mannheim Peritonitis index score in assessing the condition of patients treated for peritonitis</article-title>
            </title-group>
            <contrib-group>
                <contrib contrib-type="author">
                    <name>
                        <surname>Budzyński</surname>
                        <given-names>Piotr</given-names>
                    </name>
                    <xref ref-type="aff" rid="aff1">
                        <sup>1</sup>
                    </xref>
                </contrib>
                <contrib contrib-type="author">
                    <name>
                        <surname>Dworak</surname>
                        <given-names>Jadwiga</given-names>
                    </name>
                    <xref ref-type="aff" rid="aff1">
                        <sup>1</sup>
                    </xref>
                </contrib>
                <contrib contrib-type="author" corresp="yes">
                    <name>
                        <surname>Natkaniec</surname>
                        <given-names>Michał</given-names>
                    </name>
                    <email xlink.href="mailto:michal.natkaniec@uj.edu.pl">michal.natkaniec@uj.edu.pl</email>
                    <xref ref-type="aff" rid="aff1">
                        <sup>1</sup>
                    </xref>
                </contrib>
                <contrib contrib-type="author">
                    <name>
                        <surname>Pędziwiatr</surname>
                        <given-names>Michał</given-names>
                    </name>
                    <xref ref-type="aff" rid="aff1">
                        <sup>1</sup>
                    </xref>
                </contrib>
                <contrib contrib-type="author">
                    <name>
                        <surname>Major</surname>
                        <given-names>Piotr</given-names>
                    </name>
                    <xref ref-type="aff" rid="aff1">
                        <sup>1</sup>
                    </xref>
                </contrib>
                <contrib contrib-type="author">
                    <name>
                        <surname>Migaczewski</surname>
                        <given-names>Marcin</given-names>
                    </name>
                    <xref ref-type="aff" rid="aff1">
                        <sup>1</sup>
                    </xref>
                </contrib>
                <contrib contrib-type="author">
                    <name>
                        <surname>Matłok</surname>
                        <given-names>Maciej</given-names>
                    </name>
                    <xref ref-type="aff" rid="aff1">
                        <sup>1</sup>
                    </xref>
                </contrib>
                <contrib contrib-type="author">
                    <name>
                        <surname>Budzyński</surname>
                        <given-names>Andrzej</given-names>
                    </name>
                    <xref ref-type="aff" rid="aff1">
                        <sup>1</sup>
                    </xref>
                </contrib>
                <aff id="aff1">
                    <sup>1</sup>2nd Department of General Surgery Jagiellonian University in Cracow, Department of Endoscopic, Metabolic and Soft Tissue Malignancies Surgery, University Hospital in Cracow Kierownik
                </aff>
            </contrib-group>
            <pub-date pub-type="ppub">
                <day>1</day>
                <month>6</month>
                <year>2015</year>
            </pub-date>
            <pub-date pub-type="epub">
                <day>4</day>
                <month>8</month>
                <year>2015</year>
            </pub-date>
            <volume>87</volume>
            <issue>6</issue>
            <fpage>301</fpage>
            <lpage>306</lpage>
            <history>
                <date date-type="received">
                    <day>5</day>
                    <month>9</month>
                    <year>2015</year>
                </date>
            </history>
            <permissions>
                <copyright-statement>© by Michał Natkaniec</copyright-statement>
                <copyright-year>2015</copyright-year>
                <license license-type="open-access" xlink.href="http://creativecommons.org/licenses/by-nc-nd/3.0/">
                    <license-p>This work is licensed under the Creative Commons Attribution-NonCommercial-NoDerivatives 3.0 License.</license-p>
                </license>
            </permissions>
            <related-article related-article-type="pdf" xlink.href="pjs-2015-0058.pdf"/>
            <xml-citation-post-process status="unprocessed">2015-08-06T10:37:34.816+02:00</xml-citation-post-process>
            <original type="pdf" xlink.href="pjs-2015-0058.pdf"/>
            <abstract>
                <title>Abstract</title>
                <p>The aim of the study was to verify the Mannheim Peritonitis Index (MPI) suitability to determine the probability of death among patients in Polish population operated due to peritonitis and to assess the possibility of using the Index to determine the risk of postoperative complications, relaparotomy and need for postoperative hospitalization in intensive care unit. </p>
                <p>Material and methods. Retrospective analysis covered 168 patients (M: F = 83: 85, mean age = 48.45 years, SD ± 22.2) treated for peritonitis. The MPI score was calculated for each patient. According to MPI results, patients were divided to the appropriate groups (
                    &lt;21, 21‑29, > 29&gt; and within analyzed. The statistical analysis used Chi-square, Mann Withney U and Kolmogorov-Smirnov test. The best cut-off point for MPI was calculated on the basis of ROC analisys.
                    </p>
                    <p>Results. Mortality in the study group was 13.1%. In groups &lt;21, 21‑29 and &gt; 29 points according to MPI mortality was 1.75%, 28.13% and 50% respectively, the difference was statistically significant (p = 0.0124). Significant differences were observed in mortality depending on the diagnosis. Based on the ROC curve the cut-off point was identified as 32 with an accuracy of 85.9% and AUC = 81%. There has been a significant correlation between the MPI count and and the occurrence of: cardio-respiratory failure, acidosis, electrolyte imbalance, surgical wound complications, the need for treatment in the intensive care unit after surgery.
                        </p>
                        <p>Conclusions. The MPI is a simple and effective predictor of death among patients operated due to peritonitis. It can also provide assistance in assessing the risk of postoperative complications and the need for treatment in the intensive care unit.</p>
                    </abstract>
                    <kwd-group>
                        <title>Keywords </title>
                        <kwd>peritonitis</kwd>
                        <kwd>mortality</kwd>
                        <kwd>Mannheim Peritonitis Index (MPI)</kwd>
                    </kwd-group>
                    <counts>
                        <page-count count="6"/>
                    </counts>
                </article-meta>
            </front>
            <body>
                <ref-list>
                    <title>References</title>
                    <ref>
                        <mixed-citation>1. Wittmann DH: Intra abdominal infections: pathophysiology and treatment. New York, Marcel Dekker Publisher; 1991; pp. 8‑75.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>2. Wittmann DH, Walker AP, Condon RE: Peritonitis, intra-abdominal infection, and intra-abdominal abscess. In: Schwartz SI, Shires GT, Spencer FC, (ed.) Principles of surgery. 6th ed. New York McGraw-Hill; 1994; pp. 1449‑84.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>3. Wacha H, Linder MM, Feldmann U et al.: Mannheims peritonitis index - prediction of risk of death from peritonitis. Theoretical Surg 1987; 1: 169‑77.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>4. Billing A, Fröhlich D, Schildberg FW: Prediction of outcome using the Mannheim peritonitis index in 2003 patients. Peritonitis Study Group. Br J Surg 1994; 81: 209‑13. 8‑11.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>5. Sartelli M: A focus on intra-abdominal infections.World J of Emerg Surg 2010; 19: 5‑9.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>6. Malik AA, Wani KA, Dar LA et al.: Mannheim Peritonitis Index and APACHE II - Prediction of outcome in patients with peritonitis. Ulus Travma Acil Cerrahi Derg 2010; 16 (1): 27‑32.
                            <pub-id pub-id-type="pmid">20209392</pub-id>
                        </mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>7. Dandapat MC, Mukherjee LM, Mishra SB et al.: Gastrointestinal perforations. Indian J Surg 1991; 53(5): 189‑93.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>8. Notash AY, Salimi J, Rahimian H et al.: Evaluation of Mannheim peritonitis index and multiple organ failure score in patients with peritonitis.Indian J Gastroenterol 2005; 24: 197‑200.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>9. Correia MM, Thuler LCS, Velasco E et al.: Peritonitis Index in oncologic patients. Revista Brasileira de Cancerologia 2001; 47(1): 63‑68.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>10.Hiyama DT, Bennion RS: Peritonitis and intraperitoneal abcess. In: Zinner MJ, Schwartz SI, Ellis H, (ed.) Maingots Abdominal Operations. Vol1. 10th ed. New York: McGraw Hill; 2001, pp. 633‑53.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>11. Függer R, Rogy M, Herbst F et al.: Validation study of the Mannheim Peritonitis Index. Chirurg 1988; 59: 598‑601.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>12. Weigelt JA: Empiric treatment options in the management of complicated intra-abdominal infections.Cleveland Clinic J Medicine 2007; 74 Suppl 4: 29‑37.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>13. Seiler CA, Brugger L, Forssmann U: Conservative surgical treatment of diffuse peritonitis. Surgery 2000; 127: 178‑184.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>14. Dellinger PE: Surgical infection stratification system for intra-abdominal infection. Arch Surg 1985 Jan; 120: 21.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>15. Demmel N, Muth G, Maag K et al.: Prognostic scores in peritonitis: the Mannheim Peritonitis Index or APACHE II? Langenbecks Archiv für Chirurgie 1994; 379(6): 347‑52.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>16. Rodolfo L, Bracho-Riquelme MC, Bracho-Riquelme M et al.: Mannheim Peritonitis Index validationstudy at thehospitalgeneral de Durango (Mexico).Cir Ciruj 2002; 70: 217‑25.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>17. Basnet RB, Sharma VK: Evaluation of predictive power of MannheimPeritonitis Index.Postgraduate Medical J NAMS. Nr 2, 2010 Jul-Dec; 10: 10‑13.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>18. Wabwire B: Stratified outcome evaluation in peritonitis (dissertation). M Med (Surgery) UoN 2009.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>19. Ntirenganya F, Ntakiyiruta G, Kakande I: Prediction of Outcome Using the Mannheim peritonitis Index in Patients with Peritonitis at Kigali University Teaching Hospital. East and Central African J Surg 2012 Jul-Aug; 17(2).</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>20. Batra P, Gupta D, Batra R et al.: Mannheim Peritonitis Index as an evaluative tool in predicting mortality in patients of perforation peritonitis. CIBTech J Surg ISSN: 2319‑3875.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>21. Chandrashekar N, Prabhakar GN, Gurukiran CS et al.: Study of prognostic factors in perforative peritonitis. J of Evolution Medical and Dental Sciences 2013 Issue 30, July 29; 2: 5568‑74.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>22. Ermolov AS, Bagdat’ev VE, Chudotvortseva EV et al.: Evaluation of the Mannheim Peritonitis Index. Vestn Khir Im I IGrek 1996; 155: 22‑23.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>23. Quereshi AM, Zafar A, Khurram S et al.: Predictive power of Mannheim peritonitis Index. J of the College of Physicians and Surgeons Pakistan 2005; 15(11): 693‑96.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>24. Paduszyńska K, Kaczka K, Dworzyńska A et al.: Evaluating the prognostic value of selected prognostic scales in patients operated on due to peritonitis. Polish J Surg 2014; 86(9): 422‑28.</mixed-citation>
                    </ref>
                    <ref>
                        <mixed-citation>25. Ohmann C, Wittmann DH, Wacha H: the Peritonitis Study Group. Prospective evaluation of prognostic scoring systems in peritonitis. Eur J Surg 1993; 159: 267‑74.</mixed-citation>
                    </ref>
                </ref-list>
            </body>
        </article>
{% endhighlight %}
