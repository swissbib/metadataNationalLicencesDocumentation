---
layout: page
title: Pubmed (Central)
---

# Pubmed Central

Pubmed Central a une interface OAI qui permet d'harvester des métadonnées au format JATS Journal Interchange :  <http://www.ncbi.nlm.nih.gov/pmc/oai/oai.cgi?verb=ListRecords&from=2001-03-22&until=2001-06-12&set=bmcbioc&metadataPrefix=pmc>

Voir la [Documentation](http://www.ncbi.nlm.nih.gov/pmc/tools/oai/). On pourrait éventuellement utiliser ceci pour enrichir les métadonnées si il y a overlap ?

## Harvesting du 13 décembre

Pour avoir un jeu de données test, un harvesting OAI-PMH a été effectué le 13 décembre via le ContentCollector. Quelques infos :

 * temps de harvesting : 13 heures
 * nombre d'articles : 329'600
 * from: 2010-12-09
 * metadataPrefix: pmc_fm
 * taille du fichier xml.gz : 330.8 Mo
 * taille du fichier xml : 2.2 Go
 * nombre de lignes : 42'346'253


# Pubmed

## Source

Il y a des exemples de métadonnées disponibles ici : <ftp://ftp.nlm.nih.gov/nlmdata/sample/medline/>. C'est des jeux de 30'000 notices qui peuvent être utiles pour des tests. Ils utilisent Medline Citation DTD :

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE MedlineCitationSet PUBLIC "-//NLM//DTD Medline Citation, 1st January, 2015//EN"
                                    "http://www.nlm.nih.gov/databases/dtd/nlmmedlinecitationset_150101.dtd">
<MedlineCitationSet>
    <MedlineCitation Owner="NLM" Status="MEDLINE">
        <PMID Version="1">10697468</PMID>
        <DateCreated>
            <Year>2000</Year>
            <Month>03</Month>
            <Day>06</Day>
        </DateCreated>
        <DateCompleted>
            <Year>2000</Year>
            <Month>03</Month>
            <Day>06</Day>
        </DateCompleted>
        <DateRevised>
            <Year>2013</Year>
            <Month>11</Month>
            <Day>21</Day>
        </DateRevised>
        <Article PubModel="Print">
            <Journal>
                <ISSN IssnType="Print">0099-2399</ISSN>
                <JournalIssue CitedMedium="Print">
                    <Volume>1</Volume>
                    <Issue>6</Issue>
                    <PubDate>
                        <Year>1975</Year>
                        <Month>Jun</Month>
                    </PubDate>
                </JournalIssue>
                <Title>Journal of endodontics</Title>
                <ISOAbbreviation>J Endod</ISOAbbreviation>
            </Journal>
            <ArticleTitle>Methodology and criteria in the evaluation of dental implants.</ArticleTitle>
            <Pagination>
                <MedlinePgn>193-202</MedlinePgn>
            </Pagination>
            <Abstract>
                <AbstractText>This study was designed to develop an inexpensive, reproducible method for studying the reaction of the tissues of the oral cavity to the endosseous implant. Thirty-six guinea pigs, three materials (Teflon, Vitallium, and Titanium 6Al-4V), two observation periods (two and 12 weeks), and two implant designs (one with exposure to the oral cavity and one without exposure to the oral cavity) were used. The inflammatory response was significantly greater in the exposed implants than in the unexposed implants. In the implants that were exposed 12 weeks, there was a strong interrelationship between severe inflammation, bacteria, and epithelial invagination. These factors are significant causes for failures of implants.</AbstractText>
            </Abstract>
            <AuthorList CompleteYN="Y">
                <Author ValidYN="Y">
                    <LastName>Neuman</LastName>
                    <ForeName>G</ForeName>
                    <Initials>G</Initials>
                    <AffiliationInfo>
                        <Affiliation>CAMM Research Institute, Wayne, NJ, USA.</Affiliation>
                    </AffiliationInfo>
                </Author>
                <Author ValidYN="Y">
                    <LastName>Spangberg</LastName>
                    <ForeName>L</ForeName>
                    <Initials>L</Initials>
                </Author>
                <Author ValidYN="Y">
                    <LastName>Langeland</LastName>
                    <ForeName>K</ForeName>
                    <Initials>K</Initials>
                </Author>
            </AuthorList>
            <Language>eng</Language>
            <PublicationTypeList>
                <PublicationType UI="D003160">Comparative Study</PublicationType>
                <PublicationType UI="D016428">Journal Article</PublicationType>
                <PublicationType UI="D013485">Research Support, Non-U.S. Gov't</PublicationType>
                <PublicationType UI="D013486">Research Support, U.S. Gov't, Non-P.H.S.</PublicationType>
            </PublicationTypeList>
        </Article>
        <MedlineJournalInfo>
            <Country>UNITED STATES</Country>
            <MedlineTA>J Endod</MedlineTA>
            <NlmUniqueID>7511484</NlmUniqueID>
            <ISSNLinking>0099-2399</ISSNLinking>
        </MedlineJournalInfo>
        <ChemicalList>
            <Chemical>
                <RegistryNumber>0</RegistryNumber>
                <NameOfSubstance UI="D015921">Dental Implants</NameOfSubstance>
            </Chemical>
            <Chemical>
                <RegistryNumber>12629-02-6</RegistryNumber>
                <NameOfSubstance UI="D014800">Vitallium</NameOfSubstance>
            </Chemical>
            <Chemical>
                <RegistryNumber>12743-70-3</RegistryNumber>
                <NameOfSubstance UI="C031462">titanium alloy (TiAl6V4)</NameOfSubstance>
            </Chemical>
            <Chemical>
                <RegistryNumber>9002-84-0</RegistryNumber>
                <NameOfSubstance UI="D011138">Polytetrafluoroethylene</NameOfSubstance>
            </Chemical>
            <Chemical>
                <RegistryNumber>D1JT611TNE</RegistryNumber>
                <NameOfSubstance UI="D014025">Titanium</NameOfSubstance>
            </Chemical>
        </ChemicalList>
        <CitationSubset>D</CitationSubset>
        <MeshHeadingList>
            <MeshHeading>
                <DescriptorName MajorTopicYN="N" UI="D000818">Animals</DescriptorName>
            </MeshHeading>
            <MeshHeading>
                <DescriptorName MajorTopicYN="N" UI="D003758">Dental Implantation, Endosseous</DescriptorName>
                <QualifierName MajorTopicYN="N" UI="Q000009">adverse effects</QualifierName>
                <QualifierName MajorTopicYN="Y" UI="Q000379">methods</QualifierName>
            </MeshHeading>
            <MeshHeading>
                <DescriptorName MajorTopicYN="Y" UI="D015921">Dental Implants</DescriptorName>
                <QualifierName MajorTopicYN="N" UI="Q000592">standards</QualifierName>
            </MeshHeading>
            <MeshHeading>
                <DescriptorName MajorTopicYN="N" UI="D019232">Dental Restoration Failure</DescriptorName>
            </MeshHeading>
            <MeshHeading>
                <DescriptorName MajorTopicYN="N" UI="D006168">Guinea Pigs</DescriptorName>
            </MeshHeading>
            <MeshHeading>
                <DescriptorName MajorTopicYN="N" UI="D008297">Male</DescriptorName>
            </MeshHeading>
            <MeshHeading>
                <DescriptorName MajorTopicYN="N" UI="D010043">Outcome and Process Assessment (Health Care)</DescriptorName>
            </MeshHeading>
            <MeshHeading>
                <DescriptorName MajorTopicYN="N" UI="D010518">Periodontitis</DescriptorName>
                <QualifierName MajorTopicYN="N" UI="Q000209">etiology</QualifierName>
            </MeshHeading>
            <MeshHeading>
                <DescriptorName MajorTopicYN="N" UI="D010519">Periodontium</DescriptorName>
                <QualifierName MajorTopicYN="N" UI="Q000473">pathology</QualifierName>
            </MeshHeading>
            <MeshHeading>
                <DescriptorName MajorTopicYN="N" UI="D011138">Polytetrafluoroethylene</DescriptorName>
            </MeshHeading>
            <MeshHeading>
                <DescriptorName MajorTopicYN="N" UI="D013997">Time Factors</DescriptorName>
            </MeshHeading>
            <MeshHeading>
                <DescriptorName MajorTopicYN="N" UI="D014025">Titanium</DescriptorName>
            </MeshHeading>
            <MeshHeading>
                <DescriptorName MajorTopicYN="N" UI="D014800">Vitallium</DescriptorName>
            </MeshHeading>
        </MeshHeadingList>
    </MedlineCitation>
{% endhighlight %}
