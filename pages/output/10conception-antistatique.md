---
layout: page
title: Context for Antistatique's wireframing
---
# Context for Antistatique's wireframing

## Context

For the [Swiss National Licences](http://www.nationallicences.ch), private users are allowed to access protected online content, if they live in Switzerland. Interested persons need to create a Switch edu-ID account and fulfill some special conditions.

The Switch edu-ID framework is developed by [Switch](http://www.switch.ch/). It is a Single-Sign-On [Shibboleth based](https://en.wikipedia.org/wiki/Shibboleth_%28Internet2%29) platform. The main authentication features (user management, passwords, verified mobile phone number, verified post address) are dealt with by Switch. As some of the requirements are specific to National Licences (for example the terms of use of Swiss National Licences), they need to be dealt with by the swissbib platform.

The estimated number of potential users is 1000.

The access to the content will happen through the [swissbib.ch](http://swissbib.ch) platform, with Single Sign On with the publishers platform. The download of the pdf's happen on the publisher's platform. Signing in is also possible directly on the [publishers platform](http://dx.doi.org/10.1017/pli.2015.18), using institutional login with Switch edu-ID.


## Conditions to be satisfied to get an access to Swiss National Licences

 * User needs to accept terms and conditions for Swiss National licences
 * User must have a Switch edu-ID account (if they don't have one they should be able to create one within the same workflow)
 * User must have in its Switch edu-ID account a verified swiss mobile phone number and must have requested a temporary access in the last 14 days **OR** User has a verified postal address in Switzerland
 * User must not have been blocked by national licences administrators
 * User must have used its Switch edu-ID account in the last 12 months


## Current technical framework / possibilites

 * the Switch SAML attributes <https://www.switch.ch/aai/support/documents/attributes/>
 * All attributes are delivered using Shibboleth software (either when the user logs in Swissbib other via [Shibboleth backchannel](https://wiki.shibboleth.net/confluence/display/IDP30/SecurityAndNetworking#SecurityAndNetworking-Back-ChannelSupport))
 * Description of the possibilities to [customize login/registration](https://forge.switch.ch/projects/edu-id/wiki/Swiss_edu-ID_Registration_Form_Parameters) form from Switch
 * [Structure of the database](https://github.com/swissbib/vufind/blob/master/sbDocumentation/vf3sb_mysql_migrate_swiss_national_licences.sql) of National Licence Users on Swissbib side
 * [Templates](https://github.com/swissbib/vufind/tree/master/themes/sbvfrdsingle/templates/nationallicences) for the registration on the Swissbib side
 * To use Swissbib, only a basic Switch edu-ID is needed (email, name). The use of National Licences content within Swissbib requires the added verification to make sure that the person lives in Switzerland.


## Current status

 * Starting points :
   * registration page <http://www.consortium.ch/zugriff/?lang=en>
   * or a search result in swissbib, for example <https://www.swissbib.ch/Record/389737267>
   * or some news, like [this one](http://blog.bcul.ch/2017/01/plus-de-2-millions-darticles-scientifiques-accessibles-aux-residents-de-suisse/)
 * [Video](https://www.youtube.com/watch?v=mMT8tvHVi-8) of the registration process. Since the date of the video, the Switch edu-ID service has been undergoing a design revision (it is now responsive)
 * Currently Oxford University Press is performing a platform migration which creates problems with the authentication of private users. It is better to use content from [Cambridge University Press](https://www.swissbib.ch/Search/Results?lookfor=nationallicencecambridge*&type=AllFields) or [De Gruyter](https://www.swissbib.ch/Search/Results?lookfor=nationallicencegruyter*&type=AllFields&limit=20&sort=relevance) to test the service within the next days.

## List of current problems and possible solutions as discussed within the team

  * Switching constantly from Switch edu-ID interface to Swissbib interface is not good for the user experience
    * Extend the customized registration form to ask for the phone number / postal address at the same time (instead of only [name, email, password](https://youtu.be/mMT8tvHVi-8?t=1m05s))
    * Remove the possibility for the user to choose when the temporary access starts in Swissbib (user clicks the link and has a mobile phone in its Switch edu-ID account -> temporary access is created). The [Activate my temporary access button](https://youtu.be/mMT8tvHVi-8?t=4m02s) is not needed any more.
    * Automatically activate permanent access when user has a verified address (via log-in as well as via back-channel). The "Activate my permanent access" button is not needed any more.
    * The only thing which remains in Swissbib Interface would be the "Terms of use" for National Licences. Maybe include that in a customized workflow at Switch ?
  * Mobilnummerverifikation mit Flash-SMS kann ein Usabilityproblem darstellen (v.a. auf iPhones)
    * -> SWITCH könnte einfach auf normale SMS umschalten, wenn das erwünscht ist.
  * Nach e-mail Verifikation ist der ["Proceed-Button" nicht sichtbar](https://youtu.be/mMT8tvHVi-8?t=2m5s), und die Benutzer bleiben stecken.
    * mögl. Lösung: automatischer Redirect (bei erfolgreicher Verifikation)
    * mögl. Lösung: graphisches Redesign des Buttons
    * mögl. Lösung: Workflow sichtbar machen (Step 1, Step 2, ...)
  * Nach Initiierung der Postadressen-Verifikation erscheint eine [Bestätigung ohne "Proceed to Service" Link/Button]({{ site.github.url }}/public/images/switch-address-verification.png). Benutzer bleiben stecken in Switch edu-ID account management.
    * mögl Lösung: "Proceed to Service"  Button einfügen
  * terms of use of Switch edu-ID accepted twice : [first time](https://youtu.be/mMT8tvHVi-8?t=1m45s) and [second time](https://youtu.be/mMT8tvHVi-8?t=2m45s)
    * Switch will fix that to request it only once
  * User needs to accept the delivery of attributes for Swissbib and each publisher ([this screen](https://youtu.be/mMT8tvHVi-8?t=3m50s) and [this screen](https://youtu.be/mMT8tvHVi-8?t=5m21s)). Can we avoid that ?
    * The user consent is a very important part of Switch Privacy Policy. It cannot simply be avoided.
    * Switch will check if it can skip user consent for unpersonal attributes (like eduPersonEntitlement and Affiliation)
    * Switch will check if it is possible to gather several user consent in one step (for example Swissbib asks for the user consent for Swissbib as well as the various publishers)
  * User needs to login on Swissbib as well as on Switch edu-ID to manage its account
    * Switch will implement Single Sign-On for the Management of the Switch edu-ID account as well
  * if the person already has a Switch edu-ID and clicks on - <http://www.nationallizenzen.ch/anmeldung> - and then on - creates swiss edu-id - : she is redirected to the same page without any warning
    * -> Bug. Switch will fix that.
 * Header footer : sur les pages customized [registration](https://youtu.be/mMT8tvHVi-8?t=1m09s)/[login](https://youtu.be/mMT8tvHVi-8?t=0m56s),
   * améliorer les textes
   * faire un lien directement sur la [page pour les privés](http://www.consortium.ch/zugriff/?lang=en) plutôt que la page d'accueil des licences nationales.
* After successful registration, provide a way to search within national licences, see <https://github.com/swissbib/vufind/issues/478>
