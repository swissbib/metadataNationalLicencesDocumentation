---
layout: page
title: Questions pour les éditeurs
---



# Questions pour les éditeurs

Point de départ : document `AKTE_NL_Offer_Statement_2015_to_Publishers-Access-and-Metadata_20150918_osc.docx` ainsi que la licence modèle GASCO.

## Initial definitions

 * **Licensed Material** : information, documents or other elements (inclusive metadata). In particular, this includes the fulltext.
 * **Metadata** : set of structured information (technical or descriptive or for the management) attached to a specific part of the Licensed Material. Its purpose is to describe the characteristics of the Licensed Material in order to ease its discoverability, its management, its use or its preservation. In general, it doesn't include the fulltext of the documents.


## Questions for publishers - Metadata requirements

1. **Formats**. The Licensed Material shall be delivered to the Licensee by using open, standardized formats and accompanied by documentation.
  * Metadata for journal articles, book chapters, ... : XML. A DTD or XML Schema needs to be associated with the metadata (the preferred DTD is "NLM Journal Publishing Tag Library NISO JATS Version 1.0, August 2012" or a more recent version). Other DTD or schemas are accepted if they are well documented. For each record, the associated DTD or XML Schema must be specified.
  * Metadata for ebooks and similar : MARC21/MARCXML or NLM BITS XML
  * For full texts : PDF and/or HTML/XML
  * The description of the Licensed Material (for example at journal level) shall be delivered in KBART format, with the custom coverage dates licensed.

1. **Metadata contents**. The metadata shall include all fields that are available to the publisher on its platform. This means all fields that are displayed and/or searched on the publisher's platform, including enrichments, identifiers, covers, ... Later additions shall be delivered through updates.

1. **Metadata coverage**. The metadata shall be delivered for the Licensed Material in its entirety. The organization of the product into logical units (e.g. assignment of data records to products, of articles to journal titles) must be reflected by the data delivered.

1. **Delivery of metadata**. Publisher will provide the metadata through a standardized workflow for the Licensee to be able to deal with updates and deletions (for example when there are mistakes, retraction of articles, or whatever modifcations could happen). This shall be at least on a monthly basis (inclusive deletions if that happens). Preferred transfer protocol is OAI-PMH, but protocols like FTP, WebDAV, or others work as well, as long as there is a way to deal with updates and deletions.

1. **Delivery of licensed material**. Publisher will provide the licensed material on a commonly agreed medium.

1. **Accessibility of licensed material**.  Content has to be viewable with the usual tools like PDF-Viewer. The recommendation of the Web Accessibility Initiative (WAI) from the World Wide Web Consortium  needs to be taken into account. Copy / cut / paste needs to be possible.

1. **Character set**. Metadata has to be delivered in standardized character sets (utf8).

1. **Quality control**. Before the signature of the Licence, Publisher will provide all the metadata associated to the Licensed Material for the Licensor to be able to analyze the quality of the metadata.

1. **Metadata Licence**. Publisher delivers the Metadata under a Creative Commons Zero licence (CC0 see <http://creativecommons.org/publicdomain/zero/1.0/>).

1. **Interoperability with software and knowledge bases from Vendors**. Publisher has to have an active partnership with Vendors of Library Technology softwares (like ExLibris, EBSCO, ProQuest, OCLC). Regular transfers of standardized and complete metadata shall happen in the domains of
  * Link resolvers and the underlying knowledge bases : for example SFX by ExLibris or the open source project GoKB by Kuali
  * ERMS tools : for example Verde or Alma by ExLibris or 360 Resource Manager by Proquest
  * Discovery Index : for example Primo Central Index by ExLibris or Summon by ProQuest

1. **Documentation**. The delivery of the Licensed Material and the metadata shall be accompanied by documentation. Specifically : which DTD is used for which journals for which years ? How are the files structured (naming of the directories and the files if relevant) ? Way to deal with updates and deletions if the transfer arise via FTP ? Etc.


## Questions for publishers - Authentication requirements

1. **Authentication for private persons**. The authentication for private persons will happen on a dedicated Identity Provider from the Switch federation (using SAML/Shibboleth). The users affiliated to universities will continue to use their own University Identity Provider as before. For national licences, this means that access should be granted for more than 50 IdP (up to 100 in the future). Publisher is able to deal with that. Additionally, Publisher ensures that he is able to check that the SAML attribute `eduPersonEntitlement` has the value `urn:mace:dir:entitlement:common-lib-terms` to grant access.

1. **Registration for private users**. The registration process for private users will be done by the licensor. He will check that the user has an address in Switzerland either via post or via sms on a swiss handy number.
