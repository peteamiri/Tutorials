# Extensible Markup Language (XML)

## Sources

* [MSDN](https://docs.microsoft.com/en-us/previous-versions/aa468558(v=msdn.10))
* [XML Tutorials](https://etutorials.org/Misc/rss/Appendix+A.+The+XML+You+Need+for+RSS/A.2+Anatomy+of+an+XML+Document/)
* [W3School](https://www.w3schools.com/XML/xml_whatis.asp)


## Description

## History and Roots

The Extensible Markup Language (XML) is derived from the Standard Generalized Markup Language (SGML), and can be considered to be a meta-language: a language for defining markup languages.

SGML and XML are text-based formats that provide mechanisms for describing document structures using markup tags (words surrounded by '<' and '>'). Web developers may notice some similarity between HTML and XML, which is due to the fact that they are both derived from SGML.

XML is also suitable for describing structured data. Examples of structured data include information that is typically contained in spreadsheets, program configuration files, and network protocols.

XML is preferable to previous data formats because XML can easily represent both tabular data (such as relational data from a database or spreadsheets) and semi-structured data (such as a Web page or business document). Popular pre-existing formats such as comma separated value (CSV) files either work well for tabular data and handle semi-structured data poorly, or like RTF are too specialized for semi-structured text documents. This has led to the widespread adoption of XML as the lingua franca of information interchange.

Besides being able to represent both structured and semi-structured data, XML has a number of characteristics that have caused it to be widely adopted as a data representation format.

XML is extensible, platform-independent, and supports internationalization by being fully Unicode compliant. The fact that XML is a text-based format means that when the need arises, one can read and edit XML documents using standard text-editing tools.

XML is not tied to any programming language, operating system or software vendor. In fact, it is fairly straightforward to produce or consume XML using a variety of programming languages. Platform independence makes XML very useful as a means for achieving interoperability between different programming platforms and operating systems.

The benefits of exposing data as XML have been acknowledged by many, and have led to a proliferation of XML data sources. Business documents, databases and inter-business communication are all examples of information sources that are moving or have moved to using XML as a representation format.

## Characteristics

XML has the following characteristics

* XML is not tied to any programming language, operating system or software vendor.

## The Anatomy of an XML Document

Below is a sample XML document that represents a customer order for a music store. A point of note is how the document easily represents both the rigidly structured data that describes information about compact discs as well as the semi-structured data containing special instructions and comments about a specific customer.

     1	<?xml version="1.0" encoding="iso-8859-1" ?>
     2	<?xml-stylesheet href="orders.xsl"?>
     3
     4	<order id="ord123456">
     5	  <customer id="cust0921">
     6	    <first-name>Dare</first-name>
     7	    <last-name>Obasanjo</last-name>
     8	    <address>
     9	      <street>One Microsoft Way</street>
    10	      <city>Redmond</city>
    11	      <state>WA</state>
    12	      <zip>98052</zip>
    13	    </address>
    14	  </customer>
    15	  <items>
    16	    <compact-disc>
    17	      <price>16.95</price>
    18	      <artist>Nelly</artist>
    19	      <title>Nellyville</title>
    20	    </compact-disc>
    21	    <compact-disc>
    22	      <price>17.55</price>
    23	       <artist>Baby D</artist>
    24	       <title>Lil Chopper Toy</title>
    25	    </compact-disc>
    26	  </items>
    27
    28	  <!--  Always go the extra mile for the customer -->
    29	</order>
