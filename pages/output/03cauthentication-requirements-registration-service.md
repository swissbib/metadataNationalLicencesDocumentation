---
layout: page
title: Requirements for the Registration service of Swiss National Licences
---
# Registration service of private persons for Swiss National Licences

## Context

For the [Swiss National Licences](http://www.swissuniversities.ch/fileadmin/swissuniversities/Dokumente/DE/UH/SUK_P-2/Abstract_Nationallizenzen.pdf), private users are allowed to access protected online content, if they live in Switzerland. Interested persons will need to [create a Swiss edu-ID](https://eduid.ch/web/registration/1/) account and fulfill some special conditions.

The Swiss edu-ID framework is developed by [Switch](http://www.switch.ch/). It is a Single-Sign-On [Shibboleth based](https://en.wikipedia.org/wiki/Shibboleth_%28Internet2%29) platform. The main authentication features (user management, passwords, verified mobile phone number, verified post address) are dealt with by Switch. As some of the requirements are specific to National Licences, they need to be added to the swissbib platform.

The estimated number of potential users is 1000.

The access to the pdf will happen through the [swissbib.ch](http://swissbib.ch) platform. Access is also possible directly on a [publisher's platform](http://dx.doi.org/10.1093/occmed/kqs039).


## Requirements

### What needs to be done by Snowflake

Below, the whole processes are described. Some developments are done by Switch, some by Swissbib and some by Snowflake. The processes that need to be developed by snowflake are

 * 1.4. Swissbib user account - tab National Licences
 * 2 Management of registered users (includes 2.1, 2.2, 2.3)

### Technical Stack

The technical stack is

 * PHP / Zend Framework 2
 * MySQL
 * Shibboleth / SAML authentication mechanisms. [Implementation of Shibboleth in VuFind](https://github.com/swissbib/vufind/blob/master/module/VuFind/src/VuFind/Auth/Shibboleth.php)
 * [VuFind](http://vufind.org) : an open source software which is the basis of Swissbib.ch (based on PHP / Zend Framework).


### Conditions to be satisfied to get an access to Swiss National Licences

 * User needs to accept terms and conditions for Swiss National licences
 * User must have a Swiss edu-ID account
 * User must have in its Swiss edu-ID account a verified swiss mobile phone number and must have requested a temporary access in the last 14 days **OR** User has a verified postal address in Switzerland
 * User must not have been blocked by national licences administrators
 * User must have used its Swiss edu-ID account in the last 12 months



### List of Switch services which are to be used and are implemented

 * the Switch SAML attributes https://www.switch.ch/aai/support/documents/attributes/
 * All attributes are delivered using Shibboleth software (either when the user logs in Swissbib other via [Shibboleth backchannel](https://wiki.shibboleth.net/confluence/display/IDP30/SecurityAndNetworking#SecurityAndNetworking-Back-ChannelSupport))

### List of Switch services which are to be used and not implemented yet

feature | specification date | available for development | available in production
------- | ------------------ | ------------------------- | -----------------------  
SWITCH will provide an interface to store the shared property `national-licence-compliant` of a person, that defines if the person currently fulfills all conditions to get access to contents in the context of the national licence program. SWITCH will use this property to set the value `urn:mace:dir:entitlement:common-lib-terms` to the SAML attribute `eduPersonEntitlement`. This SAML attribute will be delivered to the publisher's platforms.||mid Aug'16|mid Sept'16
SWITCH will add [quality statements](https://projects.switch.ch/eduid/about/quality/) to attributes. This allows for example to see if a post address has been verified or not.|mid July'16|mid Sept'16|mid Oct'16
SWITCH will fill the attribute swissLibraryPersonResidence with the country chosen in the postal address||mid Aug'16|mid Sept'16

---

# Details of the various processes

## 1. Full Process for a new user

### 1.1. User gets a link for the registration

A user makes a search in Swissbib green. Based on its IP address, the system detects that the user doesn't belong to the network of the swiss universities.

![registration link]({{ site.github.url }}/public/images/swissbib_search_registration.png)

The user then clicks on a link to register for an access as a swiss resident. The links is like that

<https://eduid.ch/web/registration/1/?return=https%3A%2F%2Fwww.swissbib.ch%2FMyResearch%2FNationalLicences&forcereturn=yes&view=c920a46e>

This link is a normal Swiss edu-ID registration but

 * at the end the user is redirected to the national licences options in swissbib user account
 * the registration form is customized to always display the required fields for national licences ([Documentation](https://forge.switch.ch/projects/edu-id/wiki/Swiss_edu-ID_Registration_Form_Parameters) about this customization.)

The origin of this link could be swissbib, the consortium website or any kind of website (participating libraries...)

Remarks :

 * at the end the goal is to merge the buttons "get-it" and "register for an access as a swiss resident"
 * when the IP address is in a university, the button "register for an access as a swiss resident" is hidden and the url behind "get-it" is a different one. It goes directly to the publishers platform, without requiring first a shibboleth authentication.

---


### 1.2. Swiss edu-ID Registration step 1

The user creates a Swiss edu-ID account.

![eduid step 1]({{ site.github.url }}/public/images/edu-id-step1.png)

---


### 1.3. Swiss edu-ID Registration step 2

* Here any addresses (also foreign addresses) and phone numbers (also foreign numbers) can be registered.
* The process of validating the phone number and the postal addresses can be triggered here
* After a successful registration, user is redirected to swissbib user account

![eduid step 2]({{ site.github.url }}/public/images/edu-id-step2.png)

---

### 1.4. Swissbib user account - tab National Licences

This is what needs to be developed by Snowflake. To be granted access to Swiss National Licences, the conditions described above (page 1) must be satisfied.

Mockup :

![Mockup User Account]({{ site.github.url }}/public/images/swissbib-user-account2.png)

Here is what needs to be done in more details.


**Option 1 : Temporary access**

1. allow user to activate its temporary access valid 14 days. This can only be requested once. To be able to request this, the user needs to have a verified **swiss** (number begins with +41 79, 78, 77, ???) mobile phone number in its Swiss edu-ID account.

**Option 2 : Permanent access**

1. check if the shibboleth attribute `swissLibraryPersonResidence` has the value `CH` (Switzerland). If the value is missing, request user to fill its attribute `homePostalAddress` in Swiss edu-ID. If the value is in a foreign country, tell the user that this service is only for swiss residents.
2. check if the [quality level](https://projects.switch.ch/eduid/about/faq/#get-quality-attr) of the shibboleth attribute `homePostalAddress` is `verified`. If not, allow user to request a verification of postal address (the verification is than done by Switch, but the request is on the Registration Service side)

**Always**

1. allow user to accept terms and conditions for Swiss National Licences (checkbox). Record that in a local database.
2. show to the user if its account has been blocked by national licences administrators.
3. If all conditions are met (see page one), set the flag `national-licence-compliant` using Switch REST API. Display to the user that he is "national-licence-compliant"


To manage all this process, the details need to be recorded in a database. A small draft follows

edu-id [unique-id](https://www.switch.ch/aai/support/documents/attributes/swissedupersonuniqueid/index.html) (or [persistendId](https://www.switch.ch/aai/support/documents/attributes/edupersontargetedid/index.html)) | conditions accepted | request temporary access with sms on swiss mobile phone | End of validity of temporary access | user is blocked | post adress | name, phone number, country... ? | last swiss edu_id activity
--- | --- | --- | --- | --- | ---- |
8247315@eduid.ch | yes | yes | 8.4.2016 at 18h30 | no | Rue Faller 2, 1202 Geneve | &nbsp; | 1.5.2015
8783431@eduid.ch | yes | no | | yes | Novartis Campus, 4056 Basel | &nbsp; | 1.12.2015

This will be stored in the existing VuFind Database (MySQL). One option would be to store this additional attributes in the [existing VuFind User table](https://github.com/swissbib/vufind/blob/master/module/VuFind/sql/mysql.sql#L162) and the other would be to have a dedicated table for the National Licences workflow. Right now, the second option is preferred.



---



## 2. Management of registered users

### 2.1 When a user log-in to swissbib

 * at each login store in the database the most recent relevant attributes from user (email, phone number, country of residence, ...)
 * update the flag `national-licence-compliant` in Swiss edu-ID if necessary

---

### 2.2 Front-end for National Licences administrators

Develop a web interface that allows National Licences administrators (2-3 people from the Consortium) to :

 * ~~block a user~~ (this will be done manually in the database, shouldn't happen more than once a year)
 * see the list of registered users
 * display the total number of currently registered users for swiss national licences as well as the number of temporary access requested

 A good start could be the [libadmin interface](https://github.com/swissbib/libadmin). This interface allows Swissbib Administrators to manage the >900 libraries within Swissbib. It has been developed by Snowflake in April 2013.

 ![Screenshot Libraries Management]({{ site.github.url }}/public/images/libadmin.png)

 ---

### 2.3 Maintenance Tasks

* once a week, for each National Licence compliant user, update the attributes (last activity date, postal address, country of residence, ...) from Swiss edu-ID (using Switch [Shibboleth Back-Channel](https://wiki.shibboleth.net/confluence/display/IDP30/SecurityAndNetworking#SecurityAndNetworking-Back-ChannelSupport)).
* If the last activity date is more than one year ago, send an email to the user with a link to extend its account (with some time). To extend its account, the user needs to log in, therefore the system can update the attributes if needed. Otherwise, unset the `national-licence-compliant` flag.
* If the post address has been updated (either it is not verified any more or it is in a foreign country), update the flag `national-licence-compliant` accordingly in Swiss edu-ID.

---

## 3. Full Process for a registered user

This process doesn't involve snowflake. This is just described so that you get the big picture.

### 3.1. User gets a link

 * user gets a link to an article from swissbib

![link swissbib]({{ site.github.url }}/public/images/mockup.png)

---

 * or user gets a link from google scholar or any other search engine

![link google scholar]({{ site.github.url }}/public/images/google_scholar.png)

---

### 3.2. Article webpage - no access

The user lands on the publisher's platform. As he is not authenticated, he can not download the pdf. He then logs in.

![cambridge no access]({{ site.github.url }}/public/images/cambridge-no-access.png)

---


### 3.3. Log in via Swiss edu ID - choose federation and IDP

User needs to choose its own institution. For swiss private users, it will be Swiss edu-ID.

![login federation]({{ site.github.url }}/public/images/login-federation-cambridge.png)

---

### 3.4. Log in

User gives its Swiss edu-ID credentials.

![login Swiss edu-ID]({{ site.github.url }}/public/images/login-eduid.png)

---

### 3.5. Article webpage - with access

Now the user is authenticated and can download the pdf.

![cambridge no access]({{ site.github.url }}/public/images/cambridge-access.png)

**Remark** : It might be possible to skip steps 3.2. and 3.3 using WAYFless url's. But this depends on the publisher's platform software (should support WAYFless url's).
