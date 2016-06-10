---
layout: page
title: Annual_reviews
---

# Annual Reviews

## Description de l'échantillon

* Les 26 articles du [volume 18 de Annual Review of Political Science](http://www.annualreviews.org/toc/polisci/18/1)
* Les 12 articles du [volume 7 de Annual Review of Biomedical Engineering](http://www.annualreviews.org/toc/bioeng/7/1)

## Structure des fichiers

Tous les articles du volume sont dans le même fichier, à la suite.

## Remarques

 * Cela utilise PubMed DTD <http://www.ncbi.nlm.nih.gov:80/entrez/query/static/PubMed.dtd>
 * Problème pour ouvrir un des fichiers

## Exemple

Exemple pour cet article <http://dx.doi.org/10.1146/annurev-polisci-053013-041156>

{% highlight xml %}
<Article>
    <Journal>
        <PublisherName>Annual Reviews</PublisherName>
        <JournalTitle>Annual Review of Political Science</JournalTitle>
        <Issn>1094-2939</Issn>
        <Volume>18</Volume>
        <PubDate>
            <Year>2015</Year>
            <Month>5</Month>
            <Day>11</Day>
        </PubDate>
    </Journal>
    <ArticleTitle>Should We Leave Behind the Subfield of International Relations?</ArticleTitle>
    <FirstPage>481</FirstPage>
    <LastPage>499</LastPage>
    <AuthorList>
        <Author>
            <FirstName>Dan</FirstName>
            <LastName>Reiter</LastName>
            <Affiliation>Department of Political Science, Emory University, Atlanta, Georgia 30322; email:  dreiter@emory.edu </Affiliation>
        </Author>
    </AuthorList>
    <ArticleIdList>
        <ArticleId IdType="doi">10.1146/annurev-polisci-053013-041156</ArticleId>
    </ArticleIdList>
    <History>
        <PubDate PubStatus="aheadofprint">
            <Year>2014</Year>
            <Month>12</Month>
            <Day>17</Day>
        </PubDate>
    </History>
    <Abstract> This article considers whether political science should abandon the subfields of American politics, comparative politics, and international relations (IR), for new subfields of conflict, political economy, institutions, and behavior. The focus here is whether the field should abandon IR. The article lays out the arguments in favor of abandoning IR, describing scholarly trends that cross conventional subfield lines and are pushing to dissolve IR. Next, it argues that the costs of abandoning IR exceed the benefits, as new subfield divisions would remove some artificial walls but create new ones. Abandoning IR might undermine objective theory testing, would disadvantage the study of international system and structure, and would undermine the ability of political science to inform foreign policy debates. The article concludes by recommending that the field keep IR and its current subfield boundaries but that the walls between subfields should be kept low and porous. </Abstract>
    <ObjectList>
        <Object Type="keyword">
            <Param Name="value">international relations</Param>
        </Object>
        <Object Type="keyword">
            <Param Name="value">subfields</Param>
        </Object>
    </ObjectList>
</Article>
{% endhighlight %}
