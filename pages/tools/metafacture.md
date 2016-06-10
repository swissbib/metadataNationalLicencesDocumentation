---
layout: page
title: Metafacture
---

# Metafacture

## Informations générales

Projet de la DNB.


## Quick start

La manière la plus simple pour démarrer :


    git clone git@github.com:linked-swissbib/mfWorkflows.git
    ./flux.sh src/main/resources/transformation/resource/resource.flux


Cela crée un fichier `resourceOutput.rdf` dans `mfWorkflows/src/main/resources/transformation/resource`

## Première tentative

Objectif : avoir le nombre d'articles par titre de périodique du gros échantillon pmc.

Cela fonctionne et prend 2 minutes et 37 secondes.



## Notes suite discussion avec Nicolas Prongué le 11.11.2015

Github : linked-swissbib/, transformations sont dans mfWorkflow/src/main/resources/transformation

Metafacture fonctionne avec un fichier .flux qui indique le workflow (dans quel ordre, ...). La transformation pure est dans un xml.

Metafacture est un programme qui s'installe pour faire les transformations. Juste un script shell.

#### Exemple resource.flux :

file
open-file
decode-xml
handle-marcxml
-> des outils de Metafacture qui gère les métadonnées

C'est la "cosmétique"

#### Exemple resourceMorph.xml :

c'est le langage de transformation de Metamorph, il y a un petit wiki sur github/culturegraph/metafacture-core. Pas très bien fait.

On peut faire des lookup tables, des concat et autres.

Exemple d'un output resourceOutput.rdf, la transformation du fichier test correctMarcXML.xml

Pour exécuter le programme :

 ```
 flux.bat nom_du_fichier.flux
 ```

Transformation 300'000 notices test super rapide.

Instruction d'installation
metafacture-runner/wiki
-> plus mis à jour

Utilisé par HBZ, DNB, ...

Il y a une liste de discussion metamorph.

Voir les documents du tutoriel metafacture swib2014, suivi par Guenter et Nicolas.

## Remarques

Pour faire du generic-xml parsing, il faut que les noms de fichiers correspondants aux DTD soient présents dans le répertoire du fichier flux. Même si ils sont vides, ce n'est pas grave, mais si ils sont absents, alors ce n'est pas pris en compte par le parser SAX de Metafacture.

De plus, dans le cas où on a `<!DOCTYPE Publisher
  PUBLIC "-//Springer-Verlag//DTD A++ V2.4//EN" "http://devel.springer.de/A++/V2.4/DTD/A++V2.4.dtd">`, alors il faut modifier le fichier hosts ainsi ``

Pour faire du debug, il faut modifier le fichier log4j.xml qui est dans mfWorkflows/config et il faut faire `<priority value="debug" />` dans `root`

Commande pour complier `swissbib-metafacture-commandes` : `mvn clean install assembly:assembly -Dmaven.test.skip=true`

## Transformation XML -> ES-Bulk

Développé par le projet Linked Swissbib.

 * Petit problème : les entités doivent être déclarées (comme par exemple &ndash; ce qui est perdu quand on fait du merge)

## Flux Commands

On obtient ceci en exécutant `flux.sh` sans arguments.


        WELCOME TO METAFACTURE
        {version=3.0.1-SNAPSHOT, builtby=swissbib, git-commit=d2d27d4ded66a63a40a2f3ee9a0abb0423fe3f47, timestamp=1420298699284}

        Usage:	flux FLOW_FILE [VARNAME=VALUE ...]

        Available pipe elements:

        add-oreaggregation
        description:	adds ore:Aggregation to an Europeana Data Model stream. The aggregation id is set by emitting literal('aggregation_id', id)
        implementation:	org.culturegraph.mf.stream.pipe.OreAggregationAdder
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        add-preamble-epilogue
        description:	Adds a String preamle and/or epilogue to the stream
        options:	epilogue (java.lang.String), preamble (java.lang.String)
        implementation:	org.culturegraph.mf.stream.converter.PreambleEpilogueAdder
        signature:	java.lang.String -> java.lang.String

        as-formeta-records
        description:	Reads a stream of formeta data and splits between each top-level element
        implementation:	org.culturegraph.mf.stream.converter.FormetaRecordsReader
        signature:	java.io.Reader -> java.lang.String

        as-lines
        description:	Emits each line read as a string.
        implementation:	org.culturegraph.mf.stream.converter.LineReader
        signature:	java.io.Reader -> java.lang.String

        as-records
        description:	Reads data from a Reader and splits it into individual records
        options:	skipemptyrecords (boolean), separator (java.lang.String)
        implementation:	org.culturegraph.mf.stream.converter.RecordReader
        signature:	java.io.Reader -> java.lang.String

        batch-log
        description:	Writes log info for every BATCHSIZE records.
        options:	batchsize (int)
        implementation:	org.culturegraph.mf.stream.pipe.BatchLogger
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        batch-reset
        description:	Resets flow for every BATCHSIZE records.
        options:	batchsize (int)
        implementation:	org.culturegraph.mf.stream.pipe.BatchResetter
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        calculate-metrics
        description:	Calculates values for various cooccurrence metrics. The expected inputs are triples containing as subject the var name and as object the count. Marginal counts must appear first, joint counts second. Marinal counts must be written as 1:A, Joint counts as 2:A&B
        implementation:	org.culturegraph.mf.stream.pipe.stat.CooccurrenceMetricCalculator
        signature:	org.culturegraph.mf.types.Triple -> org.culturegraph.mf.types.Triple

        catch-object-exception
        description:	passes objects through and catches exceptions.
        options:	logprefix (java.lang.String), logstacktrace (boolean)
        implementation:	org.culturegraph.mf.stream.pipe.ObjectExceptionCatcher
        signature:	java.lang.Object -> java.lang.Object

        catch-stream-exception
        description:	passes streams events through and catches exceptions.
        implementation:	org.culturegraph.mf.stream.pipe.StreamExceptionCatcher
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        change-id
        description:	By default changes the record id to the value of the '_id' literal (if present). Use the contructor to choose another literal as id source.
        options:	keepidless (boolean), idname (java.lang.String), keepidliteral (boolean)
        implementation:	org.culturegraph.mf.stream.pipe.IdChangePipe
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        collect-triples
        description:	Collects named values to form records. The name becomes the id, the value is split by 'separator' into name and value
        implementation:	org.culturegraph.mf.stream.pipe.sort.TripleCollect
        signature:	org.culturegraph.mf.types.Triple -> org.culturegraph.mf.framework.StreamReceiver

        count-triples
        description:	Counts triples
        options:	countby [SUBJECT, PREDICATE, OBJECT, ALL], countpredicate (java.lang.String)
        implementation:	org.culturegraph.mf.stream.pipe.sort.TripleCount
        signature:	org.culturegraph.mf.types.Triple -> org.culturegraph.mf.types.Triple

        decode-cgentity
        description:	Reads Strings CGEntity format.
        implementation:	org.culturegraph.mf.stream.converter.CGEntityDecoder
        signature:	java.lang.String -> org.culturegraph.mf.framework.StreamReceiver

        decode-cgtext
        description:	Decodes a record stored in CG-Text format.
        implementation:	org.culturegraph.mf.stream.converter.CGTextDecoder
        signature:	java.lang.String -> org.culturegraph.mf.framework.StreamReceiver

        decode-csv
        description:	Decodes lines of CSV files. First line is interpreted as header.
        options:	hasheader (boolean)
        implementation:	org.culturegraph.mf.stream.converter.CsvDecoder
        signature:	java.lang.String -> org.culturegraph.mf.framework.StreamReceiver

        decode-formeta
        description:	Decodes a record in formeta format.
        implementation:	org.culturegraph.mf.stream.converter.FormetaDecoder
        signature:	java.lang.String -> org.culturegraph.mf.framework.StreamReceiver

        decode-mab
        description:	Parses a raw Mab2 stream (UTF-8 encoding expected).
        implementation:	org.culturegraph.mf.stream.converter.bib.MabDecoder
        signature:	java.lang.String -> org.culturegraph.mf.framework.StreamReceiver

        decode-marc21
        description:	Parses a raw Marc string (UTF-8 encoding expected).
        options:	checkutf8encoding (boolean)
        implementation:	org.culturegraph.mf.stream.converter.bib.MarcDecoder
        signature:	java.lang.String -> org.culturegraph.mf.framework.StreamReceiver

        decode-ntriples
        description:	Decodes lines of N-Triple files.
        options:	unicodeescapeseq (java.lang.String)
        implementation:	org.swissbib.linked.mf.decoder.NtriplesDecoder
        signature:	java.io.Reader -> org.culturegraph.mf.framework.StreamReceiver

        decode-pica
        description:	Parses pica+ records. The parser only parses single records. A string containing multiple records must be split into individual records before passing it to PicaDecoder.
        options:	ignoremissingidn (boolean), skipemptyfields (boolean), normalizeutf8 (boolean)
        implementation:	org.culturegraph.mf.stream.converter.bib.PicaDecoder
        signature:	java.lang.String -> org.culturegraph.mf.framework.StreamReceiver

        decode-string
        description:	Splits a String into several Strings, either by extracting parts that match a regexp or by splitting by a regexp.
        options:	mode [SPLIT, EXTRACT]
        implementation:	org.culturegraph.mf.stream.pipe.StringDecoder
        signature:	java.lang.String -> java.lang.String

        decode-xml
        description:	Reads an XML file and passes the XML events to a receiver.
        implementation:	org.culturegraph.mf.stream.converter.xml.XmlDecoder
        signature:	java.io.Reader -> org.culturegraph.mf.framework.XmlReceiver

        digest-file
        description:	Uses the input string as a file name and computes a cryptographic hash the file
        implementation:	org.culturegraph.mf.stream.pipe.FileDigestCalculator
        signature:	java.lang.String -> org.culturegraph.mf.types.Triple

        draw-uniform-sample
        description:	Draws a uniform sample of records from the input stream.
        implementation:	org.culturegraph.mf.stream.pipe.UniformSampler
        signature:	java.lang.Object -> java.lang.Object

        encode-cgentity
        description:	Encodes a stream in CGE Format
        implementation:	org.culturegraph.mf.stream.converter.CGEntityEncoder
        signature:	org.culturegraph.mf.framework.StreamReceiver -> java.lang.String

        encode-esbulk
        description:	Serialises an object as JSON-LD
        options:	index (java.lang.String), escapechars (java.lang.String), type (java.lang.String), header (java.lang.String)
        implementation:	org.swissbib.linked.mf.pipe.ESBulkEncoder
        signature:	org.culturegraph.mf.framework.StreamReceiver -> java.lang.String

        encode-formeta
        description:	Encodes streams in formeta format.
        options:	style [CONCISE, VERBOSE, MULTILINE]
        implementation:	org.culturegraph.mf.stream.converter.FormetaEncoder
        signature:	org.culturegraph.mf.framework.StreamReceiver -> java.lang.String

        encode-json
        description:	Serialises an object as JSON
        options:	prettyprinting (boolean)
        implementation:	org.culturegraph.mf.stream.converter.JsonEncoder
        signature:	org.culturegraph.mf.framework.StreamReceiver -> java.lang.String

        encode-literals
        description:	Formats litereals in a stream
        options:	separator (java.lang.String)
        implementation:	org.culturegraph.mf.stream.converter.StreamLiteralFormater
        signature:	org.culturegraph.mf.framework.StreamReceiver -> java.lang.String

        encode-marc21
        description:	Encodes MARC21 records
        implementation:	org.culturegraph.mf.stream.converter.bib.Marc21Encoder
        signature:	org.culturegraph.mf.framework.StreamReceiver -> java.lang.String

        encode-ntriples
        description:	Encodes data in Formeta format to N-triples RDF serialization.
        implementation:	org.swissbib.linked.mf.pipe.NtriplesEncoder
        signature:	org.culturegraph.mf.framework.StreamReceiver -> java.lang.String

        encode-pica
        description:	Encodes a stream in pica+ format
        options:	ignorerecordid (boolean)
        implementation:	org.culturegraph.mf.stream.converter.bib.PicaEncoder
        signature:	org.culturegraph.mf.framework.StreamReceiver -> java.lang.String

        extract-literals
        description:	Extracts literal values from a stream.
        options:	pattern (java.lang.String)
        implementation:	org.culturegraph.mf.stream.converter.LiteralExtractor
        signature:	org.culturegraph.mf.framework.StreamReceiver -> java.lang.String

        filter
        description:	Filters a stream based on a morph definition. A record is accepted if the morph returns at least one non empty value.
        implementation:	org.culturegraph.mf.stream.pipe.Filter
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        filter-duplicate-objects
        description:	Filters consecutive duplicated data objects.
        implementation:	org.culturegraph.mf.stream.pipe.DuplicateObjectFilter
        signature:	java.lang.Object -> java.lang.Object

        filter-strings
        description:	Only forwards records which match (or do not match) a regular expression given in the constructor
        options:	passmatches (boolean)
        implementation:	org.culturegraph.mf.stream.pipe.StringFilter
        signature:	java.lang.String -> java.lang.String

        filter-triples
        description:	Filters triple. The  patterns for subject, predicate and object are disjunctive.
        options:	passmatches (boolean), objectpattern (java.lang.String), subjectpattern (java.lang.String), predicatepattern (java.lang.String)
        implementation:	org.culturegraph.mf.stream.pipe.TripleFilter
        signature:	org.culturegraph.mf.types.Triple -> org.culturegraph.mf.types.Triple

        flatten
        description:	flattens out entities in a stream by introducing dots in literal names
        options:	entitymarker (java.lang.String)
        implementation:	org.culturegraph.mf.stream.pipe.StreamFlattener
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        generic-xml
        description:	Generic reader for xml files
        implementation:	org.culturegraph.mf.stream.reader.GenericXmlReader
        signature:	java.io.Reader -> org.culturegraph.mf.framework.StreamReceiver

        handle-cg-xml
        description:	Reads CG-XML files
        implementation:	org.culturegraph.mf.stream.converter.xml.CGXmlHandler
        signature:	org.culturegraph.mf.framework.XmlReceiver -> org.culturegraph.mf.framework.StreamReceiver

        handle-generic-xml
        description:	A generic xml reader
        implementation:	org.culturegraph.mf.stream.converter.xml.GenericXmlHandler
        signature:	org.culturegraph.mf.framework.XmlReceiver -> org.culturegraph.mf.framework.StreamReceiver

        handle-marcxml
        description:	A marc xml reader
        implementation:	org.culturegraph.mf.stream.converter.xml.MarcXmlHandler
        signature:	org.culturegraph.mf.framework.XmlReceiver -> org.culturegraph.mf.framework.StreamReceiver

        index-esbulk
        description:	Outputs an Elasticsearch Bulk API compliant file.
        options:	footer (java.lang.String), esnodes (java.lang.String), encoding (java.lang.String), esclustername (java.lang.String), recordsperupload (int), compression (java.lang.String), separator (java.lang.String), header (java.lang.String)
        implementation:	org.swissbib.linked.mf.writer.ESBulkIndexer
        signature:	java.lang.Object -> java.lang.Void

        jscript
        description:	executes the function process(obj) in a given jscript
        options:	invoke (java.lang.String)
        implementation:	org.culturegraph.mf.stream.pipe.JScriptObjectPipe
        signature:	java.lang.Object -> java.lang.Object

        log-object
        description:	logs objects with the toString method
        implementation:	org.culturegraph.mf.stream.pipe.ObjectLogger
        signature:	java.lang.Object -> java.lang.Object

        log-stream
        description:	logs events
        implementation:	org.culturegraph.mf.stream.pipe.StreamLogger
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        log-time
        description:	Benchmarks the execution time of the downstream modules.
        implementation:	org.culturegraph.mf.stream.pipe.ObjectTimer
        signature:	java.lang.Object -> java.lang.Object

        match
        description:	Matches the incoming strings against a regular expression and replaces the matching parts.
        options:	replacement (java.lang.String), pattern (java.lang.String)
        implementation:	org.culturegraph.mf.stream.pipe.StringMatcher
        signature:	java.lang.String -> java.lang.String

        merge-batch-stream
        description:	Merges a sequence of batchSize records
        options:	batchsize (int)
        implementation:	org.culturegraph.mf.stream.pipe.StreamBatchMerger
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        morph
        description:	applies a metamorph transformation to the event stream. Metamorph definition is given in brackets.
        implementation:	org.culturegraph.mf.morph.Metamorph
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        normalize-utf8
        description:	Normalizes diacritics UTF-8 encoded strings.
        implementation:	org.culturegraph.mf.stream.pipe.Utf8Normalizer
        signature:	java.lang.String -> java.lang.String

        object-batch-log
        description:	Writes log info for every BATCHSIZE records.
        options:	batchsize (int)
        implementation:	org.culturegraph.mf.stream.pipe.ObjectBatchLogger
        signature:	java.lang.Object -> java.lang.Object

        object-tee
        description:	Sends an object to more than one receiver.
        implementation:	org.culturegraph.mf.stream.pipe.ObjectTee
        signature:	java.lang.Object -> java.lang.Object

        object-to-literal
        description:	Outputs a record containing the input object as literal
        options:	literalname (java.lang.String)
        implementation:	org.culturegraph.mf.stream.converter.ObjectToLiteral
        signature:	<unknown> -> org.culturegraph.mf.framework.StreamReceiver

        open-bzip2
        description:	Opens a bzip2 file.
        options:	buffersize (int), encoding (java.lang.String)
        implementation:	org.culturegraph.mf.stream.source.Bzip2Opener
        signature:	java.lang.String -> java.io.Reader

        open-file
        description:	Opens a file.
        options:	encoding (java.lang.String), compression [NONE, AUTO, BZIP2, GZIP, PACK200, XZ]
        implementation:	org.culturegraph.mf.stream.source.FileOpener
        signature:	java.lang.String -> java.io.Reader

        open-gzip
        description:	Opens a gz file.
        options:	buffersize (int), encoding (java.lang.String)
        implementation:	org.culturegraph.mf.stream.source.GzipOpener
        signature:	java.lang.String -> java.io.Reader

        open-http
        description:	Opens a http resource. Supports the setting of Accept and Accept-Charset as http header fields.
        options:	accept (java.lang.String), encoding (java.lang.String)
        implementation:	org.culturegraph.mf.stream.source.HttpOpener
        signature:	java.lang.String -> java.io.Reader

        open-resource
        description:	Opens a resource.
        options:	encoding (java.lang.String)
        implementation:	org.culturegraph.mf.stream.source.ResourceOpener
        signature:	java.lang.String -> java.io.Reader

        pass-through
        description:	A simple pass-through module
        implementation:	org.culturegraph.mf.stream.pipe.IdentityStreamPipe
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        rdf-macros
        description:	Expands same macros for RDF/XML
        options:	autoaddedsubject (java.lang.String)
        implementation:	org.culturegraph.mf.stream.pipe.RdfMacroPipe
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        read-beacon
        description:	Reads BEACON format
        options:	buffersize (int), relation (java.lang.String), metadatafilter (java.lang.String)
        implementation:	org.culturegraph.mf.stream.reader.BeaconReader
        signature:	java.io.Reader -> org.culturegraph.mf.framework.StreamReceiver

        read-dir
        description:	Reads a directory and emits all filenames found.
        options:	recursive (boolean)
        implementation:	org.culturegraph.mf.stream.source.DirReader
        signature:	java.lang.String -> java.lang.String

        read-string
        description:	Creates a reader for the supplied string and sends it to the receiver
        implementation:	org.culturegraph.mf.stream.source.StringReader
        signature:	java.lang.String -> java.io.Reader

        read-triples
        implementation:	org.culturegraph.mf.stream.source.TripleReader
        signature:	<unknown> ->

        regex-decode
        description:	Decodes an incoming string based on a regular expression using named-capturing groups
        options:	defaultliteralname (java.lang.String)
        implementation:	org.culturegraph.mf.stream.converter.RegexDecoder
        signature:	java.lang.String -> org.culturegraph.mf.framework.StreamReceiver

        remodel-pica-multiscript
        description:	Groups multiscript fields in entities
        implementation:	org.culturegraph.mf.stream.pipe.PicaMultiscriptRemodeler
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        reorder-triple
        description:	Shifts subjectTo predicateTo and object around
        options:	objectfrom [SUBJECT, PREDICATE, OBJECT], subjectfrom [SUBJECT, PREDICATE, OBJECT], predicatefrom [SUBJECT, PREDICATE, OBJECT]
        implementation:	org.culturegraph.mf.stream.pipe.TripleReorder
        signature:	org.culturegraph.mf.types.Triple -> org.culturegraph.mf.types.Triple

        retrieve-triple-objects
        description:	Uses the object value of the triple as a URL and emits a new triple in which the object value is replaced with the contents of the resource identified by the URL.
        options:	defaultencoding (java.lang.String)
        implementation:	org.culturegraph.mf.stream.pipe.TripleObjectRetriever
        signature:	org.culturegraph.mf.types.Triple -> org.culturegraph.mf.types.Triple

        sort-triples
        description:	Sorts triples
        options:	order [INCREASING, DECREASING], by [SUBJECT, PREDICATE, OBJECT, ALL]
        implementation:	org.culturegraph.mf.stream.pipe.sort.TripleSort
        signature:	org.culturegraph.mf.types.Triple -> org.culturegraph.mf.types.Triple

        split-entities
        description:	Extracts entities of a record on a certain level (default 0) and forwards them as individual records.
        options:	entityboundary (java.lang.String)
        implementation:	org.swissbib.linked.mf.pipe.EntitySplitter
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        split-lines
        description:	Splits a string at new lines and sends each line to the receiver.
        implementation:	org.culturegraph.mf.stream.pipe.LineSplitter
        signature:	java.lang.String -> java.lang.String

        stream-count
        description:	Counts the number of records and fields read.
        implementation:	org.culturegraph.mf.stream.pipe.Counter
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        stream-tee
        description:	Replicates an event stream to an arbitrary number of stream receivers.
        implementation:	org.culturegraph.mf.stream.pipe.StreamTee
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.framework.StreamReceiver

        stream-to-triples
        description:	Takes literals from a stream and emits them as triples such that the name and value become predicate and object and the record id the subject. If 'redirect' is true, use '_id' to change the id, or '{to:ID}NAME' to change the id of a single literal. Set 'recordPredicate' to encode a complete record in one triple. The value of 'recordPredicate' is used as the predicate of the triple. If 'recordPredicate' is set, no {to:ID}NAME-style redirects are possible.
        options:	redirect (boolean), recordpredicate (java.lang.String)
        implementation:	org.culturegraph.mf.stream.converter.StreamToTriples
        signature:	org.culturegraph.mf.framework.StreamReceiver -> org.culturegraph.mf.types.Triple

        stream-to-xml
        description:	Encodes a stream as xml
        options:	roottag (java.lang.String), recordtag (java.lang.String), separateroots (boolean), writexmlheader (boolean), namespacefile (java.lang.String)
        implementation:	org.culturegraph.mf.stream.converter.xml.SimpleXmlEncoder
        signature:	org.culturegraph.mf.framework.StreamReceiver -> java.lang.String

        template
        description:	Builds a String from a template and an Object. Provide template in brackets. ${o} marks the place where the object is to be inserted. If the object in an instance of Triple ${s}, ${p} and ${o} are used instead
        implementation:	org.culturegraph.mf.stream.converter.ObjectTemplate
        signature:	java.lang.Object -> java.lang.String

        triples-to-stream
        description:	Converts a triple into a record stream
        implementation:	org.culturegraph.mf.stream.converter.TriplesToStream
        signature:	org.culturegraph.mf.types.Triple -> org.culturegraph.mf.framework.StreamReceiver

        wait-for-inputs
        description:
        implementation:	org.culturegraph.mf.stream.pipe.CloseSupressor
        signature:	java.lang.Object -> java.lang.Object

        write
        description:	Writes objects to stdout or a file
        argument in	[stdout, PATH]
        options:	footer (java.lang.String), encoding (java.lang.String), compression [NONE, AUTO, BZIP2, GZIP, PACK200, XZ], separator (java.lang.String), header (java.lang.String)
        implementation:	org.culturegraph.mf.stream.sink.ObjectWriter
        signature:	java.lang.Object -> java.lang.Void

        write-esbulk
        description:	Outputs an Elasticsearch Bulk API compliant file.
        options:	footer (java.lang.String), outfileprefix (java.lang.String), filesize (int), encoding (java.lang.String), jsoncompliant (java.lang.String), compression (java.lang.String), separator (java.lang.String), header (java.lang.String), filesperdir (int), baseoutdir (java.lang.String)
        implementation:	org.swissbib.linked.mf.writer.ESBulkWriter
        signature:	java.lang.Object -> java.lang.Void

        write-rdf-1line
        description:	Writes RDF/XML documents in outpufiles. Each document is written down in one line which makes it easer for further processing
        options:	footer (java.lang.String), usecontributor (boolean), roottag (java.lang.String), filesize (int), outfileprefix (java.lang.String), concept [BIBLIOGRAPHICRESOURCE, ITEM, ORGANIZATION, PERSON, WORK], encoding (java.lang.String), compression (java.lang.String), subdir (boolean), separator (java.lang.String), filesperdir (int), header (java.lang.String), baseoutdir (java.lang.String)
        implementation:	org.swissbib.linked.mf.writer.SingleLineWriterRDFXml
        signature:	java.lang.Object -> java.lang.Void

        write-rdf-trigger
        options:	footer (java.lang.String), usecontributor (boolean), roottag (java.lang.String), commandpath (java.lang.String), filesize (int), outfileprefix (java.lang.String), concept [BIBLIOGRAPHICRESOURCE, ITEM, ORGANIZATION, PERSON, WORK], encoding (java.lang.String), compression (java.lang.String), subdir (boolean), separator (java.lang.String), header (java.lang.String), baseoutdir (java.lang.String)
        implementation:	org.swissbib.linked.mf.writer.RDFXmlWriterTrigger
        signature:	<unknown> ->

        write-triple-objects
        description:	Writes the object value of the triple into a file. The filename is constructed from subject and predicate. Please note: This module does not check if the filename constructed from subject and predicate stays within `baseDir`. THIS MODULE SHOULD NOT BE USED IN ENVIRONMENTS IN WHICH THE VALUES OF SUBJECT AND PREDICATE A PROVIDED BY AN UNTRUSTED SOURCE!
        options:	encoding (java.lang.String)
        implementation:	org.culturegraph.mf.stream.sink.TripleObjectWriter
        signature:	org.culturegraph.mf.types.Triple -> java.lang.Void

        write-triples
        description:	Writes triples into a file.
        implementation:	org.culturegraph.mf.stream.sink.TripleWriter
        signature:	org.culturegraph.mf.types.Triple -> java.lang.Void
