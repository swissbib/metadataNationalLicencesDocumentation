---
layout: page
title: Springer
---

# Springer

## Description de l'échantillon

Tous les articles du [volume 21 du journal Abdominal Imaging](http://link.springer.com/journal/261/21/1/page/1) : 128 articles.

## Structure des fichiers

Un fichier XML par article avec une structure par dossiers journal/volume/issue/, par exemple


```
JOU=00261/VOL=1996.21/ISU=5/ART=1232/261_2009_Article_1232.xml.Meta
```




## Remarques

En-tête xml

```
<!-- Converted from Majour with majour2a++ V1.10 -->
<!--Automatically converted from version 2.3 to 2.4-->
<!DOCTYPE Publisher PUBLIC "-//Springer-Verlag//DTD A++ V2.4//EN" "http://devel.springer.de/A++/V2.4/DTD/A++V2.4.dtd">
```

 * Il y a des DTD ici <http://devel.springer.de/A++/V2.4/DTD/>. Complètement maison.
 * le tout est dans une balise <publisher>
 * d'après Robin le 3.2.2016, ont accepté une licence CC0


Réponse de Springer pour la licence CC0 :

> Der Lizenznehmer oder ein von ihm beauftragter Dritter ist berechtigt, die Metadaten in jeder Weise zu nutzen, die geeignet ist, die Nutzung des lizenzierten Produkts bzw. der darin enthaltenen einzelnen Informationsobjekte durch autorisierte Nutzer zu ermöglichen, zu befördern, zu erleichtern und zu unterstützen. Insbesondere können zu diesem Zweck die Metadaten indexiert werden und ggf. mit Verknüpfungen, die einen direkten Zugang autorisierter Nutzer zum lizenzierten Produkt bzw. den darin enthaltenen einzelnen Informationsobjekten ermöglichen, in lokale Katalogsysteme, regionale oder überregionale Verbundkatalogsysteme, sowie andere Bibliotheksdienste und Informationssysteme Dritter (einschließlich, aber nicht beschränkt auf Suchmaschinen) eingebunden und mit diesen Systemen ohne Einschränkung als Linked Open Data freigestellt werden. Das Recht, die Metadaten in dieser Weise zu nutzen, steht allen autorisierten Einrichtungen zu.


## Réception des fichiers le 15 janvier 2016

 * Par FTP (server `ftp.springer-dds.com` user and pass in swissbib password safe)
 * 38 fichiers zip totalisant 12.1 Go
 * Il y a chaque jour une update entre 5h et 7h du matin avec les nouveaux articles ainsi que les corrections d'anciens articles. Un email est envoyé à `lionel.walter@unibas.ch` pour confirmer cette livraison. A priori les updates font entre 100 Ko et 20 Mo.
 * 21 fichiers commençant par `ftp_PUB_15-12-18` contiennent directement les métadonnées
 * les fichiers commençant par `ftp_PUB_15-12-23` ainsi que les dates postérieures contiennent à leur tour 1 ou 2 fichiers zip qui contiennent les métadonnées. Il faut donc dezipper deux fois.
 * il y a de la doc ici <http://production-customer.springer.com/A++Documentation/html/A++.html>. Login and pass in swissbib password safe.
   * Aussi possible d'accéder à des [release notes sur la DTD](http://production-customer.springer.com/Section_APlusPlus.html)
 * on peut aussi accéder au ftp en ligne : <ftp://userXXX:passwordYYY@ftp.springer-dds.com/data/in>
 * contact technique <DDS_Support@springer.com>
 * Tout dézipper prend une dizaine d'heures !
 * Il y a 2721 répertoires qui correspondent a priori chacun à un périodique. Ils ont la forme `JOU=13317`
 * Un des journaux les plus longs et les plus complet est *Virchows Archiv* qui est dans le répertoire `JOU=00428`
 * **Bizarre** : dans le répertoire `JOU=00428` cela va que jusque 1996
 * Il y a aussi des articles dont le doi ne renvoie pas sur springerlink mais sur d'autres plateformes comme <http://dx.doi.org/10.12942/lrsp-2004-2> (journal no 41116). Mais on retrouve ce document sur springerlink <http://link.springer.com/article/10.12942/lrsp-2004-2>
 * pas traces des couvertures de périodiques, alors qu'elles sont sur springerlink
 * il semble que des périodiques ne sont pas inclus <http://link.springer.com/article/10.1007/PL00021468>, le no 799, mais peut-être est-ce une erreur de l'unzippage ?
 * il y a des espaces superflus dans certaines balises `<JournalTitle>Applied Nanoscience                    </JournalTitle>` et aussi `<JournalPrintISSN>0009-4722 </JournalPrintISSN>`
 * le champ `<JournalID>190</JournalID>` est peut-être le moyen le plus sûr de regrouper des articles d'un même périodique. Il semblerait que springer passe par là. Il pourrait
 * il y a différentes graphies d'un titre
  - Bulletin Gæodésique
  - Bulletin géodésique
  - Bulletin Géodésique (1946-1975)
 * 2926 ISSN distincts
 * il ne semble pas y avoir de soucis d'encodings : Øst-økonomi
 * ily a des champs vides `<JournalSubTitle/>` ainsi que plein d'autres
 * Quand tout est dézippé, il y a **9'601'836** fichiers et répertoires pour un total de 50.3 Go. Le plus gros dossier `JOU=40285` contient 170'736 fichiers et répertoires pour un total de 641 Mo.
 * Bizarre : `JOU=00138` a des sous-dossiers de 1988 à 1996 puis 2016 ! Aussi `JOU=00205` va jusque 1996, puis 2016.
 * Le travail avec 4,5 million de fichiers n'est vraiment pas pratique. De plus, metafacture ne peut pas travailler rapidement avec les DTD qui ont une url actuellement. Décision, faire un seul fichier xml par journal et enlever les déclarations DOCTYPE. C'est possible car pour springer cette déclaration est uniforme sur tout le contenu. Ce processus a pris environ 6 heures. On a maintenant 2721 fichiers xml d'une taille allant de 6.5 Ko à 425.8 Mo.
 * Dans la liste des titres, il n'y a que les périodiques qui ont commencé avant 1997, mais pas un périodique qui aurait commencé à paraître en 2002 par exemple. Est-il inclus ?
 * L'année la plus complète et la plus fiable est `Journal.Volume.Issue.IssueInfo.IssueHistory.CoverDate.Year.value`
 * Il y a tout de même 12'830 champs différents qui sont utilisés
 * il y a seulement 60 documents qui n'ont ni eISSN ni pISSN. Mais pour 3% des documents, il manque soit l'un soit l'autre
 * 5'228'545 articles
 * 2802 périodiques dont 1704 qui ont commencé <=2004. Dans la liste Springer, il y a seulement 1026 périodiques
 * il y a 4796 qui ne passent pas encore à cause des espaces dans les champs années (corriger l'analyzer trimmer)


## Administration

 * the account lionel.walter@unibas.ch can manage swiss edu-id access on springer platform.


## Contact pour la technique

**Mrs. Attilia Czikmantori**  
Business Support Officer  
Process and Content Management  
Springer Nature  
236 Gray´s Inn Road, London WC1X 8HB, UK  
T  : +44 (0)20 3192 2150  
Attilia.Czikmantori@biomedcentral.com
<Attilia.Czikmantori@springer.com>  
<http://www.springernature.com>  

*Réponses très rapides !*


## Exemple

Exemple pour cet article <http://dx.doi.org/10.1007/s002619900002>


{% highlight xml %}
<Publisher>
    <PublisherInfo>
        <PublisherName>Springer-Verlag</PublisherName>
        <PublisherLocation>Berlin/Heidelberg</PublisherLocation>
    </PublisherInfo>
    <Journal>
        <JournalInfo JournalProductType="Legacy" NumberingStyle="Unnumbered">
            <JournalID>261</JournalID>
            <JournalPrintISSN>0942-8925</JournalPrintISSN>
            <JournalElectronicISSN>1432-0509</JournalElectronicISSN>
            <JournalSPIN/>
            <JournalTitle>Abdominal Imaging</JournalTitle>
            <JournalSubTitle/>
            <JournalAbbreviatedTitle>Abdom Imaging</JournalAbbreviatedTitle>
            <JournalSubjectGroup>
                <JournalSubject Type="Primary">Legacy</JournalSubject>
            </JournalSubjectGroup>
        </JournalInfo>
        <Volume>
            <VolumeInfo VolumeType="Regular">
                <VolumeIDStart>21</VolumeIDStart>
                <VolumeIDEnd>21</VolumeIDEnd>
                <VolumeIssueCount/>
            </VolumeInfo>
            <Issue IssueType="Regular">
                <IssueInfo TocLevels="0">
                    <IssueIDStart>1</IssueIDStart>
                    <IssueIDEnd>1</IssueIDEnd>
                    <IssueHistory>
                        <PrintDate>
                            <Year>1996</Year>
                            <Month>11</Month>
                            <Day/>
                        </PrintDate>
                        <CoverDate>
                            <Year>1996</Year>
                            <Month>11</Month>
                        </CoverDate>
                    </IssueHistory>
                    <IssueCopyright>
                        <CopyrightHolderName>Springer-Verlag New York Inc.</CopyrightHolderName>
                        <CopyrightYear>1996</CopyrightYear>
                    </IssueCopyright>
                </IssueInfo>
                <Article ID="Art1">
                    <ArticleInfo ArticleType="OriginalPaper" ContainsESM="No" Language="En" NumberingStyle="Unnumbered" TocLevels="0">
                        <ArticleID>0005</ArticleID>
                        <ArticleDOI>10.1007/s002619900002</ArticleDOI>
                        <ArticleTitle Language="En">Ultrasonography of the gastrointestinal tract in infants and children</ArticleTitle>
                        <ArticleCategory/>
                        <ArticleFirstPage>9</ArticleFirstPage>
                        <ArticleLastPage>20</ArticleLastPage>
                        <ArticleCopyright>
                            <CopyrightHolderName>Springer-Verlag New York Inc.</CopyrightHolderName>
                            <CopyrightYear>1996</CopyrightYear>
                        </ArticleCopyright>
                        <ArticleGrants>
                            <MetadataGrant Grant="OpenAccess"/>
                            <AbstractGrant Grant="OpenAccess"/>
                            <BodyPDFGrant Grant="Restricted"/>
                            <BodyHTMLGrant Grant="Restricted"/>
                            <BibliographyGrant Grant="Restricted"/>
                            <ESMGrant Grant="Restricted"/>
                        </ArticleGrants>
                    </ArticleInfo>
                    <ArticleHeader>
                        <AuthorGroup>
                            <Author AffiliationIDS="A1">
                                <AuthorName DisplayOrder="Western">
                                    <GivenName>C. K. </GivenName>
                                    <FamilyName>Hayden Jr.</FamilyName>
                                </AuthorName>
                            </Author>
                            <Affiliation ID="A1">
                                <OrgName>Department of Special Imaging, Cook&lt;+&gt;–&lt;+&gt;Fort Worth Children's Medical Center, 801 Seventh Avenue, Fort Worth, TX 76104, USA</OrgName>
                                <OrgAddress>
                                    <Street/>
                                    <Postbox/>
                                    <Postcode/>
                                    <City/>
                                    <State/>
                                </OrgAddress>
                            </Affiliation>
                        </AuthorGroup>
                        <ArticleNote Type="Misc">
                            <SimplePara>Received: 0/0/00/Accepted: 0/0/00</SimplePara>
                        </ArticleNote>
                    </ArticleHeader>
                    <NoBody/>
                </Article>
            </Issue>
        </Volume>
    </Journal>
</Publisher>
{% endhighlight %}
