---
layout: page
title: Swissbib JATS
---

# Swissbib JATS

Before ingesting into CBS and Swissbib, all incoming metadata is transformed into what we call Swissbib-JATS.

On this page are some considerations about Swissbib-JATS.

Swissbib-JATS is *JATS (Z39.96) Journal Archiving and Interchange DTD with OASIS Tables with MathML3 v1.1 20151215* as defined on <http://jats.nlm.nih.gov/archiving/tag-library/1.1/>.

You can find an example on Github : <https://github.com/swissbib/metadataNationalLicences/blob/master/xslt/swissbib-jats.xml>

Though some conventions are used. They are detailed here.

## Name of the pdf file

There is no exact field in JATS to save the name of the pdf file.

One option is [self-uri](http://jats.nlm.nih.gov/archiving/tag-library/1.1/element/self-uri.html), which is the one we use now.

In the future, we think it is a better idea to use [meta-name](http://jats.nlm.nih.gov/archiving/tag-library/1.1/element/meta-name.html) and [meta-value](http://jats.nlm.nih.gov/archiving/tag-library/1.1/element/meta-value.html) to store it as a custom field

## Metadata licence

TBD.
