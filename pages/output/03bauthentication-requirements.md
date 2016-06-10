---
layout: page
title: Authentication requirements
---

# Requirements for the authentication of private persons for Swiss National Licences

## Context

For the Swiss National Licences, private users are allowed to access the content, if they live in Switzerland. Interested persons will need to [create a Swiss Edu-Id](https://eduid.ch/web/registration/1/) account and fulfill some special conditions. Goal of the present document is to detail these requirements to prepare the meeting of March 21st 2016.

Only 3 publishers are still in the race for a contract. It is very probable that a contract will be signed with these 3 publishers, but there are still some steps to be taken (steering comitee, ...)

Publisher|url of the platform|url for authentication|support of eduPersonEntitlement|number of articles|switch federation registered
---|---|---|--|--:|--|
Cambridge University Press|[platform](http://journals.cambridge.org)|[registration](https://shibboleth.cambridge.org/discovery/WAYF?entityID=https%3A%2F%2Fshibboleth.cambridge.org%2Fshibboleth-sp&return=https%3A%2F%2Fshibboleth.cambridge.org%2FShibboleth.sso%2Fdiscovery%3FSAMLDS%3D1%26target%3Dcookie%253A1cdd095d)|31.5.2016|1'132'000|yes|
De Gruyter|[platform](http://www.degruyter.com/)|[registration](https://www.degruyter.com/applib/openathens)|ok|473'000|yes|
Oxford University Press|[platform](http://oxfordjournals.org/en/)|[registration](http://ae.oxfordjournals.org/login/shibboleth?subcode=oupjournals&env=prod&uri=http%3A%2F%2Fae.oxfordjournals.org%2F)|30.9.2016|621'000|no|

### Estimated Number of Users

Germany has 8000 active users. As Switzerland has 10 times less inhabitants, we come to an estimate of **800 private users**.

Another interesting number is the number of users of [ETH e-lending platform](https://www.library.ethz.ch/en/About-us/Projects/E-Lending) : **1650 users** in 2015.

These two figures give a rough estimate.

Estimated number of logins per day : ???

## Meeting of March 21st 2016

Questions to answer :

 * who develops the requirements below
 * who will support the processes below on the long term
 * who pays for it
 * what are the roles of Switch, Swissbib and the Consortium


### Cost estimates

 * development : ???
 * price to send a letter (automatically) : 1.60 CHF
 * price to send an SMS : 0.10 CHF
 * long-term support : ???

## Requirements

### 1. Support of common-lib-terms on Swiss edu-id side

Every Swiss edu-id user who requested to access the National Licences contents and satisfies the conditions must get the value `urn:mace:dir:entitlement:common-lib-terms` for the attribute `eduPersonEntitlement`


### 2. Accept the conditions of use

Every user who wants to access the National Licences contents must accept the terms of use (don't resell the pdf's, don't do massive downloads, live in Switzerland...). This process should happen only once, when the user applies to get access to the National Licences contents.

### 3. Check residency per letter (via Post)

Every user that wants to access the National Licences contents must give a verified post address in Switzerland. A letter will be sent to this address with a code in it to verify the addresss.

*Open question* : what do we do with an address such as "Heinz Muster, Novartis Campus, 4056 Basel" ? Should we take some special care with the addresses ?


### 4. SMS (48 hours)

Additionnally, it is possible to get a temporary access for 48 hours if the user gives a verified swiss mobile phone number. This temporary access can only be granted once.

*Open question* : is that a separate SMS or the same as the SMS that verifies that the number is valid ? There are 2 use cases :

 1. a person registers for a swiss edu id account for other reasons and gives a swiss mobile phone number. Some months later, she wants to access national licences contents. She should be able to get an SMS at that point of time
 2. a person wants to access swiss national licences contents. She registers for a swiss edu id account with a swiss mobile phone. She gets an SMS to verify the number. Then she registers for swiss national licence and get a second SMS. Is that too complicated ?

*Open question* : is 48 hours enough to get the letter (from [pingen.com](http://pingen.com) : submission should be before 12h Mo-Fr). Requesting on Friday afternoon will get the letter on Tuesday (90 hours). Is that a problem ?

### 5. Block user after publisher reports misuse

If the publisher gives us a SAML persistent id `eduPersonTargetedID`, an IP address and the date/time of the misuses, we should be able to block this account (i.e. remove the value `urn:mace:dir:entitlement:common-lib-terms` from this account). With the experience from the swiss universities and the estimated small number of private users, this should happen at most once or twice a year.


### 6. Remove inactive account

This process isn't detailed in the contracts, we suggest to do the same as in the german project.

If a person (with `urn:mace:dir:entitlement:common-lib-terms`) doesn't use its account at all for the last 12 months :

 1. send this person an email with a link to maintain the account active for the next 12 months. If the link is clicked, then the account remains active and nothing else is done.
 2. if the person doesn't click the link during (overn the next 4 weeks for example), remove the value `urn:mace:dir:entitlement:common-lib-terms`. The person needs to start the process again (letter, sms).



### 7. Reporting

Oxford requested some reporting. Reporting is also useful for the consortium and swissbib. I suggest something like this :

At a given time (like once or twice a year) :

 * Number of active private users (users who have the attribute value `urn:mace:dir:entitlement:common-lib-terms`)
 * Total number of swiss-edu-id accounts
 * In the last 12 months : number of persons who requested access to national licence but didn't complete the process
 * In the last 12 months : number of persons who requested access to national licence and did complete the process (the new active private users)
 * In the last 12 months : number of successful login to publisher platforms by private users (split by platform)
 * In the last 12 months : number of persons whose account was disabled





## Other tasks

Some non-development tasks are to be done as well :

 1. write the terms of use
 2. write the content of the letter (and sms).
 3. specify the wording in the user interface
 4. ???


## Flow-chart

Small diagram (requested by Oxford University Press)

![Flow-chart]({{ site.github.url }}/public/images/flow_chart.png)


## Excerpts from Contract Drafts (state 26.2.2016)

### Cambridge

**Authorised Users** means as well scientifically interested private individuals (to the requirement of permanent residence in Switzerland) that have completed a suitable registration procedure.

**Secure Authentication** methods shall include SAML2/Shibboleth (with up to 100 IdPs in the
future), Internet Protocol (IP) ranges as well as authentication with username and
password or other methods that are to be agreed upon in writing between the Publisher,
the Licensee and the Institutions. The use of proxy servers is permitted as long as any
proxy server IP addresses provided limit remote or off-campus access to Authorised
Users. Private individuals will authenticate on an Identity Provider registered in the
SWITCHaai federation (using SAML2/Shibboleth).
The Licensor will enhance its existing Shibboleth-based authentication service in order to
support the use of the SAML attribute eduPersonEntitlement with the value
'urn:mace:dir:entitlement:common-lib-terms' as defined here:
http://middleware.internet2.edu/urn-mace/urn-mace-dir-entitlement.html . The enhancement will
be completed by 31 May 2016.

**Registration process for private individuals**. SWITCH, a service provider of the Licensee is responsible for the registration process of private individuals. SWITCH will verify that a private individual has an address in Switzerland either via postal mail or via SMS on a Swiss mobile number.

### De Gruyter

**Authorized Users** means as well scientifically
interested private individuals (to the requirement of
permanent residence in Switzerland) that have
completed a suitable registration procedure. This
procedure shall guarantee a reliable limitation to
authorized users only.

De Gruyter supports **authentication** via Internet Protocol (IP) -Range, Referrer URL and per Username and Password, even though for institutions this is an exception.
De Gruyter support authentication via Shibboleth (SAML1 & SAML2) with up to 100 IdPs in the future as well as the use of WAYFless URLs.
Other methods are agreed upon in writing between De Gruyter and the Licensee.

The use of proxy servers is permitted as long as any proxy server IP addresses provided limit remote or off-campus access to Authorised Users.

Private individuals will authenticate on an Identity Provider registered in the SWITCHaai federation (using SAML2/Shibboleth).
The Publisher supports access control based on the SAML attribute eduPersonEntitlement with the value 'urn:mace:dir:entitlement:common-lib-terms' as defined here: http://middleware.internet2.edu/urn-mace/urn-mace-dir-entitlement.html.

SWITCH, a service provider of the Licensee is responsible for the registration process of private individuals. SWITCH will verify that a private individual has an address in Switzerland  either via postal mail or via sms on a swiss mobile number. To avoid improper use, the registration via swiss mobile number is valid **one time only and expires after 48 hours**.

### Oxford

**Authorised Users** means as well scientifically interested private individuals provided that

 1. the individual is permanently resident in Switzerland;
 2.  the individual is requesting access on their own behalf to satisfy their
own private personal interest only and not in connection with
their employment or engagement by any other entity;
 3.  any usage rights granted to these individuals are limited to use for
non-commercial research purposes for private study, and
 4.  a suitable registration process as agreed with the Licensor has been
set up by the Consortium, which shall include giving effect to
these criteria;

**Commercial Use** shall mean use for the purposes of monetary reward (whether by or for
21/29the Licensee, an Authorised User, or any other person or entity) by means
of sale, resale, loan, transfer, hire, or other form of exploitation of the
Licensed Works. For the avoidance of doubt, **use by an Institution or
Authorised User of the Licensed Material in the course of research,
funded by a Commercial Organisation is not deemed to constitute
Commercial Use**. Recovery of costs is not deemed as Commercial Use;

**Secure Authentication** methods shall include SAML2/Shibboleth (including access control based on the SAML attribute eduPersonEntitlement with the value 'urn:mace:dir:entitlement:common-lib-terms' as defined here: http://middleware.internet2.edu/urn-mace/urn-mace-dir-entitlement.html) (**available Q3 2016**) (with up to 100IdPs in the future), Internet Protocol (IP) ranges as well as authentication with username and password or other methods that are to be agreed upon in writing between the Licensor, the Consortium Agent and the Licensees. The use of proxy servers is permitted as long as any proxy server IP addresses provided limit remote or off-campus access to Authorised Users.

Upon request by the Licensor, **the Licensee shall produce reports** detailing the extent of use of the Licensed Works under the access granted to scientifically-interested private individuals who are permanently resident in Switzerland. Such reporting shall also detail the numbers of private individuals who
 1. have requested access under the scheme and
 2. have been granted access under the scheme.
