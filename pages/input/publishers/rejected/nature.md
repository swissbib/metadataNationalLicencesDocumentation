---
layout: page
title: Nature
---

# Nature

## Description de l'échantillon

* Tout le contenu de [Nature, Vol 526, No 7571, October 2015](http://www.nature.com/nature/journal/v526/n7571/index.html).
* Un [article](http://dx.doi.org/10.1038/nplants.2015.138) de Nature Plants.

## Structure des fichiers

 * Un fichier pour tout le contenu de Nature
 * Un fichier pour l'article de Nature Plants

## Remarques

 * Pubmed DTD 2.5
 * Pour Nature, il y a tout, y compris editorial, les articles de news, ou les research highlights. A exclure peut-être ?

## Remarque de l'éditeur

> If you need more information on metadata, please feel free to contact
Dan Foley,  Web Production Editor,  <mailto:d.foley@nature.com> , who will be glad to assist you with any
queries.

## Exemple

Exemple pour cet [article](http://dx.doi.org/10.1038/nature14962)

{% highlight xml %}
<Article>
    <!-- NPG CATEGORY: ARTICLE -->
    <Journal>
        <PublisherName>Nature Publishing Group, a division of Macmillan Publishers Limited. All Rights Reserved.</PublisherName>
        <JournalTitle>Nature</JournalTitle>
        <Issn>0028-0836</Issn>
        <Volume>526</Volume>
        <Issue>7571</Issue>
        <PubDate PubStatus="ppublish">
            <Year>2015</Year>
            <Month>October</Month>
            <Day>1</Day>
        </PubDate>
    </Journal>
    <Replaces>26367797</Replaces>
    <ArticleTitle>The UK10K project identifies rare variants in health and disease</ArticleTitle>
    <FirstPage>82</FirstPage>
    <LastPage>90</LastPage>
    <ELocationID EIdType="doi">10.1038/nature14962</ELocationID>
    <Language>EN</Language>
    <AuthorList>
        <Author>
            <CollectiveName>The UK10K Consortium</CollectiveName>
        </Author>
        <Author>
            <CollectiveName>Writing group</CollectiveName>
        </Author>
        <Author>
            <CollectiveName>Production group</CollectiveName>
        </Author>
        <Author>
            <CollectiveName>Cohorts group</CollectiveName>
        </Author>
        <Author>
            <CollectiveName>Neurodevelopmental disorders group</CollectiveName>
        </Author>
        <Author>
            <CollectiveName>Obesity group</CollectiveName>
        </Author>
        <Author>
            <CollectiveName>Rare disease group</CollectiveName>
        </Author>
        <Author>
            <CollectiveName>Statistics group</CollectiveName>
        </Author>
        <Author>
            <CollectiveName>Ethics group</CollectiveName>
        </Author>
        <Author>
            <CollectiveName>Incidental findings group</CollectiveName>
        </Author>
        <Author>
            <CollectiveName>Management committee</CollectiveName>
        </Author>
        <Author>
            <CollectiveName>Lipid meta-analysis group</CollectiveName>
        </Author>
        <Author>
            <CollectiveName>The UCLEB Consortium</CollectiveName>
        </Author>
    </AuthorList>
    <GroupList>
        <Group>
            <GroupName>Writing group</GroupName>
            <IndividualName>
                <FirstName>Klaudia</FirstName>
                <LastName>Walter</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Josine L.</FirstName>
                <LastName>Min</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jie</FirstName>
                <LastName>Huang</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Lucy</FirstName>
                <LastName>Crooks</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Yasin</FirstName>
                <LastName>Memari</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Shane</FirstName>
                <LastName>McCarthy</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>John R. B.</FirstName>
                <LastName>Perry</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>ChangJiang</FirstName>
                <LastName>Xu</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Marta</FirstName>
                <LastName>Futema</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Daniel</FirstName>
                <LastName>Lawson</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Valentina</FirstName>
                <LastName>Iotchkova</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Stephan</FirstName>
                <LastName>Schiffels</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Audrey E.</FirstName>
                <LastName>Hendricks</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Petr</FirstName>
                <LastName>Danecek</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Rui</FirstName>
                <LastName>Li</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>James</FirstName>
                <LastName>Floyd</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Louise V.</FirstName>
                <LastName>Wain</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Inês</FirstName>
                <LastName>Barroso</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Steve E.</FirstName>
                <LastName>Humphries</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Matthew E.</FirstName>
                <LastName>Hurles</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Eleftheria</FirstName>
                <LastName>Zeggini</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jeffrey C.</FirstName>
                <LastName>Barrett</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Vincent</FirstName>
                <LastName>Plagnol</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>J.</FirstName>
                <LastName>Brent Richards</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Celia M. T.</FirstName>
                <LastName>Greenwood</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Nicholas J.</FirstName>
                <LastName>Timpson</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Richard</FirstName>
                <LastName>Durbin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Nicole</FirstName>
                <LastName>Soranzo</LastName>
            </IndividualName>
        </Group>
        <Group>
            <GroupName>Production group</GroupName>
            <IndividualName>
                <FirstName>Senduran</FirstName>
                <LastName>Bala</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Peter</FirstName>
                <LastName>Clapham</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Guy</FirstName>
                <LastName>Coates</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Tony</FirstName>
                <LastName>Cox</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Allan</FirstName>
                <LastName>Daly</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Petr</FirstName>
                <LastName>Danecek</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Yuanping</FirstName>
                <LastName>Du</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Richard</FirstName>
                <LastName>Durbin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Sarah</FirstName>
                <LastName>Edkins</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Peter</FirstName>
                <LastName>Ellis</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Paul</FirstName>
                <LastName>Flicek</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Xiaosen</FirstName>
                <LastName>Guo</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Xueqin</FirstName>
                <LastName>Guo</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Liren</FirstName>
                <LastName>Huang</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>David K.</FirstName>
                <LastName>Jackson</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Chris</FirstName>
                <LastName>Joyce</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Thomas</FirstName>
                <LastName>Keane</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Anja</FirstName>
                <LastName>Kolb-Kokocinski</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Cordelia</FirstName>
                <LastName>Langford</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Yingrui</FirstName>
                <LastName>Li</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jieqin</FirstName>
                <LastName>Liang</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Hong</FirstName>
                <LastName>Lin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Ryan</FirstName>
                <LastName>Liu</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>John</FirstName>
                <LastName>Maslen</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Shane</FirstName>
                <LastName>McCarthy</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Dawn</FirstName>
                <LastName>Muddyman</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Michael A.</FirstName>
                <LastName>Quail</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jim</FirstName>
                <LastName>Stalker</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jianping</FirstName>
                <LastName>Sun</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jing</FirstName>
                <LastName>Tian</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Guangbiao</FirstName>
                <LastName>Wang</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jun</FirstName>
                <LastName>Wang</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Yu</FirstName>
                <LastName>Wang</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Kim</FirstName>
                <LastName>Wong</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Pingbo</FirstName>
                <LastName>Zhang</LastName>
            </IndividualName>
        </Group>
        <Group>
            <GroupName>Cohorts group</GroupName>
            <IndividualName>
                <FirstName>Inês</FirstName>
                <LastName>Barroso</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Ewan</FirstName>
                <LastName>Birney</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Chris</FirstName>
                <LastName>Boustred</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Lu</FirstName>
                <LastName>Chen</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Gail</FirstName>
                <LastName>Clement</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Massimiliano</FirstName>
                <LastName>Cocca</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Petr</FirstName>
                <LastName>Danecek</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>George</FirstName>
                <LastName>Davey Smith</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Ian N. M.</FirstName>
                <LastName>Day</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Aaron</FirstName>
                <LastName>Day-Williams</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Thomas</FirstName>
                <LastName>Down</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Ian</FirstName>
                <LastName>Dunham</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Richard</FirstName>
                <LastName>Durbin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>David M.</FirstName>
                <LastName>Evans</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Tom R.</FirstName>
                <LastName>Gaunt</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Matthias</FirstName>
                <LastName>Geihs</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Celia M. T.</FirstName>
                <LastName>Greenwood</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Deborah</FirstName>
                <LastName>Hart</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Audrey E.</FirstName>
                <LastName>Hendricks</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Bryan</FirstName>
                <LastName>Howie</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jie</FirstName>
                <LastName>Huang</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Tim</FirstName>
                <LastName>Hubbard</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Pirro</FirstName>
                <LastName>Hysi</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Valentina</FirstName>
                <LastName>Iotchkova</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Yalda</FirstName>
                <LastName>Jamshidi</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Konrad J.</FirstName>
                <LastName>Karczewski</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>John P.</FirstName>
                <LastName>Kemp</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Genevieve</FirstName>
                <LastName>Lachance</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Daniel</FirstName>
                <LastName>Lawson</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Monkol</FirstName>
                <LastName>Lek</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Margarida</FirstName>
                <LastName>Lopes</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Daniel G.</FirstName>
                <LastName>MacArthur</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jonathan</FirstName>
                <LastName>Marchini</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Massimo</FirstName>
                <LastName>Mangino</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Iain</FirstName>
                <LastName>Mathieson</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Shane</FirstName>
                <LastName>McCarthy</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Yasin</FirstName>
                <LastName>Memari</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Sarah</FirstName>
                <LastName>Metrustry</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Josine L.</FirstName>
                <LastName>Min</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Alireza</FirstName>
                <LastName>Moayyeri</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Dawn</FirstName>
                <LastName>Muddyman</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Kate</FirstName>
                <LastName>Northstone</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Kalliope</FirstName>
                <LastName>Panoutsopoulou</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Lavinia</FirstName>
                <LastName>Paternoster</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>John R. B.</FirstName>
                <LastName>Perry</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Lydia</FirstName>
                <LastName>Quaye</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>J.</FirstName>
                <LastName>Brent Richards</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Susan</FirstName>
                <LastName>Ring</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Graham R. S.</FirstName>
                <LastName>Ritchie</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Stephan</FirstName>
                <LastName>Schiffels</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Hashem A.</FirstName>
                <LastName>Shihab</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>So-Youn</FirstName>
                <LastName>Shin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Kerrin S.</FirstName>
                <LastName>Small</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>María</FirstName>
                <LastName>Soler Artigas</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Nicole</FirstName>
                <LastName>Soranzo</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Lorraine</FirstName>
                <LastName>Southam</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Timothy D.</FirstName>
                <LastName>Spector</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Beate</FirstName>
                <LastName>St Pourcain</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Gabriela</FirstName>
                <LastName>Surdulescu</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Ioanna</FirstName>
                <LastName>Tachmazidou</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Nicholas J.</FirstName>
                <LastName>Timpson</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Martin D.</FirstName>
                <LastName>Tobin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Ana M.</FirstName>
                <LastName>Valdes</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Peter M.</FirstName>
                <LastName>Visscher</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Louise V.</FirstName>
                <LastName>Wain</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Klaudia</FirstName>
                <LastName>Walter</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Kirsten</FirstName>
                <LastName>Ward</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Scott G.</FirstName>
                <LastName>Wilson</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Kim</FirstName>
                <LastName>Wong</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jian</FirstName>
                <LastName>Yang</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Eleftheria</FirstName>
                <LastName>Zeggini</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Feng</FirstName>
                <LastName>Zhang</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Hou-Feng</FirstName>
                <LastName>Zheng</LastName>
            </IndividualName>
        </Group>
        <Group>
            <GroupName>Neurodevelopmental disorders group</GroupName>
            <IndividualName>
                <FirstName>Richard</FirstName>
                <LastName>Anney</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Muhammad</FirstName>
                <LastName>Ayub</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jeffrey C.</FirstName>
                <LastName>Barrett</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Douglas</FirstName>
                <LastName>Blackwood</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Patrick F.</FirstName>
                <LastName>Bolton</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Gerome</FirstName>
                <LastName>Breen</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>David A.</FirstName>
                <LastName>Collier</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Nick</FirstName>
                <LastName>Craddock</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Lucy</FirstName>
                <LastName>Crooks</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Sarah</FirstName>
                <LastName>Curran</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>David</FirstName>
                <LastName>Curtis</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Richard</FirstName>
                <LastName>Durbin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Louise</FirstName>
                <LastName>Gallagher</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Daniel</FirstName>
                <LastName>Geschwind</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Hugh</FirstName>
                <LastName>Gurling</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Peter</FirstName>
                <LastName>Holmans</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Irene</FirstName>
                <LastName>Lee</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jouko</FirstName>
                <LastName>Lönnqvist</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Shane</FirstName>
                <LastName>McCarthy</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Peter</FirstName>
                <LastName>McGuffin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Andrew M.</FirstName>
                <LastName>McIntosh</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Andrew G.</FirstName>
                <LastName>McKechanie</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Andrew</FirstName>
                <LastName>McQuillin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>James</FirstName>
                <LastName>Morris</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Dawn</FirstName>
                <LastName>Muddyman</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Michael C.</FirstName>
                <LastName>O'Donovan</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Michael J.</FirstName>
                <LastName>Owen</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Aarno</FirstName>
                <LastName>Palotie</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jeremy R.</FirstName>
                <LastName>Parr</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Tiina</FirstName>
                <LastName>Paunio</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Olli</FirstName>
                <LastName>Pietilainen</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Karola</FirstName>
                <LastName>Rehnström</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Sally I.</FirstName>
                <LastName>Sharp</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>David</FirstName>
                <LastName>Skuse</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>David</FirstName>
                <LastName>St Clair</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jaana</FirstName>
                <LastName>Suvisaari</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>James T. R.</FirstName>
                <LastName>Walters</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Hywel J.</FirstName>
                <LastName>Williams</LastName>
            </IndividualName>
        </Group>
        <Group>
            <GroupName>Obesity group</GroupName>
            <IndividualName>
                <FirstName>Inês</FirstName>
                <LastName>Barroso</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Elena</FirstName>
                <LastName>Bochukova</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Rebecca</FirstName>
                <LastName>Bounds</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Anna</FirstName>
                <LastName>Dominiczak</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Richard</FirstName>
                <LastName>Durbin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>I. Sadaf</FirstName>
                <LastName>Farooqi</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Audrey E.</FirstName>
                <LastName>Hendricks</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Julia</FirstName>
                <LastName>Keogh</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Gaëlle</FirstName>
                <LastName>Marenne</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Shane</FirstName>
                <LastName>McCarthy</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Andrew</FirstName>
                <LastName>Morris</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Dawn</FirstName>
                <LastName>Muddyman</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Stephen</FirstName>
                <LastName>O'Rahilly</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>David J.</FirstName>
                <LastName>Porteous</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Blair H.</FirstName>
                <LastName>Smith</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Ioanna</FirstName>
                <LastName>Tachmazidou</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Eleanor</FirstName>
                <LastName>Wheeler</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Eleftheria</FirstName>
                <LastName>Zeggini</LastName>
            </IndividualName>
        </Group>
        <Group>
            <GroupName>Rare disease group</GroupName>
            <IndividualName>
                <FirstName>Saeed</FirstName>
                <LastName>Al Turki</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Carl A.</FirstName>
                <LastName>Anderson</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Dinu</FirstName>
                <LastName>Antony</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Inês</FirstName>
                <LastName>Barroso</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Phil</FirstName>
                <LastName>Beales</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jamie</FirstName>
                <LastName>Bentham</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Shoumo</FirstName>
                <LastName>Bhattacharya</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Mattia</FirstName>
                <LastName>Calissano</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Keren</FirstName>
                <LastName>Carss</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Krishna</FirstName>
                <LastName>Chatterjee</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Sebahattin</FirstName>
                <LastName>Cirak</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Catherine</FirstName>
                <LastName>Cosgrove</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Richard</FirstName>
                <LastName>Durbin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>David R.</FirstName>
                <LastName>Fitzpatrick</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>James</FirstName>
                <LastName>Floyd</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>A.</FirstName>
                <LastName>Reghan Foley</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Christopher S.</FirstName>
                <LastName>Franklin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Marta</FirstName>
                <LastName>Futema</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Detelina</FirstName>
                <LastName>Grozeva</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Steve E.</FirstName>
                <LastName>Humphries</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Matthew E.</FirstName>
                <LastName>Hurles</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Shane</FirstName>
                <LastName>McCarthy</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Hannah M.</FirstName>
                <LastName>Mitchison</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Dawn</FirstName>
                <LastName>Muddyman</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Francesco</FirstName>
                <LastName>Muntoni</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Stephen</FirstName>
                <LastName>O'Rahilly</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Alexandros</FirstName>
                <LastName>Onoufriadis</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Victoria</FirstName>
                <LastName>Parker</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Felicity</FirstName>
                <LastName>Payne</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Vincent</FirstName>
                <LastName>Plagnol</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>F.</FirstName>
                <LastName>Lucy Raymond</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Nicola</FirstName>
                <LastName>Roberts</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>David B.</FirstName>
                <LastName>Savage</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Peter</FirstName>
                <LastName>Scambler</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Miriam</FirstName>
                <LastName>Schmidts</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Nadia</FirstName>
                <LastName>Schoenmakers</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Robert K.</FirstName>
                <LastName>Semple</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Eva</FirstName>
                <LastName>Serra</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Olivera</FirstName>
                <LastName>Spasic-Boskovic</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Elizabeth</FirstName>
                <LastName>Stevens</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Margriet</FirstName>
                <LastName>van Kogelenberg</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Parthiban</FirstName>
                <LastName>Vijayarangakannan</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Klaudia</FirstName>
                <LastName>Walter</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Kathleen A.</FirstName>
                <LastName>Williamson</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Crispian</FirstName>
                <LastName>Wilson</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Tamieka</FirstName>
                <LastName>Whyte</LastName>
            </IndividualName>
        </Group>
        <Group>
            <GroupName>Statistics group</GroupName>
            <IndividualName>
                <FirstName>Antonio</FirstName>
                <LastName>Ciampi</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Celia M. T.</FirstName>
                <LastName>Greenwood</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Audrey E.</FirstName>
                <LastName>Hendricks</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Rui</FirstName>
                <LastName>Li</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Sarah</FirstName>
                <LastName>Metrustry</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Karim</FirstName>
                <LastName>Oualkacha</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Ioanna</FirstName>
                <LastName>Tachmazidou</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>ChangJiang</FirstName>
                <LastName>Xu</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Eleftheria</FirstName>
                <LastName>Zeggini</LastName>
            </IndividualName>
        </Group>
        <Group>
            <GroupName>Ethics group</GroupName>
            <IndividualName>
                <FirstName>Martin</FirstName>
                <LastName>Bobrow</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Patrick F.</FirstName>
                <LastName>Bolton</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Richard</FirstName>
                <LastName>Durbin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>David R.</FirstName>
                <LastName>Fitzpatrick</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Heather</FirstName>
                <LastName>Griffin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Matthew E.</FirstName>
                <LastName>Hurles</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jane</FirstName>
                <LastName>Kaye</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Karen</FirstName>
                <LastName>Kennedy</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Alastair</FirstName>
                <LastName>Kent</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Dawn</FirstName>
                <LastName>Muddyman</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Francesco</FirstName>
                <LastName>Muntoni</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>F.</FirstName>
                <LastName>Lucy Raymond</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Robert K.</FirstName>
                <LastName>Semple</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Carol</FirstName>
                <LastName>Smee</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Timothy D.</FirstName>
                <LastName>Spector</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Nicholas J.</FirstName>
                <LastName>Timpson</LastName>
            </IndividualName>
        </Group>
        <Group>
            <GroupName>Incidental findings group</GroupName>
            <IndividualName>
                <FirstName>Ruth</FirstName>
                <LastName>Charlton</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Rosemary</FirstName>
                <LastName>Ekong</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Marta</FirstName>
                <LastName>Futema</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Steve E.</FirstName>
                <LastName>Humphries</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Farrah</FirstName>
                <LastName>Khawaja</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Luis R.</FirstName>
                <LastName>Lopes</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Nicola</FirstName>
                <LastName>Migone</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Stewart J.</FirstName>
                <LastName>Payne</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Vincent</FirstName>
                <LastName>Plagnol</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Rebecca C.</FirstName>
                <LastName>Pollitt</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Sue</FirstName>
                <LastName>Povey</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Cheryl K.</FirstName>
                <LastName>Ridout</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Rachel L.</FirstName>
                <LastName>Robinson</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Richard H.</FirstName>
                <LastName>Scott</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Adam</FirstName>
                <LastName>Shaw</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Petros</FirstName>
                <LastName>Syrris</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Rohan</FirstName>
                <LastName>Taylor</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Anthony M.</FirstName>
                <LastName>Vandersteen</LastName>
            </IndividualName>
        </Group>
        <Group>
            <GroupName>Management committee</GroupName>
            <IndividualName>
                <FirstName>Jeffrey C.</FirstName>
                <LastName>Barrett</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Inês</FirstName>
                <LastName>Barroso</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>George</FirstName>
                <LastName>Davey Smith</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Richard</FirstName>
                <LastName>Durbin</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>I. Sadaf</FirstName>
                <LastName>Farooqi</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>David R.</FirstName>
                <LastName>Fitzpatrick</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Matthew E.</FirstName>
                <LastName>Hurles</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jane</FirstName>
                <LastName>Kaye</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Karen</FirstName>
                <LastName>Kennedy</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Cordelia</FirstName>
                <LastName>Langford</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Shane</FirstName>
                <LastName>McCarthy</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Dawn</FirstName>
                <LastName>Muddyman</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Michael J.</FirstName>
                <LastName>Owen</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Aarno</FirstName>
                <LastName>Palotie</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>J.</FirstName>
                <LastName>Brent Richards</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Nicole</FirstName>
                <LastName>Soranzo</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Timothy D.</FirstName>
                <LastName>Spector</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Jim</FirstName>
                <LastName>Stalker</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Nicholas J.</FirstName>
                <LastName>Timpson</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Eleftheria</FirstName>
                <LastName>Zeggini</LastName>
            </IndividualName>
        </Group>
        <Group>
            <GroupName>The UCLEB Consortium</GroupName>
            <IndividualName>
                <FirstName>Daniela</FirstName>
                <LastName>Toniolo</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Michela</FirstName>
                <LastName>Traglia</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Anne</FirstName>
                <LastName>Tybjaerg-Hansen</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Cornelia M.</FirstName>
                <LastName>van Duijn</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Elisabeth M.</FirstName>
                <LastName>van Leeuwen</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Anette</FirstName>
                <LastName>Varbo</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Peter</FirstName>
                <LastName>Whincup</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Gianluigi</FirstName>
                <LastName>Zaza</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Eleftheria</FirstName>
                <LastName>Zeggini</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Weihua</FirstName>
                <LastName>Zhang</LastName>
            </IndividualName>
        </Group>
        <Group>
            <GroupName>The UCLEB Consortium</GroupName>
            <IndividualName>
                <FirstName>Daniela</FirstName>
                <LastName>Toniolo</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Michela</FirstName>
                <LastName>Traglia</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Anne</FirstName>
                <LastName>Tybjaerg-Hansen</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Cornelia M.</FirstName>
                <LastName>van Duijn</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Elisabeth M.</FirstName>
                <LastName>van Leeuwen</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Anette</FirstName>
                <LastName>Varbo</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Peter</FirstName>
                <LastName>Whincup</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Gianluigi</FirstName>
                <LastName>Zaza</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Eleftheria</FirstName>
                <LastName>Zeggini</LastName>
            </IndividualName>
            <IndividualName>
                <FirstName>Weihua</FirstName>
                <LastName>Zhang</LastName>
            </IndividualName>
        </Group>
    </GroupList>
    <ArticleIdList>
        <ArticleId IdType="pii">nature14962</ArticleId>
        <ArticleId IdType="doi">10.1038/nature14962</ArticleId>
    </ArticleIdList>
    <History>
        <PubDate PubStatus="received">
            <Year>2015</Year>
            <Month>03</Month>
            <Day>15</Day>
        </PubDate>
        <PubDate PubStatus="accepted">
            <Year>2015</Year>
            <Month>07</Month>
            <Day>17</Day>
        </PubDate>
        <PubDate PubStatus="aheadofprint">
            <Year>2015</Year>
            <Month>September</Month>
            <Day>14</Day>
        </PubDate>
    </History>
    <Abstract>The contribution of rare and low-frequency variants to human traits is largely unexplored. Here we describe insights from sequencing whole genomes (low read depth, 7×) or exomes (high read depth, 80×) of nearly 10,000 individuals from population-based and disease collections. In extensively phenotyped cohorts we characterize over 24 million novel sequence variants, generate a highly accurate imputation reference panel and identify novel alleles associated with levels of triglycerides (APOB), adiponectin (ADIPOQ) and low-density lipoprotein cholesterol (LDLR and RGAG1) from single-marker and rare variant aggregation tests. We describe population structure and functional annotation of rare and low-frequency variants, use the data to estimate the benefits of sequencing for association studies, and summarize lessons from disease-specific collections. Finally, we make available an extensive resource, including individual-level genetic and phenotypic data and web-based tools to facilitate the exploration of association results.</Abstract>
</Article>
{% endhighlight %}
