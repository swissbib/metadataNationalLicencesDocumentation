---
layout: page
title: xmllint
---

# xmllint

Outil utile et rapide pour valider des xml contre des DTD ou alors vérifier qu'ils sont bien formés.

Vérifier que tous les fichiers xml sont bien formés :

`find . -name "*.xml" -type f -exec xmllint --noout {} \;`

Vérifier que tous les fichiers xml sont valides par rapport à une DTD donnée en argument :

`find . -name "*.xml" -type f -exec xmllint --noout --dropdtd --dtdvalid ~/Documents/swissbib/dtd/jats-publishing-dtd-1.0/JATS-journalpublishing1.dtd 2>>result.txt {} \;`


Ou alors sur un fichier sans warnings :

`xmllint swissbib-jats.xml --noout --dropdtd --dtdvalid ../../../dtd/JATS-Archiving-1-1-OASIS-MathML3-DTD/JATS-archive-oasis-article1-mathml3.dtd  --nowarning`

Quelques problèmes pour résoudre les DTD

 * il faut ajouter une entrée dans /etc/xml/catalog
 * quelque chose du genre ce qui suit (tiré du JATS xml framework de oxygen editor)

{% highlight xml %}
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE catalog
  PUBLIC "-//OASIS//DTD Entity Resolution XML Catalog V3.0//EN" "http://www.oasis-open.org/committees/entity/release/1.0/catalog.dtd">
<catalog xmlns="urn:oasis:names:tc:entity:xmlns:xml:catalog" prefer="public">
   <group xml:base="." prefer="public">
      <public publicId="-//NLM//DTD BITS Book Interchange DTD v0.2 20121015//EN"
              uri="O2-book.dtd"/>
      <public publicId="-//NLM//DTD BITS Book Interchange DTD with OASIS and XHTML Tables v0.2 20121015//EN"
              uri="O2-book-ot.dtd"/>
      <public publicId="-//NLM//DTD JATS (Z39.96) Journal Publishing DTD v1.0 20120330//EN"
              uri="O2-blue.dtd"/>
      <public publicId="-//NLM//DTD JATS (Z39.96) Journal Publishing DTD with OASIS Tables v1.0 20120330//EN"
              uri="O2-blue-ot.dtd"/>
      <public publicId="-//NLM//DTD JATS (Z39.96) Journal Archiving and Interchange DTD v1.0 20120330//EN"
              uri="O2-green.dtd"/>
      <public publicId="-//NLM//DTD JATS (Z39.96) Journal Archiving and Interchange DTD with OASIS Tables v1.0 20120330//EN"
              uri="O2-green-ot.dtd"/>
      <public publicId="-//NLM//DTD JATS (Z39.96) Article Authoring DTD v1.0 20120330//EN"
              uri="O2-orange.dtd"/>
   </group>
</catalog>
{% endhighlight %}


On peut ensuite avoir les erreurs principales ainsi
`more result.txt | sed -e's/^[^:]*:[0-9]*://g' | sort  | uniq -ci | sort -nr`
