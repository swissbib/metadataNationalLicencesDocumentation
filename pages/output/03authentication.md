---
layout: page
title: Authentification
---

# Authentification (pour les non-membres d'une uni suisse)


Il y a une [liste détaillée](http://lib.consortium.ch/html_wrapper.php?dir=libraries&src=addresses1&activeElement=5) avec les sites web des bibliothèques et les personnes de contact (y compris téléphone)

## Téléphone Rolf Brugger 7.3.2016

 * `common-lib-terms` n'est pas encore implémenté sur swiss edu-id. Il faut passer par le IdP VHO pour faire des tests. Là `common-lib-terms` est implémenté, mais il y a en plus un attribut `http://partner-switchaai.ch/cambridge` dans `eduPersonEntitlement`. Ceci est spécifique au VHO.

## Liens

 * [swiss edu-id](https://eduid.ch/web/registration/1/)
 * [libraries.ch](https://www.libraries.ch/users/new?locale=en) - [switch idp](https://www.switch.ch/aai/participants/allhomeorgs/#libraries.ch)
 * [wiki de documentation switch aai](https://dokuwiki.toolbox.switch.ch/aai-lib-cons/inoperation)

## Remarque de Thomas Lenggenhager de Switch du 8 janvier 2016

> Im Kontext der Nationallizenzen muss man sich bewusst sein, welche
> technischen Möglichkeiten die Anbieter lizenzierter Inhalte in ihrer
> SAML Implementation zur Verfügung haben um Benutzer auf Lizenzen mappen
> zu können. Es gibt noch immer Anbieter die nur fähig sind eine EntityID
> zu einer Lizenz zu mappen (ohne irgendwelche Attributwerte zu
> berücksichtigen zu können, d.h. ohne jegliche Möglichkeit zur
> Autorisierungs-Einschränkung auf dem SP!) und somit alle Benutzer des
> IdPs mit dieser EntityID dann Zugriff haben.
>
> Bei Swiss edu-ID 1.0 hätten dann sämtliche Swiss edu-ID Benutzer
> Zugriff, ob Wohnsitz in der Schweiz oder als Alumni im Ausland lebend.
>
> Für so 'rückständige' Anbieter müsste wohl ein EZproxy dazwischen
> geschaltet werden um dort die Autorisierung gemäss den Lizenzbedingungen
> vornehmen zu können, die der Anbieter nicht selbst vornehmen kann.
> Dies könnte vermieden werden, wenn Nationallizenzen nur für Anbieter
> abgeschlossen werden die in der Lage sind eine zeitgemässe Autorisierung
> auf der SP Seite durchzuführen, z.B. auf der Basis von einem speziellen
> Entitlement Wert.

et

> Der Login via libraries.ch wird verwendet um für die e-Book Ausleihe auf
> den SWITCHaai Federation Partner Ebooks Corporation Ltd zuzugreifen.
> Solche Service Provider lizenzierter Inhalte müssen die Lizenzen auf
> eine Affiliation zu einer Institutionen abbilden können. Das ist etwas
> was in Swiss edu-ID 1.0 noch nicht möglich ist. Der SP könnte nicht
> unterscheiden welcher Swiss edu-ID Benutzer als Privatkunde der
> ETH-Bibliothek registriert ist und welcher nichts mit der ETH-Bibliothek
> am Hut hat. Dies auch ein technischer Grund für den nun gewählten Ansatz.


## Remarque de Lisa Ott de l'ETH au sujet de la plateforme e-lending et libraries.ch, 9.2.2016

> Zu Ihrer ersten Frage: Ob sich der Wohnsitz einer Person tatsächlich in der Schweiz befindet, prüfen wir persönlich vor Ort. Wenn sich eine neue Kundin/ein neuer Kunde auf libraries.ch einschreibt, erhält sie/er die Aufforderung, ein NEBIS-Konto zu erstellen und sich am Schalter auszuweisen. Existiert bereits ein NEBIS-Konto kann der Wohnsitz über dieses NEBIS-Konto geprüft werden, da auch das NEBIS-Konto nur freigeschaltet wurde, wenn die Person sich persönlich an einem der Schalter der ETH-Bibliothek ausgewiesen hat.

et

>Ihre zweite Frage ist schwerer zu beantworten: Im letzten Jahr hatten wir ca. **1‘650 Nutzer** von E-Lending. Leider kann ich aktuell aber keine Aussagen zu den letzten Monaten oder gar Prognosen für die kommenden Monate machen.

## Réponses des éditeurs

### Question

Authorised Users means as well scientifically interested private individuals (to the requirement of permanent residence in Switzerland) that have completed a suitable registration procedure.

### Cambridge

We accept this definition

### Oxford

Inclusion of scientifically interested private individuals can be accepted, provided (i) rights to the Licensed Works are limited to use for non-commercial research purposes and (ii) CSAL have set up a suitable registration procedure in agreement with OUP

### De Gruyter

Yes, accepted in general for the licensed Journal Archives within the National License. The licensee is kindly requested
to specify the registration tool which guarantees a secure registration process. Furthermore the licensee should review
on a regular (annual) basis if users still meet the requirements to be authorised to access.

### Springer

YES and it should be possible to give Springer a list of
these registered private individuals on request.
