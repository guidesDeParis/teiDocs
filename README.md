teiDocs
=======

###Goal

The goal of this project is to generate documentation for the subset of TEI elements in a particular TEI document.

###Technology

The code consists of an XQuery module along with the [tei_all.xsd](http://www.tei-c.org/release/xml/tei/custom/schema/xsd/tei_all.xsd). The code has been tested on [eXist](http://exist-db.org/exist/apps/homepage/index.html). The formatting of the ouput comes from a slightly modified version of the [Bootstrap Basic Template](http://getbootstrap.com/getting-started/).

###Installation

Create a collection "/db/apps/teiDocs" at eXist and add "teiDocs.xqm" and "tei_all.xsd" to the collection. You can invoke the module from eXide with the following function:

```xquery
xquery version "3.0";

import module namespace teiDoc = "http://nullable.net/teiDocs" at "/db/apps/teiDocs/teiDocs.xqm";

declare option exist:serialize "method=html5 media-type=text/html";

teiDoc:generate-docs("YOUR_TEI_FILE")
```

###Credits

Created during [Hack Nashville 5](http://hacknashville.com/) on May 2-4, 2014.
