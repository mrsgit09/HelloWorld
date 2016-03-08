**\[MS-ART\]: **

**Access Run Time Protocol**

**Intellectual Property Rights Notice for Open Specifications Documentation**

-   **Technical Documentation.** Microsoft publishes Open Specifications documentation for protocols, file formats, languages, standards as well as overviews of the interaction among each of these technologies.

-   **Copyrights**. This documentation is covered by Microsoft copyrights. Regardless of any other terms that are contained in the terms of use for the Microsoft website that hosts this documentation, you may make copies of it in order to develop implementations of the technologies described in the Open Specifications and may distribute portions of it in your implementations using these technologies or your documentation as necessary to properly document the implementation. You may also distribute in your implementation, with or without modification, any schema, IDL's, or code samples that are included in the documentation. This permission also applies to any documents that are referenced in the Open Specifications.

-   **No Trade Secrets**. Microsoft does not claim any trade secret rights in this documentation.

-   **Patents**. Microsoft has patents that may cover your implementations of the technologies described in the Open Specifications. Neither this notice nor Microsoft's delivery of the documentation grants any licenses under those or any other Microsoft patents. However, a given Open Specification may be covered by Microsoft [Open Specification Promise](http://go.microsoft.com/fwlink/?LinkId=214445) or the [Community Promise](http://go.microsoft.com/fwlink/?LinkId=214448). If you would prefer a written license, or if the technologies described in the Open Specifications are not covered by the Open Specifications Promise or Community Promise, as applicable, patent licenses are available by contacting <iplg@microsoft.com>.

-   **Trademarks**. The names of companies and products contained in this documentation may be covered by trademarks or similar intellectual property rights. This notice does not grant any licenses under those rights. For a list of Microsoft trademarks, visit [www.microsoft.com/trademarks](http://www.microsoft.com/trademarks).

-   **Fictitious Names**. The example companies, organizations, products, domain names, e-mail addresses, logos, people, places, and events depicted in this documentation are fictitious. No association with any real company, organization, product, domain name, email address, logo, person, place, or event is intended or should be inferred.

**Reservation of Rights**. All other rights are reserved, and this notice does not grant any rights other than specifically described above, whether by implication, estoppel, or otherwise.

**Tools**. The Open Specifications do not require the use of Microsoft programming tools or programming environments in order for you to develop an implementation. If you have access to Microsoft programming tools and environments you are free to take advantage of them. Certain Open Specifications are intended for use in conjunction with publicly available standard specifications and network programming art, and assumes that the reader either is familiar with the aforementioned material or has immediate access to it.

**Revision Summary**

| Date       | Revision History | Revision Class | Comments                                                                     |
|------------|------------------|----------------|------------------------------------------------------------------------------|
| 1/20/2012  | 0.1              | New            | Released new document.                                                       |
| 4/11/2012  | 0.1              | None           | No changes to the meaning, language, or formatting of the technical content. |
| 7/16/2012  | 0.1              | None           | No changes to the meaning, language, or formatting of the technical content. |
| 9/12/2012  | 0.1              | None           | No changes to the meaning, language, or formatting of the technical content. |
| 10/8/2012  | 1.0              | Major          | Significantly changed the technical content.                                 |
| 2/11/2013  | 2.0              | Major          | Significantly changed the technical content.                                 |
| 7/30/2013  | 2.0              | None           | No changes to the meaning, language, or formatting of the technical content. |
| 11/18/2013 | 2.0              | None           | No changes to the meaning, language, or formatting of the technical content. |
| 2/10/2014  | 2.0              | None           | No changes to the meaning, language, or formatting of the technical content. |
| 4/30/2014  | 2.0              | None           | No changes to the meaning, language, or formatting of the technical content. |
| 7/31/2014  | 2.0              | None           | No changes to the meaning, language, or formatting of the technical content. |
| 10/30/2014 | 2.0              | None           | No changes to the meaning, language, or formatting of the technical content. |
| 2/26/2016  | 3.0              | Major          | Significantly changed the technical content.                                 |

Table of Contents

[1 Introduction 5](#_Toc445116526)

[1.1 Glossary 5](#_Toc445116527)

[1.2 References 6](#_Toc445116528)

[1.2.1 Normative References 6](#_Toc445116529)

[1.2.2 Informative References 6](#_Toc445116530)

[1.3 Overview 7](#_Toc445116531)

[1.4 Relationship to Other Protocols 7](#_Toc445116532)

[1.5 Prerequisites/Preconditions 7](#_Toc445116533)

[1.6 Applicability Statement 7](#_Toc445116534)

[1.7 Versioning and Capability Negotiation 8](#_Toc445116535)

[1.8 Vendor-Extensible Fields 8](#_Toc445116536)

[1.9 Standards Assignments 8](#_Toc445116537)

[2 Messages 9](#_Toc445116538)

[2.1 Transport 9](#_Toc445116539)

[2.2 Message Syntax 9](#_Toc445116540)

[2.2.1 Complex Types 10](#_Toc445116541)

[2.2.1.1 ClientMessage 11](#_Toc445116542)

[2.2.1.2 CurrentUserPermissions 11](#_Toc445116543)

[2.2.1.3 FieldSchema 12](#_Toc445116544)

[2.2.1.4 FilterInfo 13](#_Toc445116545)

[2.2.1.5 FixupRecord 13](#_Toc445116546)

[2.2.1.6 FormatInfo 14](#_Toc445116547)

[2.2.1.7 PagingInfo 15](#_Toc445116548)

[2.2.1.8 ParameterValue 17](#_Toc445116549)

[2.2.1.9 RecordSet 17](#_Toc445116550)

[2.2.1.10 ServiceError 18](#_Toc445116551)

[2.2.1.11 ServiceResult 19](#_Toc445116552)

[2.2.1.12 SharedDataBaseInfo 19](#_Toc445116553)

[2.2.1.13 UpdateRecord 22](#_Toc445116554)

[2.2.2 Simple Types 22](#_Toc445116555)

[2.2.2.1 CacheCommands 23](#_Toc445116556)

[2.2.2.2 ClientMessageID 23](#_Toc445116557)

[2.2.2.3 MessageSeverity 25](#_Toc445116558)

[3 Protocol Details 27](#_Toc445116559)

[3.1 Server Details 27](#_Toc445116560)

[3.1.1 Abstract Data Model 27](#_Toc445116561)

[3.1.2 Timers 27](#_Toc445116562)

[3.1.3 Initialization 27](#_Toc445116563)

[3.1.4 Higher-Layer Triggered Events 27](#_Toc445116564)

[3.1.5 Message Processing Events and Sequencing Rules 27](#_Toc445116565)

[3.1.5.1 AccessPortal 28](#_Toc445116566)

[3.1.5.1.1 GetData 28](#_Toc445116567)

[3.1.5.1.1.1 Request Body 29](#_Toc445116568)

[3.1.5.1.1.2 Response Body 29](#_Toc445116569)

[3.1.5.1.1.3 Processing Details 29](#_Toc445116570)

[3.1.5.1.2 InsertRecords 30](#_Toc445116571)

[3.1.5.1.2.1 Request Body 30](#_Toc445116572)

[3.1.5.1.2.2 Response Body 31](#_Toc445116573)

[3.1.5.1.2.3 Processing Details 31](#_Toc445116574)

[3.1.5.1.3 UpdateRecords 32](#_Toc445116575)

[3.1.5.1.3.1 Request Body 32](#_Toc445116576)

[3.1.5.1.3.2 Response Body 33](#_Toc445116577)

[3.1.5.1.3.3 Processing Details 33](#_Toc445116578)

[3.1.5.1.4 DeleteRecords 34](#_Toc445116579)

[3.1.5.1.4.1 Request Body 34](#_Toc445116580)

[3.1.5.1.4.2 Response Body 34](#_Toc445116581)

[3.1.5.1.4.3 Processing Details 35](#_Toc445116582)

[3.1.5.1.5 GetDistinctValues 35](#_Toc445116583)

[3.1.5.1.5.1 Request Body 35](#_Toc445116584)

[3.1.5.1.5.2 Response Body 36](#_Toc445116585)

[3.1.5.1.5.3 Processing Details 36](#_Toc445116586)

[3.1.5.1.6 FixupRow 36](#_Toc445116587)

[3.1.5.1.6.1 Request Body 37](#_Toc445116588)

[3.1.5.1.6.2 Response Body 37](#_Toc445116589)

[3.1.5.1.6.3 Processing Details 38](#_Toc445116590)

[3.1.5.1.7 GetSearchData 38](#_Toc445116591)

[3.1.5.1.7.1 Request Body 38](#_Toc445116592)

[3.1.5.1.7.2 Response Body 39](#_Toc445116593)

[3.1.5.1.7.3 Processing Details 39](#_Toc445116594)

[3.1.6 Timer Events 40](#_Toc445116595)

[3.1.6.1 Session Timeout 40](#_Toc445116596)

[3.1.7 Other Local Events 40](#_Toc445116597)

[4 Protocol Examples 41](#_Toc445116598)

[4.1 GetData Service Operation 41](#_Toc445116599)

[4.2 InsertRecords Service Operation 43](#_Toc445116600)

[4.3 UpdateRecords Service Operation 45](#_Toc445116601)

[4.4 DeleteRecords Service Operation 47](#_Toc445116602)

[5 Security 50](#_Toc445116603)

[5.1 Security Considerations for Implementers 50](#_Toc445116604)

[5.2 Index of Security Parameters 50](#_Toc445116605)

[6 Appendix A: Full JSON ABNF 51](#_Toc445116606)

[7 Appendix B: Product Behavior 57](#_Toc445116607)

[8 Change Tracking 58](#_Toc445116608)

[9 Index 60](#_Toc445116609)

<span id="section_fe694013d9d84727b4e6f88e417d4de3" class="anchor"><span id="_Toc445116526" class="anchor"></span></span>Introduction
=====================================================================================================================================

The Access Run Time Protocol enables a protocol client to read, insert, update or delete data in a [**database application**](#gt_ff8f9390-b8b7-4845-8735-09cf9080e263).

Sections 1.5, 1.8, 1.9, 2, and 3 of this specification are normative. All other sections and examples in this specification are informative.

<span id="section_46b952aeeb1043c7971ad5ab0a0386dc" class="anchor"><span id="_Toc445116527" class="anchor"></span></span>Glossary
---------------------------------------------------------------------------------------------------------------------------------

This document uses the following terms:

> <span id="gt_5038d42c-6611-4cfc-9c6a-d6a9d03a10e5" class="anchor"></span>**alert**: A message that is passed to a protocol client to notify it when specific criteria are met.
>
> <span id="gt_24ddbbb4-b79e-4419-96ec-0fdd229c9ebf" class="anchor"></span>**Augmented Backus-Naur Form (ABNF)**: A modified version of Backus-Naur Form (BNF), commonly used by Internet specifications. ABNF notation balances compactness and simplicity with reasonable representational power. ABNF differs from standard BNF in its definitions and uses of naming rules, repetition, alternatives, order-independence, and value ranges. For more information, see [\[RFC5234\]](http://go.microsoft.com/fwlink/?LinkId=123096).
>
> <span id="gt_81d81412-1575-4084-ba61-742de406b418" class="anchor"></span>**caption**: One or more characters that can be used as a label for display purposes or as an identifier.
>
> <span id="gt_ff8f9390-b8b7-4845-8735-09cf9080e263" class="anchor"></span>**database application**: A set of objects, including tables, queries, forms, reports, macros, and code modules, that are stored in a database structure.
>
> <span id="gt_f819dd42-7f44-4613-8231-d5ad47f2bbcc" class="anchor"></span>**field**: A discrete unit of a record that has a name, a data type, and a value.
>
> <span id="gt_bb52365c-d923-4f0a-ae73-707c31d99704" class="anchor"></span>**Help topic identifier**: A unique identifier for an article that contains Help content.
>
> <span id="gt_d72f1494-4917-4e9e-a9fd-b8f1b2758dcd" class="anchor"></span>**Hypertext Transfer Protocol (HTTP)**: An application-level protocol for distributed, collaborative, hypermedia information systems (text, graphic images, sound, video, and other multimedia files) on the World Wide Web.
>
> <span id="gt_9239bd88-9747-44a6-83a6-473f53f175a7" class="anchor"></span>**Hypertext Transfer Protocol Secure (HTTPS)**: An extension of HTTP that securely encrypts and decrypts web page requests. In some older protocols, "Hypertext Transfer Protocol over Secure Sockets Layer" is still used (Secure Sockets Layer has been deprecated). For more information, see [\[SSL3\]](http://go.microsoft.com/fwlink/?LinkId=90534) and [\[RFC5246\]](http://go.microsoft.com/fwlink/?LinkId=129803).
>
> <span id="gt_7c4f81c3-2e19-4c95-ab8d-45721da01d26" class="anchor"></span>**JavaScript Object Notation (JSON)**: A text-based, data interchange format that is used to transmit structured data, typically in Asynchronous JavaScript + XML (AJAX) web applications, as described in [\[RFC4627\]](http://go.microsoft.com/fwlink/?LinkId=140879). The JSON format is based on the structure of ECMAScript (Jscript, JavaScript) objects.
>
> <span id="gt_e4d8c530-39c1-4fc6-8ccc-8d51a221158d" class="anchor"></span>**primary key**: A field or set of fields that uniquely identifies each record in a table. A primary key cannot contain a null value.
>
> <span id="gt_dca3e776-890f-48c8-be62-094a5f2fcf71" class="anchor"></span>**record**: A group of related [**fields**](#gt_f819dd42-7f44-4613-8231-d5ad47f2bbcc), which are sometimes referred to as columns, of information that are treated as a unit. Also referred to as row.
>
> <span id="gt_a72572a2-726e-40e4-b9a4-e158bdacf720" class="anchor"></span>**Request-URI**: A [**URI**](#gt_e18af8e8-01d7-4f91-8a1e-0fb21b191f95) in an [**HTTP**](#gt_d72f1494-4917-4e9e-a9fd-b8f1b2758dcd) request message, as described in [\[RFC2616\]](http://go.microsoft.com/fwlink/?LinkId=90372).
>
> <span id="gt_c8a27238-8ccc-442b-9604-75f74d3e6b3d" class="anchor"></span>**result set**: A list of records that results from running a stored procedure or query, or applying a filter. The structure and content of the data in a result set varies according to the implementation.
>
> <span id="gt_a87817fc-9b18-49a1-925e-9be9e1d92665" class="anchor"></span>**row**: A collection of columns (1) that contains property values that describe a single item in a set of items that match the restriction (1) specified in a query.
>
> <span id="gt_0cd96b80-a737-4f06-bca4-cf9efb449d12" class="anchor"></span>**session**: A representation of application data in system memory. It is used to maintain state for application data that is being manipulated or monitored on a protocol server by a user.
>
> <span id="gt_95849ec1-2a77-48db-816f-187fdd7c992a" class="anchor"></span>**session identifier**: A key that enables an application to make reference to a session.
>
> <span id="gt_8abdc986-5679-42d9-ad76-b11eb5a0daba" class="anchor"></span>**site**: A group of related pages and data within a SharePoint site collection. The structure and content of a site is based on a site definition. Also referred to as SharePoint site and web site.
>
> <span id="gt_e18af8e8-01d7-4f91-8a1e-0fb21b191f95" class="anchor"></span>**Uniform Resource Identifier (URI)**: A string that identifies a resource. The URI is an addressing mechanism defined in Internet Engineering Task Force (IETF) Uniform Resource Identifier (URI): Generic Syntax [\[RFC3986\]](http://go.microsoft.com/fwlink/?LinkId=90453).
>
> <span id="gt_433a4fb7-ef84-46b0-ab65-905f5e3a80b1" class="anchor"></span>**Uniform Resource Locator (URL)**: A string of characters in a standardized format that identifies a document or resource on the World Wide Web. The format is as specified in [\[RFC1738\]](http://go.microsoft.com/fwlink/?LinkId=90287).
>
> **MAY, SHOULD, MUST, SHOULD NOT, MUST NOT:** These terms (in all caps) are used as defined in [\[RFC2119\]](http://go.microsoft.com/fwlink/?LinkId=90317). All statements of optional behavior use either MAY, SHOULD, or SHOULD NOT.

<span id="section_e94fd3f6ddcd4ff2a88f0d7357508ea0" class="anchor"><span id="_Toc445116528" class="anchor"></span></span>References
-----------------------------------------------------------------------------------------------------------------------------------

Links to a document in the Microsoft Open Specifications library point to the correct section in the most recently published version of the referenced document. However, because individual documents in the library are not updated at the same time, the section numbers in the documents may not match. You can confirm the correct section numbering by checking the [Errata](http://msdn.microsoft.com/en-us/library/dn781092.aspx).

### <span id="section_30be68b021e44bb5a9be36fe35695688" class="anchor"><span id="_Toc445116529" class="anchor"></span></span>Normative References

We conduct frequent surveys of the normative references to assure their continued availability. If you have any issue with finding a normative reference, please contact <dochelp@microsoft.com>. We will assist you in finding the relevant information.

\[MS-ADR\] Microsoft Corporation, "[Access Services Data Run Time Protocol](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa)".

\[MS-AXL2\] Microsoft Corporation, "[Access Application Transfer Data Structure Version 2](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-AXL2%5d.pdf#Section_208c003b477b4743b29b6a8c92fa46ad)".

\[RFC2119\] Bradner, S., "Key words for use in RFCs to Indicate Requirement Levels", BCP 14, RFC 2119, March 1997, [http://www.rfc-editor.org/rfc/rfc2119.txt](http://go.microsoft.com/fwlink/?LinkId=90317)

\[RFC2616\] Fielding, R., Gettys, J., Mogul, J., et al., "Hypertext Transfer Protocol -- HTTP/1.1", RFC 2616, June 1999, [http://www.rfc-editor.org/rfc/rfc2616.txt](http://go.microsoft.com/fwlink/?LinkId=90372)

\[RFC2818\] Rescorla, E., "HTTP Over TLS", RFC 2818, May 2000, [http://www.rfc-editor.org/rfc/rfc2818.txt](http://go.microsoft.com/fwlink/?LinkId=90383)

\[RFC4627\] Crockford, D., "The application/json Media Type for JavaScript Object Notation (JSON)", RFC 4627, July 2006, [http://www.ietf.org/rfc/rfc4627.txt](http://go.microsoft.com/fwlink/?LinkId=140879)

\[RFC5234\] Crocker, D., Ed., and Overell, P., "Augmented BNF for Syntax Specifications: ABNF", STD 68, RFC 5234, January 2008, [http://www.rfc-editor.org/rfc/rfc5234.txt](http://go.microsoft.com/fwlink/?LinkId=123096)

### <span id="section_8da12ec75c284eb29d53346df1239938" class="anchor"><span id="_Toc445116530" class="anchor"></span></span>Informative References

None.

<span id="section_5282b034621d4d659f990994de1fd9ed" class="anchor"><span id="_Toc445116531" class="anchor"></span></span>Overview
---------------------------------------------------------------------------------------------------------------------------------

This protocol is used for manipulating data maintained by a protocol server. Communication is always initiated by the protocol client using different operations, the functionality of which is outlined following.

-   Inserting, reading, updating and deleting data from the database application.

-   Filtering, sorting data while reading it from the database application.

-   Modeling hypothetical updates on the protocol server.

-   Reading distinct values for a certain [**field**](#gt_f819dd42-7f44-4613-8231-d5ad47f2bbcc) in a [**result set**](#gt_c8a27238-8ccc-442b-9604-75f74d3e6b3d).

A typical scenario for this protocol is opening a result set and updating or deleting data.

<span id="section_77723f42041e40e9bb970755c46eb887" class="anchor"><span id="_Toc445116532" class="anchor"></span></span>Relationship to Other Protocols
--------------------------------------------------------------------------------------------------------------------------------------------------------

This protocol enables a protocol client to send a request that calls methods and accesses data on a protocol server, and then receive a corresponding response from the protocol server. This protocol depends on other structures and protocols to transport messages. Applications are layered on top of this protocol and they interact directly with this protocol specification.

The messages that are sent from the protocol client to the protocol server are formatted as [**JSON**](#gt_7c4f81c3-2e19-4c95-ab8d-45721da01d26). It transmits those messages by using [**HTTP**](#gt_d72f1494-4917-4e9e-a9fd-b8f1b2758dcd), as described in [\[RFC2616\]](http://go.microsoft.com/fwlink/?LinkId=90372), or [**HTTPS**](#gt_9239bd88-9747-44a6-83a6-473f53f175a7), as described in [\[RFC2818\]](http://go.microsoft.com/fwlink/?LinkId=90383). Responses from the protocol server are formatted as JSON.

<embed src="./media/image1.bin" width="484" height="200" />

Figure This protocol in relation to other protocols

<span id="section_ffd0658f6a9a483aae65d8aa70e127a2" class="anchor"><span id="_Toc445116533" class="anchor"></span></span>Prerequisites/Preconditions
----------------------------------------------------------------------------------------------------------------------------------------------------

This protocol operates against a protocol server that is configured to listen for HTTP or HTTPS requests and a protocol client that knows the [**Request-URI**](#gt_a72572a2-726e-40e4-b9a4-e158bdacf720) of the protocol server.

<span id="section_8fb8a66e01244c06a8d474ed16d0130e" class="anchor"><span id="_Toc445116534" class="anchor"></span></span>Applicability Statement
------------------------------------------------------------------------------------------------------------------------------------------------

This protocol is applicable for the following scenarios:

-   Inserting, reading, updating, or deleting data from the database application.

-   Retrieving data from the database application in **Pages** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)). This applies only if the number of [**records**](#gt_dca3e776-890f-48c8-be62-094a5f2fcf71) exceeds a threshold specified by the protocol server.

-   Filtering data by retrieving only the data matching given restrictions.

-   Sorting data retrieved from the database application

-   Retrieving only distinct values for certain fields in the result set from the database application

-   Modeling hypothetical updates on the protocol server.

This protocol is not applicable for the following scenarios:

-   Creating, updating or deleting objects on the database application.

-   Acting as a data transfer channel between protocol client and protocol server. Instead the data sent to protocol client is intended to be rendered for end user viewing.

    1.  <span id="section_c82d8de0685f411987e9a2ed1b1184d7" class="anchor"><span id="_Toc445116535" class="anchor"></span></span>Versioning and Capability Negotiation
        --------------------------------------------------------------------------------------------------------------------------------------------------------------

This document covers versioning issues in the area of supported transports. This protocol can use HTTP or HTTPS as a transport. For more information, see Transport (section [2.1](#Section_0d6e56cfd12f40e4a67cfcdde6ba3f2c)).

<span id="section_7493a5f5ec934fd69048b12250b58d83" class="anchor"><span id="_Toc445116536" class="anchor"></span></span>Vendor-Extensible Fields
-------------------------------------------------------------------------------------------------------------------------------------------------

None.

<span id="section_4598ffb2570849f0be8451a17b822a04" class="anchor"><span id="_Toc445116537" class="anchor"></span></span>Standards Assignments
----------------------------------------------------------------------------------------------------------------------------------------------

None.

1.  <span id="section_4b896e804893444699964d525edc79e5" class="anchor"><span id="_Toc445116538" class="anchor"></span></span>Messages
    =================================================================================================================================

    1.  <span id="section_0d6e56cfd12f40e4a67cfcdde6ba3f2c" class="anchor"><span id="_Toc445116539" class="anchor"></span></span>Transport
        ----------------------------------------------------------------------------------------------------------------------------------

Protocol servers MUST support HTTP, as specified in [\[RFC2616\]](http://go.microsoft.com/fwlink/?LinkId=90372). Protocol servers SHOULD also additionally support HTTPS, as specified in [\[RFC2818\]](http://go.microsoft.com/fwlink/?LinkId=90383), to help secure connections with protocol clients.

Protocol messages MUST be formatted as JSON as specified in [\[RFC4627\]](http://go.microsoft.com/fwlink/?LinkId=140879). Protocol clients MUST use the **GET** (\[RFC2616\] section 9.3) or **POST** (\[RFC2616\] section 9.5) method to send messages to the protocol servers.

<span id="section_1e211795f3c0470bbe90757a76a3f05c" class="anchor"><span id="_Toc445116540" class="anchor"></span></span>Message Syntax
---------------------------------------------------------------------------------------------------------------------------------------

This section contains common definitions used by this protocol specification. The syntax of the definitions uses JavaScript Object Notation (JSON), as specified in [\[RFC4627\]](http://go.microsoft.com/fwlink/?LinkId=140879), and the common JSON in [**ABNF**](#gt_24ddbbb4-b79e-4419-96ec-0fdd229c9ebf), as specified by [\[RFC5234\]](http://go.microsoft.com/fwlink/?LinkId=123096).

1.  json-begin-array = json-whitespace %x5B json-whitespace ; \[ left square bracket

    json-begin-object = json-whitespace %x7B json-whitespace ; { left curly bracket

    json-end-array = json-whitespace %x5D json-whitespace ; \] right square bracket

    json-end-object = json-whitespace %x7D json-whitespace ; } right curly bracket

    json-name-separator = json-whitespace %x3A json-whitespace ; : colon

    json-value-separator = json-whitespace %x2C json-whitespace ; , comma

    json-whitespace = \*(

    %x20 / ; Space

    %x09 / ; Horizontal tab

    %x0A / ; Line feed or New line

    %x0D ; Carriage return

    )

    json-value = json-false / json-null / json-true / json-object / json-array / json-number / json-string

    json-false = %x66.61.6c.73.65 ; false

    json-null = %x6e.75.6c.6c ; null

    json-true = %x74.72.75.65 ; true

    json-bool = json-false / json-true

    json-object = json-begin-object \[json-member \*( json-value-separator json-member ) \] json-end-object

    json-member = json-string json-name-separator json-value

    json-number = \[ json-minus \] json-int \[ json-frac \] \[ json-exp \]

    json-decimal-point = %x2E ; .

    json-digit1-9 = %x31-39 ; 1-9

    json-e = %x65 / %x45 ; e E

    json-exp = json-e \[ json-minus / json-plus \] 1\*DIGIT

    json-frac = json-decimal-point 1\*DIGIT

    json-int = json-zero / ( json-digit1-9 \*DIGIT )

    json-minus = %x2D ; -

    json-plus = %x2B ; +

    json-zero = %x30 ; 0

    json-array = json-begin-array \[ json-value \*( json-value-separator json-value ) \] json-end-array

    json-string = json-quotation-mark \*json-char json-quotation-mark

    json-char = json-unescaped /

    json-escape (

    %x22 / ; " quotation mark U+0022

    %x5C / ; \\ reverse solidus U+005C

    %x2F / ; / solidus U+002F

    %x62 / ; b backspace U+0008

    %x66 / ; f form feed U+000C

    %x6E / ; n line feed U+000A

    %x72 / ; r carriage return U+000D

    %x74 / ; t tab U+0009

    %x75 4HEXDIG ) ; uXXXX U+XXXX

    json-escape = %x5C ; \\

    json-quotation-mark = %x22 ; "

    json-unescaped = %x20-21 / %x23-5B / %x5D-10FFFF

The following table defines the common JSON types used in this document.

| Common Type                     | Value                                                                                                              |
|---------------------------------|--------------------------------------------------------------------------------------------------------------------|
| JsonAnyValue                    | 1.  json-value                                                                                                     |
| JsonStringValue                 | 1.  json-string                                                                                                    |
| JsonArrayOfAnyType              | 1.  json-array                                                                                                     |
| JsonArrayOfString               | 1.  json-begin-array \[ json-string \*( json-value-separator json-string) \] json-end-array                        |
| JsonArrayOfInt                  | 1.  json-begin-array \[ json-int \*( json-value-separator json-int) \] json-end-array                              |
| JsonArrayOfArrayOfAnyType       | 1.  json-begin-array \[JsonArrayOfAnyType \*( json-value-separator JsonArrayOfAnyType) \] json-end-array           |
| JsonArrayOfArrayOfString        | 1.  json-begin-array \[JsonArrayOfString \*( json-value-separator JsonArrayOfString) \] json-end-array             |
| JsonArrayOfArrayOfArrayOfString | 1.  json-begin-array \[JsonArrayOfArrayOfString \*( json-value-separator JsonArrayOfArrayString) \] json-end-array |

### <span id="section_5ef9e8f98cc844158994cb7c5d6f2b1e" class="anchor"><span id="_Toc445116541" class="anchor"></span></span>Complex Types

The following table summarizes the set of common JSON complex type definitions defined by this specification. JSON complex type definitions that are specific to a particular operation are described with the operation.

| Complex Type       | Description                                                                                                                                                                                                                                                                                                         |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ClientMessage      | Specifies an error or informative message to return fro1m the protocol server. See section [2.2.1.1](#Section_a136d4ff75eb4eba8ff8313e032c273b) for more details.                                                                                                                                                   |
| FieldSchema        | Specifies all metadata information about a field of a **Source** ([\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.1.1). See section [2.2.1.3](#Section_30acf56e4f464584809b8655020c0183) for more details.                      |
| FilterInfo         | Specifies how to filter a result set. See section [2.2.1.4](#Section_e6bd0749245149f3afa9c95835e6f244) for more details.                                                                                                                                                                                            |
| FixupRecord        | Specifies the values for the fields of the records that are to be used for the modeling a hypothetical update on the protocol server. See section [2.2.1.5](#Section_bccb561364bb453ca501aea0124333f7) for more details.                                                                                            |
| FormatInfo         | Specifies all metadata information about a field of a **Source** (\[MS-ADR\] section 3.1.1.1).See section [2.2.1.6](#Section_fd0bb464b85f4f9c9954afa33cf0a59e) for more details.                                                                                                                                    |
| PagingInfo         | Specifies which records of data from the **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)) are requested by the protocol client. See section [2.2.1.7](#Section_e8004e1c5c2e4159a46b84caaf473c5f) for more details.                                                                           |
| ParameterValue     | Specifies a container for the name of a **CT\_Parameter** ([\[MS-AXL2\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-AXL2%5d.pdf#Section_208c003b477b4743b29b6a8c92fa46ad) section 2.2.3.12) and its associated value. See section [2.2.1.8](#Section_90e96692144d4c71bcb735d2d5672fe6) for more details. |
| RecordSet          | A complex type that is output by all the protocol operations. See section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b) for more details.                                                                                                                                                                    |
| ServiceError       | Specifies information about an alert (2) sent from protocol server to the protocol client. See section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f) for more details.                                                                                                                                      |
| ServiceResult      | Specifies the result of the protocol operation. See section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd) for more details.                                                                                                                                                                                 |
| SharedDataBaseInfo | Specifies information about the **Source** (section 3.1.1) on which protocol operations are to be performed. See section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc) for more details.                                                                                                                    |
| UpdateRecord       | Specifies information about original values and new values of fields in a record that is to be inserted or updated in database application. See section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93) for more details.                                                                                     |

#### <span id="section_a136d4ff75eb4eba8ff8313e032c273b" class="anchor"><span id="_Toc445116542" class="anchor"></span></span>ClientMessage

The meaning of **ClientMessage** is specified by [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 2.2.4.24. The format of the **ClientMessage** complex type is specified by this section. The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c).

1.  ClientMessage = json-object

    MessageID = json-quotation-mark "MessageID" json-quotation-mark json-name-separator  ClientMessageID

    Context =  json-quotation-mark "Context" json-quotation-mark json-name-separator  JsonArrayOfAnyType

The meanings of **Context** and **MessageID** are specified by \[MS-ADR\] section 2.2.4.24.

**ClientMessage** MUST contain exactly two **json-member** instances, and each instance MUST be different. Each instance MUST be one of the following: **Context** and **MessageID**.

#### <span id="section_4afce5d527f24602806f5c2fe43270b9" class="anchor"><span id="_Toc445116543" class="anchor"></span></span>CurrentUserPermissions

The meaning of **CurrentUserPermissions** is specified by [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.4.45.3.11. The format of the **CurrentUserPermissions** complex type is specified by this section. The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c).

1.  CurrentUserPermissions = json-object

    Read = json-quotation-mark "Read" json-quotation-mark json-name-separator  json-bool

    Write = json-quotation-mark "Write" json-quotation-mark json-name-separator  json-bool

    Author = json-quotation-mark "Author" json-quotation-mark json-name-separator  json-bool

    IsAuthenticated = json-quotation-mark "IsAuthenticated" json-quotation-mark json-name-separator  json-bool

The meanings of **Read**, **Write**, **Author**, and **IsAuthenticated** are specified by \[MS-ADR\] section 3.1.4.45.3.11.

**CurrentUserPermissions** MUST contain exactly four **json-member** instances, and each instance MUST be different. Each instance MUST be one of the following: **Read**, **Write**, **Author**, and **IsAuthenticated.**

#### <span id="section_30acf56e4f464584809b8655020c0183" class="anchor"><span id="_Toc445116544" class="anchor"></span></span>FieldSchema

The meaning of **FieldSchema** is specified by [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 2.2.4.25. The format of the **FieldSchema** complex type is specified by this section. The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c).

1.  FieldSchema = json-object

    ColumnName = json-quotation-mark "ColumnName" json-quotation-mark json-name-separator json-string

    DataType = json-quotation-mark " DataType" json-quotation-mark json-name-separator json-string

    DefaultValue = json-quotation-mark "DefaultValue" json-quotation-mark json-name-separator json-string

    IsKey = json-quotation-mark "IsKey" json-quotation-mark json-name-separator json-bool

    Required = json-quotation-mark "Required" json-quotation-mark json-name-separator json-bool

    ReadOnly = json-quotation-mark " ReadOnly" json-quotation-mark json-name-separator json-bool

    MaxLength = json-quotation-mark "MaxLength" json-quotation-mark json-name-separator json-int

    DefaultExpression = json-quotation-mark "DefaultExpression" json-quotation-mark json-name-separator json-string

    ValidationScript = json-quotation-mark "ValidationScript" json-quotation-mark json-name-separator  json-string

    ValidationMessage = json-quotation-mark "ValidationMessage" json-quotation-mark json-name-separator ClientMessage

    KeyIndex = json-quotation-mark "KeyIndex" json-quotation-mark json-name-separator json-int

    SourceObject = json-quotation-mark "SourceObject" json-quotation-mark json-name-separator json-string

    DependentFields = json-quotation-mark "DependentFields" json-quotation-mark json-name-separator JsonArrayOfInt

    AllowMultipleValues = json-quotation-mark "AllowMultipleValues" json-quotation-mark json-name-separator json-bool

    FormatString = json-quotation-mark "FormatString" json-quotation-mark json-name-separator json-string

    CurrencySymbol = json-quotation-mark "CurrencySymbol" json-quotation-mark json-name-separator json-string

    DecimalPlaces = json-quotation-mark "DecimalPlaces" json-quotation-mark json-name-separator json-int

    TextType = json-quotation-mark "TextType" json-quotation-mark json-name-separator json-string

    IsTableQueryLookup = json-quotation-mark "IsTableQueryLookup" json-quotation-mark json-name-separator json-bool

    LookupSource = json-quotation-mark "LookupSource" json-quotation-mark json-name-separator json-string

    LookupBoundField = json-quotation-mark "LookupBoundField" json-quotation-mark json-name-separator json-string

    LookupDisplayField = json-quotation-mark "LookupDisplayField" json-quotation-mark json-name-separator json-string

The meanings of **ColumnName**, **DataType**, **DefaultValue**, **IsKey**, **Required**, **ReadOnly**, **MaxLength**, **DefaultExpression**, **ValidationScript**, **ValidationMessage**, **KeyIndex**, **SourceObject**, **DependentFields**, **AllowMultipleValues**, **FormatString**, **CurrencySymbol**, **DecimalPlaces**, **TextType**, **IsTableQueryLookup**, **LookupSource**, **LookupBoundField**, and **LookupDisplayField** are specified by \[MS-ADR\] section 2.2.4.25.

**FieldSchema** MUST contain at least one and no more than twenty two **json-member** instances, and each instance MUST be different. Each instance MUST be one of the following: **ColumnName**, **DataType**, **DefaultValue**, **IsKey**, **Required**, **ReadOnly**, **MaxLength**, **DefaultExpression**, **ValidationScript**, **ValidationMessage**, **KeyIndex**, **SourceObject**, **DependentFields**, **AllowMultipleValues**, **FormatString**, **CurrencySymbol**, **DecimalPlaces**, **TextType**, **IsTableQueryLookup**, **LookupSource**, **LookupBoundField**, and **LookupDisplayField**.

#### <span id="section_e6bd0749245149f3afa9c95835e6f244" class="anchor"><span id="_Toc445116545" class="anchor"></span></span>FilterInfo

The meaning of **FilterInfo** is specified by [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 2.2.4.10. The format of the **FilterInfo** complex type is specified by this section. The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c).

1.  FilterInfo = json-object

    Culture = json-quotation-mark "Culture" json-quotation-mark json-name-separator  json-string

    Expression =  json-quotation-mark "Expression" json-quotation-mark json-name-separator  json-string

    Fields = json-quotation-mark "Fields" json-quotation-mark json-name-separator  JsonArrayOfStrings

    Text = json-quotation-mark "Text" json-quotation-mark json-name-separator json-string

The meanings of **Culture**, **Expression**, **Fields**, and **Text** are specified by \[MS-ADR\] section 2.2.4.10.

**FilterInfo** MUST contain at least one and no more than four **json-member** instances, and each instance MUST be different. Each instance MUST be one of the following: **Culture**, **Expression**, **Fields**, and **Text**. If one of the **json-member** instances is **Text**, then an instance of **Fields** and an instance of **Culture** MUST also be present.

#### <span id="section_bccb561364bb453ca501aea0124333f7" class="anchor"><span id="_Toc445116546" class="anchor"></span></span>FixupRecord

The **FixupRecord** type specifies the values for the fields of **Updatable Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)) which are used for modeling a hypothetical update on the protocol server. These values are only used for the hypothetical update, and are not updated in the database application.

The **FixupRecord** type is an input for the **FixupRow** operation (section [3.1.5.1.6](#Section_05532d6eb25e46379a55284b41c96fc2)).

The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c) and applies to the **FixupRecord**, unless extended or overridden by an operation specification.

1.  FixupRecord = json-object

    Key = json-quotation-mark "Key" json-quotation-mark json-name-separator json-string

    SupportingFieldIndexes = json-quotation-mark "SupportingFieldIndexes" json-quotation-mark json-name-separator JsonArrayOfInt

    SupportingFieldValues = json-quotation-mark "SupportingFieldValues" json-quotation-mark json-name-separator JsonArrayOfString

**FixupRecord** MUST contain three **json-member** instances, and each instance MUST be different. Each instance MUST be one of the following: **Key**, **SupportingFieldIndexes** and **SupportingFieldValues**.

**Key:** A **json-string** (section 2.2) that specifies a value that uniquely identifies the record on which a **FixupRow** operation (section 3.1.5.1.6) is to be performed. MUST be present. MUST NOT be **json-null**.

**SupportingFieldIndexes:** A **JsonArrayOfInt** (section 2.2), that specifies the indexes of the fields whose values are used for performing **FixupRow** operation. MUST be present. MUST have at least one element.

**SupportingFieldValues:** A **JsonArrayOfString** (section 2.2) that specifies the values of **SupportingFieldIndexes**. MUST be present. MUST have at least one element.

#### <span id="section_fd0bb464b85f4f9c9954afa33cf0a59e" class="anchor"><span id="_Toc445116547" class="anchor"></span></span>FormatInfo

The **FormatInfo** complex type specifies the format for a field in a **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)). The format is used by the protocol server to verify the value of the field sent by the protocol client and also to convert the value of field to its format before returning the value to the protocol client.

The **FormatInfo** complex type is an input as well as output used by some protocol operations.

The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c) and applies to the **FormatInfo**, unless extended or overridden by an operation specification.

1.  FormatInfo = json-object

    Currency = json-quotation-mark "Currency" json-quotation-mark json-name-separator json-string

    Format = json-quotation-mark "Format" json-quotation-mark json-name-separator json-string

    Precision = json-quotation-mark "Precision" json-quotation-mark json-name-separator json-int

**FormatInfo** MUST contain three **json-member** instances, and each instance MUST be different. Each instance MUST be one of the following: **Currency**, **Format**, and **Precision**.

**Currency:** A **json-string** (section 2.2) that specifies the currency symbol for the value of a field of a **Source** (section 3.1.1) in the database application. MUST be set to **json-null** (section 2.2) when the **Format** of the value of the field is not "currency".

**Format:** A **json-string** (section 2.2) that specifies the format for the value of a field of a **Source** (section 3.1.1) in the database application. MUST either be **json-null** (section 2.2) or MUST have one of the following values.

| Value            | Meaning                                                                      |
|------------------|------------------------------------------------------------------------------|
| "general date"   | The field is formatted as general date. For example, 01/02/2011 01:20:30 PM. |
| "long date"      | The field is formatted as long date. For example, Monday, Jan 01, 2011.      |
| "short date"     | The field is formatted as short date. For example, 01/01/11.                 |
| "long time"      | The field is formatted as long time. For example, 5:34:45 PM.                |
| "medium time"    | The field is formatted as medium time. For example, 5:34.                    |
| "short time"     | The field is formatted as short time. For example, 17.                       |
| "general number" | The number format is general. For example, 123,456.                          |
| "standard"       | The number format applied is standard. For example, 1234,567.89.             |
| "fixed"          | The number format applied is fixed. For example, 1234.56.                    |
| "scientific"     | The number format applied is scientific. For example, 123E+03.               |
| "percent"        | The number format applied is percentage. For example, 12.3%.                 |
| "currency"       | The number format applied is currency. For example, $12.34.                  |

**Precision:** A **json-int** (section 2.2) that specifies the maximum number of digits present after the decimal point in the value of a field of a **Source** (section 3.1.1) in the database application. MUST be a number between 0 and 15 and MUST only be present when **Format** is one of the following:

-   "general number"

-   "standard"

-   "fixed"

-   "scientific"

-   "percent"

-   "currency"

    1.  #### <span id="section_e8004e1c5c2e4159a46b84caaf473c5f" class="anchor"><span id="_Toc445116548" class="anchor"></span></span>PagingInfo

The **PagingInfo** complex type specifies which **Page** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)) of data from the cached result set or from the **Source** (section 3.1.1) is requested by the protocol client.

The **PagingInfo** complex type is used as an input as well as output by the some protocol operations.

The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c), and applies to the **PagingInfo** complex type unless extended or overridden by an operation specification.

1.  PagingInfo = json-object

    FirstRow = json-quotation-mark "FirstRow" json-quotation-mark json-name-separator json-int

    PageSize = json-quotation-mark "PageSize" json-quotation-mark json-name-separator json-int

    Moniker = json-quotation-mark "Moniker" json-quotation-mark json-name-separator (json-string / json-null)

    UseCache = json-quotation-mark "UseCache" json-quotation-mark json-name-separator json-bool

    CacheCommands = json-quotation-mark "CacheCommands" json-quotation-mark json-name-separator CacheCommands

    SortExpression = json-quotation-mark "SortExpression" json-quotation-mark json-name-separator json-string

    Filter = json-quotation-mark "Filter" json-quotation-mark json-name-separator FilterInfo

    TotalRows = json-quotation-mark "TotalRows" json-quotation-mark json-name-separator json-int

    SessionId = json-quotation-mark "SessionId" json-quotation-mark json-name-separator json-string

    RetrieveExactRowCount = json-quotation-mark "RetrieveExactRowCount" json-quotation-mark json-name-separator json-bool

    RowKey = json-quotation-mark "RowKey" json-quotation-mark json-name-separator json-int

**PagingInfo** MUST contain at least one and no more than nine **json-member** instances, and each instance MUST be different. Each instance MUST be one of the following: **CacheCommands**, **Filter**, **FirstRow**, **Moniker**, **PageSize**, **SessionId**, **SortExpression**, **TotalRows**, or **UseCache**.

**CacheCommands:** A **CacheCommands** (section [2.2.2.1](#Section_9967041420a644f39788c2352f30810c)) that specifies the operations to perform on the result set.

**Filter:** A **FilterInfo** (section [2.2.1.4](#Section_e6bd0749245149f3afa9c95835e6f244)) that specifies how to filter the result set.

**FirstRow:** A **json-int** (section 2.2) that specifies the index of the first record to return from the **Source** (section 3.1.1) specified by the **SelectCommand** element of the **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)).

-   MUST be present.

-   MUST be non-negative.

-   MUST be less than total records in **Source**.

**Moniker:** A **json-string** (section 2.2) that specifies the identifier for a result set that was specified by the protocol client. If a **Moniker** is specified in the [**session**](#gt_0cd96b80-a737-4f06-bca4-cf9efb449d12) then it MUST be used as the **moniker** element for the input to all **GetData** service operations (section [3.1.5.1.1](#Section_8e0492c58cb4494cb22457ca68e5386f)) within the same session.

**PageSize:** A **json-int** (section 2.2) that specifies the maximum number of records to return. MUST be non-negative.

**SessionId:** A **SessionIdentifier**, as specified by [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.1.2, that specifies a unique identifier for the current session that was previously received from the protocol server in the response of the first **GetData** service operation (section 3.1.5.1.1).

**SortExpression:** A **json-string** (section 2.2) that specifies the sort order to apply to the result set. If the **CacheCommands** contains **ApplySort:**

-   MUST be present.

-   MUST contain a **CT\_AdhocOrdering**, as specified in [\[MS-AXL2\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-AXL2%5d.pdf#Section_208c003b477b4743b29b6a8c92fa46ad) section 2.2.3.5.

**TotalRows:** A **json-int** (section 2.2) that specifies the total number of records in the **Source**. This element is populated by the protocol server, and sent as a part of **PagingInfo**, in the response body of all protocol operations. MUST be present when included in a paging response.

**UseCache:** MUST be ignored.

**RetrieveExactRowCount:** A **json-bool** (section 2.2) that specifies whether the protocol server retrieves the exact number of records or an approximation of the number of records in the **Source.** The protocol server retrieves the exact number of records if the value of **RetrieveExactRowCount** is **json-true**. If this element is not specified, a default value of **json-false** is used.

**RowKey:** A **json-int** (section 2.2) that specifies the value of the [**primary key**](#gt_e4d8c530-39c1-4fc6-8ccc-8d51a221158d) field of the record to return from the **Source** (section 3.1.1) specified by the **SelectCommand** element of the **SharedDataBaseInfo** (section 2.2.1.12).

-   MUST be non-negative.

    1.  #### <span id="section_90e96692144d4c71bcb735d2d5672fe6" class="anchor"><span id="_Toc445116549" class="anchor"></span></span>ParameterValue

The **ParameterValue** complex type is an input used by all protocol operations.

The following applies to the **ParameterValue** complex type, unless extended or overridden by an operation specification.

The **ParameterValue** type serves as a container for the name of a **CT\_Parameter** ([\[MS-AXL2\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-AXL2%5d.pdf#Section_208c003b477b4743b29b6a8c92fa46ad) section 2.2.3.12) and its associated value. Some **Sources** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)) in a database application are parameterized, and need parameter values to open them. Hence, this complex type is sent along with **SelectCommand** in a **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) in the request body of all protocol operations. The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c).

1.  ParameterValue = json-object

    Name = json-quotation-mark "Name" json-quotation-mark json-name-separator json-string

    Value = json-quotation-mark "Value" json-quotation-mark json-name-separator json-value

**ParameterValue** MUST contain two **json-member** instances that are not **json-null**, and each instance MUST be different. Each instance MUST be one of the following: **Name** and **Value**.

**Name:** A **json-string** (section 2.2) that specifies a value that uniquely identifies the **ParameterValue** within a collection.

**Value:** A **json-value** (section 2.2) that specifies data associated with the given **Name**.

#### <span id="section_15f468fe332a4c02af4e532b695ea41b" class="anchor"><span id="_Toc445116550" class="anchor"></span></span>RecordSet

The **RecordSet** is a complex type that is output by all the protocol operations. The **RecordSet** is specified by the **Result** element of the **ServiceResult** complex type (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)).

The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c) and applies to the **RecordSet**, unless extended or overridden by an operation specification.

1.  RecordSet = json-object

    Values = json-quotation-mark "Values" json-quotation-mark json-name-separator JsonArrayOfArrayOfAnyType

    Localized = json-quotation-mark "Localized" json-quotation-mark json-name-separator JsonArrayOfArrayOfArrayOfString

    Paging = json-quotation-mark "Paging" json-quotation-mark json-name-separator PagingInfo

    Fields = json-quotation-mark "Fields" json-quotation-mark json-name-separator json-begin-array \[FieldSchema \*( json-value-separator FieldSchema) \] json-end-array

    FormatInfos = json-quotation-mark "FormatInfos" json-quotation-mark json-name-separator json-begin-array \[FormatInfo \*( json-value-separator FormatInfo) \] json-end-array

    AutoSumValues = json-quotation-mark "AutoSumValues" json-quotation-mark json-name-separator JsonArrayOfAnyType

    CurrentUserPermissions = json-quotation-mark "CurrentUserPermissions" json-quotation-mark json-name-separator CurrentUserPermissions

    RelatedFieldInfos = json-quotation-mark "RelatedFieldInfos" json-quotation-mark json-name-separator json-begin-array \[FieldSchema \*( json-value-separator FieldSchema) \] json-end-array

**RecordSet** MUST contain at least one **json-member** instance from the following **json-member** instances. All **json-member** instances MUST be unique.

**Values**: A **JsonArrayOfArrayOfAnyType** (section 2.2) that specifies a record array. Each record is an array of values for the fields (3). Each field value at an ordinal in a record array is the value of the **FieldSchema** (section [2.2.1.3](#Section_30acf56e4f464584809b8655020c0183)) at the same ordinal in the **Fields** array **RecordSet**, returned in the **Result** element of the **ServiceResult** element from a previous call to the **GetData** operation (section [3.1.5.1.1](#Section_8e0492c58cb4494cb22457ca68e5386f)). MUST be present.

**Localized**: A **JsonArrayofArayOfArrayOfString** (section 2.2) that specifies the formatted value for each value in the **Values** array at the same ordial in the **FormatInfos** element in **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)). MUST be present.

**Paging**: A **PagingInfo**, as specified by section [2.2.1.7](#Section_e8004e1c5c2e4159a46b84caaf473c5f). MUST be present.

**Fields**: A **json-array** of **FieldSchema** ([\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 2.2.4.19) that specifies the schema of the fields of the **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), which is specified by the **SelectCommand** of the **SharedDataBaseInfo** complex type (section 2.2.1.12). MUST be present.

**FormatInfos**: A **json-array** of **FormatInfo** (section [2.2.1.6](#Section_fd0bb464b85f4f9c9954afa33cf0a59e)) that specifies the format information for the fields in the **Source**. MUST be present.

**AutoSumValues**: A **JsonArrayOfAnyType** (section 2.2) that specifies the results of aggregate functions, which are specified by the **AutoSumFunctions** of the **SharedDataBaseInfo** complex type (section 2.2.1.12), when applied to the fields specified by the **AutoSumFields** of the **SharedDatabaseInfo**.

**CurrentUserPermissions**: A **CurrentUserPermissions** (section [2.2.1.2](#Section_4afce5d527f24602806f5c2fe43270b9)) that specifies the permissions the user has for the database application.

**RelatedFieldInfos**: A **json-array** of **FieldSchema** (\[MS-ADR\] section 3.1.4.7.3.1) that specifies the schema of the related fields of the **Source** (section 3.1.1), which is specified by the **SelectCommand** of the **SharedDataBaseInfo** complex type (section 2.2.1.12).

#### <span id="section_2af4e1d0808a4cb7801ece964a1a154f" class="anchor"><span id="_Toc445116551" class="anchor"></span></span>ServiceError

The **ServiceError** complex type is an output used by all protocol operations. It is used to return alert (2) information to the protocol client.

The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c) and applies to the **ServiceError**, unless extended or overridden by an operation specification.

1.  ServiceError = json-object

    Message = json-quotation-mark "Message" json-quotation-mark json-name-separator ClientMessage

    Caption = json-quotation-mark "Caption" json-quotation-mark json-name-separator (json-string / json-null)

    HelpText = json-quotation-mark "HelpText" json-quotation-mark json-name-separator (json-string / json-null)

    HelpId = json-quotation-mark "HelpId" json-quotation-mark json-name-separator (json-string / json-null)

    Severity = json-quotation-mark "Severity" json-quotation-mark json-name-separator MessageSeverity

    Number = json-quotation-mark "Number" json-quotation-mark json-name-separator json-value

**ServiceError** MUST contain at least five and no more than six **json-member** instances, and each instance MUST be different. Each instance MUST be one of the following: **Caption**, **HelpId**, **HelpText**, **Message**, **Number**, and **Severity**.

**Caption:** A **json-string** (section 2.2) that specifies the [**caption**](#gt_81d81412-1575-4084-ba61-742de406b418) for the [**alert**](#gt_5038d42c-6611-4cfc-9c6a-d6a9d03a10e5). MUST be present.

**HelpId:** A **json-string** (section 2.2) that specifies the [**Help topic identifier**](#gt_bb52365c-d923-4f0a-ae73-707c31d99704).

**HelpText:** A **json-string** (section 2.2) that specifies a description of the help topic. MUST be present.

**Message:** A **ClientMessage** (section [2.2.1.1](#Section_a136d4ff75eb4eba8ff8313e032c273b)) that specifies a description of the alert. MUST be present. MUST NOT be empty.

**Number:** A **json-value** (section 2.2) that specifies an error code that is associated with this alert. MUST either be **json-null** or **json-int**.

**Severity:** A **MessageSeverity** (section [2.2.2.3](#Section_ad8d3b0d17c9493f8445fa1e1ce1537a)) that specifies the severity of the alert. MUST be present.

#### <span id="section_ef035760fdc5451387f91ab8b21647cd" class="anchor"><span id="_Toc445116552" class="anchor"></span></span>ServiceResult

The **ServiceResult** complex type is an output used by all protocol operations.

The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c) and applies to the **ServiceResult**, unless extended or overridden by an operation specification.

1.  ServiceResult = json-object

    Result = json-quotation-mark "Result" json-quotation-mark json-name-separator json-value

    Error = json-quotation-mark "Error" json-quotation-mark json-name-separator ServiceError

**ServiceResult** MUST contain at least one and no more than two **json-member** instances, and each instance MUST be different. Each instance MUST be one of the following: **Error**, and **Result**.

**Error:** A **ServiceError**, as specified in section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f).

**Result:** A **json-value** (section 2.2) that specifies the result of the protocol operation.

After the protocol server has finished the execution of the protocol operation, it creates the **ServiceResult** object, and then sends it in the Response body of the protocol operation. The **Result** element of the **ServiceResult** contains the result of the protocol operation, if it finished successfully, otherwise the **Error** element will contain the error information.

#### <span id="section_ee5da76004b540218b22c12c042648cc" class="anchor"><span id="_Toc445116553" class="anchor"></span></span>SharedDataBaseInfo

The **SharedDataBaseInfo** complex type specifies the **Source**, the fields from this **Source**, the sort order and restriction criteria of the records that are retrieved from database application.

The **SharedDataBaseInfo** complex type is an input used by all protocol operations.

The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c), and applies to the **SharedDataBaseInfo** unless extended or overridden by an operation specification.

1.  SharedDataBaseInfo = json-object

    SessionId = json-quotation-mark "SessionId" json-quotation-mark json-name-separator (json-string | json-null)

    SelectCommand = json-quotation-mark "SelectCommand" json-quotation-mark json-name-separator (json-string | json-null)

    ParameterValues = json-quotation-mark "ParameterValues" json-quotation-mark json-name-separator json-begin-array \[ParameterValue \*( json-value-separator ParameterValue) \] json-end-array

    OriginalCommand = json-quotation-mark "OriginalCommand" json-quotation-mark json-name-separator (json-string | json-null)

    AggregateExpressions = json-quotation-mark "AggregateExpressions" json-quotation-mark json-name-separator (json-string | json-null)

    AggregateFormatInfos = json-quotation-mark "AggregateFormatInfos" json-quotation-mark json-name-separator json-begin-array \[FormatInfo \*( json-value-separator FormatInfo) \] json-end-array

    Restriction = json-quotation-mark "Restriction" json-quotation-mark json-name-separator (json-string | json-null)

    Ordering = json-quotation-mark "Ordering" json-quotation-mark json-name-separator (json-string | json-null)

    AllowEdits = json-quotation-mark "AllowEdits" json-quotation-mark json-name-separator (json-string | json-null)

    AllowAdditions = json-quotation-mark "AllowAdditions" json-quotation-mark json-name-separator (json-string | json-null)

    AllowDeletions = json-quotation-mark "AllowDeletions" json-quotation-mark json-name-separator (json-string | json-null)

    DataEntry = json-quotation-mark "DataEntry" json-quotation-mark json-name-separator json-bool

    FieldNames = json-quotation-mark "FieldNames" json-quotation-mark json-name-separator (json-string | json-null)

    FormatInfos = json-quotation-mark "FormatInfos" json-quotation-mark json-name-separator json-begin-array \[FormatInfo \*( json-value-separator FormatInfo) \] json-end-array

    DataLevelFormat = json-quotation-mark "DataLevelFormat" json-quotation-mark json-name-separator json-bool

    ShowHeaders = json-quotation-mark "ShowHeaders" json-quotation-mark json-name-separator json-bool

    InitialPage = json-quotation-mark "InitialPage" json-quotation-mark json-name-separator (json-string | json-null)

    FetchSchema = json-quotation-mark "FetchSchema" json-quotation-mark json-name-separator json-bool

    FetchKeyFields = json-quotation-mark "FetchKeyFields" json-quotation-mark json-name-separator json-bool

    FetchDisplayFields = json-quotation-mark "FetchDisplayFields" json-quotation-mark json-name-separator json-bool

    DoNotPrefetchImages = json-quotation-mark "DoNotPrefetchImages" json-quotation-mark json-name-separator json-bool

    AutoSumFields = json-quotation-mark "AutoSumFields" json-quotation-mark json-name-separator JsonArrayOfString

    AutoSumFunctions = json-quotation-mark "AutoSumFunctions" json-quotation-mark json-name-separator JsonArrayOfString

**SharedDataBaseInfo** MUST contain at least one **json-member** instance from the following **json-member** instances. All **json-member** instances MUST be unique.

**AggregateExpressions:** MUST NOT be used.

**AggregateFormatInfos:** MUST NOT be used.

**AllowAdditions:** MUST NOT be used.

**AllowDeletions:** MUST NOT be used.

**AllowEdits:** MUST NOT be used.

**DataEntry:** MUST NOT be used.

**DataLevelFormat:** MUST NOT be used.

**FetchSchema:** A **json-bool** (section 2.2) that specifies whether the protocol server fetches the schema information of the **SelectCommand** element. The protocol server fetches the schema information if the value of **FetchSchema** is **json-true**; otherwise, the protocol server does not fetch schema information. If this element is not specified, a default value of **json-true** is used.

**FieldNames:** The fields from the **SelectCommand** for which data is to be fetched.

**FormatInfos:** A **json-array** of **FormatInfo** instances, as specified in section [2.2.1.6](#Section_fd0bb464b85f4f9c9954afa33cf0a59e).

**InitialPage:** MUST NOT be used.

**Ordering:** A **json-string** (section 2.2) that specifies the sort order. If present, the protocol server applies this sort order to the data and returns the sorted data. This element MUST contain a **CT\_AdHocOrdering** complex type, as specified in [\[MS-AXL2\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-AXL2%5d.pdf#Section_208c003b477b4743b29b6a8c92fa46ad) section 2.2.3.5.

**OriginalCommand:** MUST NOT be used.

**ParameterValues:** The value of each parameter, as specified in \[MS-AXL2\] section 2.2.3.17, required in the **SelectCommand** element. This element MUST be present for every parameter defined in **SelectCommand**.

-   The **Key** element is the name of the parameter.

-   The **Value** element is the value of the parameter in the correct data type.

**Restriction:** A **CT\_Expression** complex type, as specified in \[MS-AXL2\] section 2.2.3.1. Only records in **SelectCommand** that return "true" for this restriction expression are included in the **Result Set** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)).

**SelectCommand:** A **json-string** (section 2.2) that specifies the **Source** (section 3.1.1) from which data is to be retrieved.

**SessionId:** A **json-string** (section 2.2) that specifies a unique identifier for the session as specified in [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.1.2.

**ShowHeaders:** MUST NOT be used.

**FetchKeyFields:** A **json-bool** (section 2.2) that specifies whether the protocol server fetches the values of the primary key fields of the **SelectCommand** element. The protocol server fetches the values of the primary key fields if the value of **FetchKeyFields** is **json-true**; otherwise, the protocol server does not fetch the values of the primary key fields. If this element is not specified, a default value of **json-false** is used

**FetchDisplayFields:** A **json-bool** (section 2.2) that specifies whether the protocol server fetches the display values of the **foreign key** fields of the **SelectCommand** element. The protocol server fetches the display values of the **foreign key** fields if the value of **FetchDisplayFields** is **json-true**; otherwise, the protocol server does not fetch the display values of the **foreign key** fields. If this element is not specified, a default value of **json-false** is used

**DoNotPrefetchImages:** A **json-bool** (section 2.2) that specifies whether the protocol server fetches and caches the values of the image fields of the **SelectCommand** element. The protocol server does not fetch and cache the values of the image fields if the value of **DoNotPrefetchImages** is **json-true**; otherwise, the protocol server fetches and caches the values of the image fields. If this element is not specified, a default value of **json-false** is used.

**AutoSumFields:** A **JsonArrayOfString** (section 2.2) that specifies the names of fields for which the protocol server applies the **AutoSumFunctions**.

**AutoSumFunctions:** A **JsonArrayOfString** (section 2.2) that specifies the aggregate functions to be applied to the **AutoSumFields**. The number of elements in **AutoSumFunctions** MUST be exactly equal to the number of elements in the **AutoSumFields**.

#### <span id="section_2ffd6ea911884ef3aaf8aee48f62ae93" class="anchor"><span id="_Toc445116554" class="anchor"></span></span>UpdateRecord

The **UpdateRecord** complex type specifies the new values and original values for fields in an **Updatable Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)) that are used for insert, update, and delete operations.

The **UpdateRecord** type is an input used by some protocol operations.

The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c) and applies to **UpdateRecord**, unless extended or overridden by an operation specification.

1.  UpdateRecord = json-object

    OriginalValues = json-quotation-mark "OriginalValues" json-quotation-mark json-name-separator JsonArrayOfArrayOfAnyType

    NewValues = json-quotation-mark "NewValues" json-quotation-mark json-name-separator JsonArrayOfArrayOfString

    Paging = json-quotation-mark "Paging" json-quotation-mark json-name-separator PagingInfo

    ReturnDataMacroIds = json-quotation-mark "ReturnDataMacroIds" json-quotation-mark json-name-separator json-bool

**UpdateRecord** MUST contain at least one and no more than four **json-member** instances, and each instance MUST be different. Each instance MUST be one of the following: **NewValues**, **OriginalValues**, **Paging**, and **ReturnDataMacroIds**.

**NewValues:** A **JsonArrayOfArrayOfString** (section 2.2) that specifies the new values of a collection of records which need to be inserted, updated, or deleted. The protocol server will insert, update, or delete the records in a **Source** (section 3.1.1) with the values that are provided by this element.

**OriginalValues:** A **JsonArrayOfArrayOfAnyType** (section 2.2) that specifies the existing values of a collection of records in a **Source** (section 3.1.1), which need to be inserted, updated, or deleted.

**Paging:** A **PagingInfo** complex type, as specified in section [2.2.1.7](#Section_e8004e1c5c2e4159a46b84caaf473c5f). MUST be present.

**ReturnDataMacroIds:** MUST NOT be used.

### <span id="section_55121303aee2478c92d3b5aa08737a1f" class="anchor"><span id="_Toc445116555" class="anchor"></span></span>Simple Types

The following table summarizes the set of common JSON simple type definitions defined by this specification. JSON simple type definitions that are specific to a particular operation are described with the operation.

| Simple Type     | Description                                                                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CacheCommands   | The **CacheCommands** simple type as specified in [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 2.2.5.5. See section [2.2.2.1](#Section_9967041420a644f39788c2352f30810c). for more details. |
| ClientMessageID | A **ClientMessageID** simple type, as specified in \[MS-ADR\] section 2.2.5.6. See section [2.2.2.2](#Section_550384b20157467e9035d58293055f46) for more details.                                                                                                              |
| MessageSeverity | Specifies the severity of a **ServiceError** (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) sent from protocol server to protocol client. See section [2.2.2.3](#Section_ad8d3b0d17c9493f8445fa1e1ce1537a) for more details.                                  |

#### <span id="section_9967041420a644f39788c2352f30810c" class="anchor"><span id="_Toc445116556" class="anchor"></span></span>CacheCommands

The meaning of **CacheCommands** is specified by [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 2.2.5.5. The format of the **CacheCommands** simple type is specified by this section. The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c).

1.  CacheCommands = json-int;

The value of **CacheCommands** MUST be one of the values in the following table.

| Value | Meaning                                      |
|-------|----------------------------------------------|
| 0x01  | RefreshData, See \[MS-ADR\] section 2.2.5.   |
| 0x02  | ApplyFilter, See \[MS-ADR\] section 2.2.5.   |
| 0x04  | ClearFilter, See \[MS-ADR\] section 2.2.5.   |
| 0x08  | ApplySort, See \[MS-ADR\] section 2.2.5.     |
| 0x10  | RetrieveImage, See \[MS-ADR\] section 2.2.5. |

#### <span id="section_550384b20157467e9035d58293055f46" class="anchor"><span id="_Toc445116557" class="anchor"></span></span>ClientMessageID

The meaning of **ClientMessageID** is specified by[\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 2.2.5.6. The format of the **ClientMessageID** simple type is specified by this section. The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c).

1.  ClientMessageID = json-string;

The value of the **ClientMessageID** string MUST be one of the values in the following table.

| Value                                   | Meaning                        |
|-----------------------------------------|--------------------------------|
| None                                    | See \[MS-ADR\] section 2.2.5.6 |
| PassthroughMessage                      | See \[MS-ADR\] section 2.2.5.6 |
| WebServiceUnavailableMessage            | See \[MS-ADR\] section 2.2.5.6 |
| WebServiceCanceledMessage               | See \[MS-ADR\] section 2.2.5.6 |
| DataMacroStopWaiting                    | See \[MS-ADR\] section 2.2.5.6 |
| GenericError                            | See \[MS-ADR\] section 2.2.5.6 |
| NotifyRecordUpdated                     | See \[MS-ADR\] section 2.2.5.6 |
| NotifyRecordsDeleted                    | See \[MS-ADR\] section 2.2.5.6 |
| NotifyCannotDelete                      | See \[MS-ADR\] section 2.2.5.6 |
| NotifyCannotSave                        | See \[MS-ADR\] section 2.2.5.6 |
| NotifyCannotSaveDescription             | See \[MS-ADR\] section 2.2.5.6 |
| SubFormNestingLimitExceededError        | See \[MS-ADR\] section 2.2.5.6 |
| DivisionByZero                          | See \[MS-ADR\] section 2.2.5.6 |
| TypeMismatch                            | See \[MS-ADR\] section 2.2.5.6 |
| NoCurrentRecord                         | See \[MS-ADR\] section 2.2.5.6 |
| RecordNotUpdatable                      | See \[MS-ADR\] section 2.2.5.6 |
| WhereConditionTooLong                   | See \[MS-ADR\] section 2.2.5.6 |
| InvalidArgument                         | See \[MS-ADR\] section 2.2.5.6 |
| InvalidContainerControlName             | See \[MS-ADR\] section 2.2.5.6 |
| ActionArgumentNotFound                  | See \[MS-ADR\] section 2.2.5.6 |
| FormCannotClose                         | See \[MS-ADR\] section 2.2.5.6 |
| AttachmentMustSave                      | See \[MS-ADR\] section 2.2.5.6 |
| InvalidExpression                       | See \[MS-ADR\] section 2.2.5.6 |
| AttachmentUploadSucceed                 | See \[MS-ADR\] section 2.2.5.6 |
| AttachmentDeleted                       | See \[MS-ADR\] section 2.2.5.6 |
| FormOrReportNotBound                    | See \[MS-ADR\] section 2.2.5.6 |
| InvalidPropertyOrMethod                 | See \[MS-ADR\] section 2.2.5.6 |
| InvalidUrl                              | See \[MS-ADR\] section 2.2.5.6 |
| UserInterfaceMacroLoadFailure           | See \[MS-ADR\] section 2.2.5.6 |
| CannotFindMacroObject                   | See \[MS-ADR\] section 2.2.5.6 |
| CannotGoToSpecifiedRecord               | See \[MS-ADR\] section 2.2.5.6 |
| InvalidConditionExpression              | See \[MS-ADR\] section 2.2.5.6 |
| CannotGoToSubformOrTabpage              | See \[MS-ADR\] section 2.2.5.6 |
| InvalidControl                          | See \[MS-ADR\] section 2.2.5.6 |
| CannotFocusOnControl                    | See \[MS-ADR\] section 2.2.5.6 |
| InvalidControlValue                     | See \[MS-ADR\] section 2.2.5.6 |
| NoControlName                           | See \[MS-ADR\] section 2.2.5.6 |
| CannotFindErrorHandlingMacro            | See \[MS-ADR\] section 2.2.5.6 |
| InvalidSetPropertyControl               | See \[MS-ADR\] section 2.2.5.6 |
| LocalVarNameNotSpecified                | See \[MS-ADR\] section 2.2.5.6 |
| LocalVarExpressionNotSpecified          | See \[MS-ADR\] section 2.2.5.6 |
| LocalVariableNameInvalid                | See \[MS-ADR\] section 2.2.5.6 |
| TempVarNameNotSpecified                 | See \[MS-ADR\] section 2.2.5.6 |
| TempVariableNameInvalid                 | See \[MS-ADR\] section 2.2.5.6 |
| CommandNotAvailable                     | See \[MS-ADR\] section 2.2.5.6 |
| ExpressionErrorCannotSet                | See \[MS-ADR\] section 2.2.5.6 |
| TooManyRunMacros                        | See \[MS-ADR\] section 2.2.5.6 |
| InvalidBrowseToPathArgument             | See \[MS-ADR\] section 2.2.5.6 |
| InvalidObjectReference                  | See \[MS-ADR\] section 2.2.5.6 |
| FormNotFoundRep                         | See \[MS-ADR\] section 2.2.5.6 |
| ControlDoesNotSupportRequery            | See \[MS-ADR\] section 2.2.5.6 |
| ReadOnlyNote                            | See \[MS-ADR\] section 2.2.5.6 |
| TooMuchParameterData                    | See \[MS-ADR\] section 2.2.5.6 |
| OperationNotSupportedOnSubReports       | See \[MS-ADR\] section 2.2.5.6 |
| ExpressionErrorInfo                     | See \[MS-ADR\] section 2.2.5.6 |
| InvalidPropertyValue                    | See \[MS-ADR\] section 2.2.5.6 |
| AutocompleteWaitingForValidationMessage | See \[MS-ADR\] section 2.2.5.6 |
| AutocompleteInvalidDataMessage          | See \[MS-ADR\] section 2.2.5.6 |
| TooManyTermsInFilter                    | See \[MS-ADR\] section 2.2.5.6 |
| InvalidValueForFieldMessage             | See \[MS-ADR\] section 2.2.5.6 |
| InvalidValueForControlMessage           | See \[MS-ADR\] section 2.2.5.6 |
| ImageUploadFailureNotificationMessage   | See \[MS-ADR\] section 2.2.5.6 |
| NoResultsFromFilter                     | See \[MS-ADR\] section 2.2.5.6 |

#### <span id="section_ad8d3b0d17c9493f8445fa1e1ce1537a" class="anchor"><span id="_Toc445116558" class="anchor"></span></span>MessageSeverity

The **MessageSeverity** simple type is used to specify the severity of a **ServiceError** (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) sent to the protocol client. The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c).

1.  MessageSeverity = json-string;

The value of the **MessageSeverity** string MUST be one of the values in the following table.

| Value | Meaning                                                                                              |
|-------|------------------------------------------------------------------------------------------------------|
| Info  | The **ServiceError** indicates that an informational message has been sent from the protocol server. |
| Warn  | The **ServiceError** indicates that a warning has been sent from the protocol server.                |
| Error | The **ServiceError** indicates that an error has occurred.                                           |

1.  <span id="section_5e9e73a805614bc49d90198edc75b692" class="anchor"><span id="_Toc445116559" class="anchor"></span></span>Protocol Details
    =========================================================================================================================================

    1.  <span id="section_e9fb58d578d945088004776294b33914" class="anchor"><span id="_Toc445116560" class="anchor"></span></span>Server Details
        ---------------------------------------------------------------------------------------------------------------------------------------

The protocol server receives request messages from the protocol client in JSON format. The request messages can be either to retrieve, insert, update or delete data from the database application. The protocol server processes the request, and then returns the result set and alert in the **Result** and **Error** elements of **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)) object to the protocol client. The protocol server never initiates communication with other endpoints of the protocol.

### <span id="section_87227a78be1246b3b49414d9e1e7c416" class="anchor"><span id="_Toc445116561" class="anchor"></span></span>Abstract Data Model

This section describes a conceptual model of possible data organization that an implementation maintains to participate in this protocol. The described organization is provided to facilitate the explanation of how the protocol behaves. This document does not mandate that implementations adhere to this model as long as their external behavior is consistent with that described in this document.

This protocol includes the following Abstract Data Model elements, which are directly accessed from Access Services Data Run Time protocol as specified in [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.1:

-   **Session**

-   **Request**

-   **Source**

-   **Updatable Source**

The following elements are specific to this protocol:

-   **Page:** A partial result set, which is part of a sequence of partial result sets of the same size.

    1.  ### <span id="section_2be35f1bc0634612b7ed9758390348d6" class="anchor"><span id="_Toc445116562" class="anchor"></span></span>Timers

No new timers are required beyond those specified in [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.2.

### <span id="section_47ba0f6d247045f1a8ade432e5ebd19f" class="anchor"><span id="_Toc445116563" class="anchor"></span></span>Initialization

None.

### <span id="section_575d52e15c7e4b83b3e958f24e96342a" class="anchor"><span id="_Toc445116564" class="anchor"></span></span>Higher-Layer Triggered Events

None.

### <span id="section_da3d178827fa4328bb37f77d8349a7f1" class="anchor"><span id="_Toc445116565" class="anchor"></span></span>Message Processing Events and Sequencing Rules

The following table summarizes the operations in this protocol.

| Resources    | Description                                                                                                                                                                                                                   |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AccessPortal | Specifies a resource which operates against a [**site**](#gt_8abdc986-5679-42d9-ad76-b11eb5a0daba) that contains the database application. See section [3.1.5.1](#Section_7d55f39e1d1646c9a9b6fdd3024847d1) for more details. |

The responses to all the operations can result in the following status codes.

| Status code | Description                                                      |
|-------------|------------------------------------------------------------------|
| 200         | This status code indicates that operation finished successfully. |

#### <span id="section_7d55f39e1d1646c9a9b6fdd3024847d1" class="anchor"><span id="_Toc445116566" class="anchor"></span></span>AccessPortal

This resource operates against a site that is identified by a [**URL**](#gt_433a4fb7-ef84-46b0-ab65-905f5e3a80b1) that is known by protocol clients. The protocol server endpoint is formed by appending "/\_vti\_bin/accsvc/accessportal.json" to the URL of the site, for example: http://www.example.com/Repository/\_vti\_bin/accsvc/accessportal.json.

The operation path is obtained by appending the operation name to the endpoint, for example, "http://www.example.com/Repository/\_vti\_bin/accsvc/accessportal.json/&lt;serviceName&gt;"

The URL parameters are defined by the following ABNF syntax:

1.  serviceName = STRING

**serviceName**: The unique name of the hosted service operation.

| Operation         | Description                                                                                                                                                                                                                                                               |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| GetData           | Retrieves a subset of [**rows**](#gt_a87817fc-9b18-49a1-925e-9be9e1d92665) from a **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)) in a database application. See section [3.1.5.1.1](#Section_8e0492c58cb4494cb22457ca68e5386f) for more details. |
| InsertRecords     | Inserts records into an **Updatable Source** (section 3.1.1) in a database application. See section [3.1.5.1.2](#Section_66bcd29499404b03901d44f89d0ed240) for more details.                                                                                              |
| UpdateRecords     | Updates records into an **Updatable Source** (section 3.1.1) in a database application. See section [3.1.5.1.3](#Section_c08b87c6f773453a99078f8c66d2b613) for more details.                                                                                              |
| DeleteRecords     | Deletes records from an **Updatable Source** (section 3.1.1) in a database application. See section [3.1.5.1.4](#Section_8ebe43b81f7648509f5a99aa00dbf083) for more details.                                                                                              |
| GetDistinctValues | Retrieves distinct values for a field from a **Source** (section 3.1.1) in a database application. See section [3.1.5.1.5](#Section_15bf48dc3ff24004a3603a82f576419e) for more details.                                                                                   |
| FixupRow          | Performs modeling of a hypothetical update for an **Updatable Source** (section 3.1.1) in a database application. See section [3.1.5.1.6](#Section_05532d6eb25e46379a55284b41c96fc2) for more details.                                                                    |
| GetSearchData     | Retrieves records from **Source** (section 3.1.1). See section [3.1.5.1.7](#Section_361e998dcfb14886931838624f4b7098) for more details.                                                                                                                                   |

##### <span id="section_8e0492c58cb4494cb22457ca68e5386f" class="anchor"><span id="_Toc445116567" class="anchor"></span></span>GetData

This operation fetches a subset of rows from a **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), which is passed in as **SelectCommand** element of **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)).

This operation is transported by an HTTP **POST.**

The **serviceName** as specified in section [3.1.5.1](#Section_7d55f39e1d1646c9a9b6fdd3024847d1) MUST be "GetData".

The operation can be invoked through the following [**URI**](#gt_e18af8e8-01d7-4f91-8a1e-0fb21b191f95):

1.  http://www.example.com/Repository/\_vti\_bin/accsvc/accessportal.json/GetData.

During this operation, the protocol server receives a JSON request that contains the **SharedDataBaseInfo** (section 2.2.1.12) and **PagingInfo** (section [2.2.1.7](#Section_e8004e1c5c2e4159a46b84caaf473c5f)) objects. The protocol server then processes the request, and then responds with a JSON response that contains **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)). The **Values** element of **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)), which is returned as **Result** element of the **ServiceResult** contains the rows of data which protocol client had requested.

In the event of an application error on the protocol server during this operation, the **ServiceError**, as specified in section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f), MUST be present in **ServiceResult** (section 2.2.1.11).

The processing details for this operation are specified by section [3.1.5.1.1.3](#Section_9aab4fb8603648548bf8b11c86ada3c8).

###### <span id="section_8f459bc107444d16a5b4628e05c507be" class="anchor"><span id="_Toc445116568" class="anchor"></span></span>Request Body

The **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) and **PagingInfo** (section [2.2.1.7](#Section_e8004e1c5c2e4159a46b84caaf473c5f)) objects in Request Body determine which records are fetched from a **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), which is specified by the **SelectCommand** element of the **SharedDataBaseInfo**. The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c).

1.  GetDataRequest = dataBaseInfo-member pagingInfo-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    pagingInfo-member = json-quotation-mark "pagingInfo" json-quotation-mark json-name-separator PagingInfo

**dataBaseInfo:** A **SharedDataBaseInfo** (section 2.2.1.12) that specifies the **Source**, the fields from this **Source**, the sort order and restriction criteria of the records that are retrieved from the database application.

**pagingInfo:** A **PagingInfo** (section 2.2.1.7) that specifies which records are retrieved from the database application. MUST be present.

###### <span id="section_85d7012780394666add3e6a167a631dc" class="anchor"><span id="_Toc445116569" class="anchor"></span></span>Response Body

The records from the **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)) which is specified by the **SelectCommand** element of **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) are returned to the protocol client in the **Values** element of **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)), which is returned as the **Result** element of the **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)) in the Response Body. If there is any error on the protocol server, a **ServiceError** (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) is returned in the **Error** element of **ServiceResult.** The following ABNF references types specified by section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c).

1.  GetDataResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

**GetDataResult**: A **ServiceResult** (section 2.2.1.11) that specifies the records returned by protocol server to the protocol client. MUST be present.

###### <span id="section_9aab4fb8603648548bf8b11c86ada3c8" class="anchor"><span id="_Toc445116570" class="anchor"></span></span>Processing Details

The protocol client sends a request message, and the protocol server responds as specified in [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.4.4, except as follows:

-   The protocol server retrieves data from the given **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)) which is supplied as the **SelectCommand** element of the **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)), which is an input element of the Request Body (section [3.1.5.1.1.1](#Section_8f459bc107444d16a5b4628e05c507be)).

-   Only the fields that are specified by **FieldNames** input element of **SharedDataBaseInfo** are retrieved.

-   If the **FetchSchema** element of **SharedDataBaseInfo** is true, the protocol server also returns the schema information about the fields in **Source**, which are specified by **Fields** element of **SharedDataBaseInfo**. This schema information is returned via the **Fields** element of the **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)).

-   If the request sent to the protocol server is the first GetData request in the session, then the protocol server MUST return the **SessionIdentifier** (\[MS-ADR\] section 3.1.1.2) in the **SessionId** element of the **PagingInfo** (section [2.2.1.7](#Section_e8004e1c5c2e4159a46b84caaf473c5f)). The **PagingInfo** type is returned as an element in the **RecordSet**, which is returned as the **Result** element of the **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)) complex type.

In the event of an application error on the protocol server during this operation, the **ServiceError**, as specified in section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f), MUST be present in **ServiceResult** (section 2.2.1.11).

##### <span id="section_66bcd29499404b03901d44f89d0ed240" class="anchor"><span id="_Toc445116571" class="anchor"></span></span>InsertRecords

This operation inserts records into an **Updatable Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)) specified in the **SelectCommand** element of the **SharedDataBaseInfo** element in the request body (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)).

The protocol server receives a JSON request that contains the **SharedDataBaseInfo** and **UpdateRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) objects. The protocol server processes the request and responds with a JSON response that contains the **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)). The **Values** element of **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned as the **Result** element of the **ServiceResult** contains the records of data which the protocol server inserted.

In the event of an application error on the protocol server, the **ServiceError** element (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) MUST be present in **ServiceResult** (section 2.2.1.11).

This operation is transported by an HTTP **POST**.

The **serviceName** as specified in section [3.1.5.1](#Section_7d55f39e1d1646c9a9b6fdd3024847d1) MUST be "InsertRecords".

The processing details for this operation are specified by section [3.1.5.1.2.3](#Section_2339b014ffe14a4290c7662b6b4641c3).

###### <span id="section_6d8cde1816984f6da8c7a6a7d8a86eb6" class="anchor"><span id="_Toc445116572" class="anchor"></span></span>Request Body

The **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) and **UpdateRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) objects in Request Body determine the values for the fields of the records to be inserted into the **Updatable** **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)). The **Updatable** **Source** is specified by the **FieldSchema** elements in **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned as the **Result** element in the Response Body of a prior **GetData** operation (section [3.1.5.1.1.2](#Section_85d7012780394666add3e6a167a631dc)).

The values to be inserted are specified by the **NewValues** element of **UpdateRecord.** These values MUST be formatted according to the **FormatInfo** element of **SharedDataBaseInfo.** The **SessionId** element of **SharedDataBaseInfo** MUST be the same as the **SessionId** element of the **PagingInfo** which is an element of **RecordSet** (section 2.2.1.9) returned as the **Result** element in Response Body of the first **GetData** operation.

1.  InsertRecordsRequest = dataBaseInfo-member updateRecord-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    updateRecord-member = json-quotation-mark "updateRecord" json-quotation-mark json-name-separator UpdateRecord

**dataBaseInfo:** A **SharedDataBaseInfo** (section 2.2.1.12) that specifies information about the **Updatable** **Source** (section 3.1.1) into which records are to be inserted.

**updateRecord:** An **UpdateRecord** (section 2.2.1.13) that specifies the values for the fields of the records to be inserted.

-   The number of fields in each record MUST be the same for all the records, and MUST match the number and ordering of fields in the **FieldNames** element of **dataBaseInfo**.

-   The value of primary key fields in **NewValues** element MUST be "null".

-   Each field value at an ordinal in a record array from the **NewValues** element MUST be formatted according to the **FormatInfo** at the same ordinal in the **FormatInfos** array of the **dataBaseInfo**.

-   The **OriginalValues** element of the **UpdateRecord** MUST be ignored.

-   The field value at an ordinal in a record array from the **NewValues** element MUST be "null" if the **ReadOnly** element of the **FieldSchema** element at the same ordinal in the **Fields** array of the **RecordSet** (section 2.2.1.9), returned in the **Result** element of the **ServiceResult** element from a previous call to the **GetData** operation (section [3.1.5.1.1](#Section_8e0492c58cb4494cb22457ca68e5386f)) is "true".

    1.  ###### <span id="section_f68f9e0affb14b23b23f6a25a03d6c69" class="anchor"><span id="_Toc445116573" class="anchor"></span></span>Response Body

Returns the values of the successfully inserted records in the **Values** element of the **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned in the **Result** element of the **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)) in the Response Body. In the event of an error on the protocol server, a **ServiceError** (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) is returned in the **Error** part of **ServiceResult**.

1.  InsertRecordsResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

**InsertRecordsResult:** A **ServiceResult** (section 2.2.1.11) that specifies the records which are inserted by the protocol server. MUST be present.

-   The **Paging** element of the **RecordSet** MUST be the same as the **Paging** element of the **UpdateRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) which is passed in as an input element in the **Request Body** (section [3.1.5.1.2.1](#Section_6d8cde1816984f6da8c7a6a7d8a86eb6)) of the protocol operation.

    1.  ###### <span id="section_2339b014ffe14a4290c7662b6b4641c3" class="anchor"><span id="_Toc445116574" class="anchor"></span></span>Processing Details

The protocol server processes **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) and **UpdateRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) and inserts a collection of records in the **Updatable** **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), which is specified by **SelectCommand** of **SharedDataBaseInfo**.

The protocol server responds as specified in [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.4.8, except as follows:

-   The values for the fields of the new records are retrieved from the **NewValues** property of **UpdateRecord**.

-   The protocol server retrieves the values of all fields of the newly inserted records from the **Updatable** **Source** and returns them in the **Values** element of **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)), which is the **Result** element of **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)) in Response Body.

In the event of an application error on the protocol server during this operation, the **ServiceError**, as specified in section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f), MUST be present in **ServiceResult** (section 2.2.1.11).

##### <span id="section_c08b87c6f773453a99078f8c66d2b613" class="anchor"><span id="_Toc445116575" class="anchor"></span></span>UpdateRecords

This operation updates records in an **Updatable Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), specified in the **SelectCommand** element of **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) in the request body of the operation (section [3.1.5.1.3.1](#Section_0cc8edb23c344a2bb05764a2ca83490d)).

The protocol server receives a JSON request that contains the **SharedDataBaseInfo** (section 2.2.1.12) and **UpdateRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) objects. The protocol server processes the request and responds with a JSON response that contains **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)). The **Values** element of **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned as the **Result** element of the **ServiceResult** contains the records which the protocol server updated.

In the event of an application error on the protocol server during this operation, the **ServiceError** element (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) MUST be present in **ServiceResult** (section 2.2.1.11).

This operation is transported by an HTTP **POST**.

The **serviceName** as specified in section [3.1.5.1](#Section_7d55f39e1d1646c9a9b6fdd3024847d1) MUST be "UpdateRecords".

The processing details for this operation are specified by section [3.1.5.1.3.3](#Section_104df3bdb8214073ac6ed3bc0757b446).

###### <span id="section_0cc8edb23c344a2bb05764a2ca83490d" class="anchor"><span id="_Toc445116576" class="anchor"></span></span>Request Body

The **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) and **UpdateRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) objects in Request Body determine the original and new values for the fields of the records to be updated into the **Updatable** **Source**. The **Updatable** **Source** is specified by the **FieldSchema** elements in **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned as the **Result** element in the Response Body of a prior **GetData** operation (section [3.1.5.1.1.2](#Section_85d7012780394666add3e6a167a631dc))**. **

The original values and new values are specified by the **OriginalValues** and **NewValues** elements of the **UpdateRecord,** respectively**.** These values MUST be formatted according to the **FormatInfo** element of **SharedDataBaseInfo.** The **SessionId** element of the **SharedDataBaseInfo** MUST be same as the **SessionId** element of the **PagingInfo** element of **RecordSet** (section 2.2.1.9) returned in the **Result** element in Response Body of the first **GetData** operation.

1.  UpdateRecordsRequest = dataBaseInfo-member updateRecord-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    updateRecord-member = json-quotation-mark "updateRecord" json-quotation-mark json-name-separator UpdateRecord

**dataBaseInfo:** A **SharedDataBaseInfo** (section 2.2.1.12) that specifies information about the **Updatable Source** to be updated.

**updateRecord:** An **UpdateRecord** (section 2.2.1.13) that specifies the values for the fields of the records to be updated.

-   The number of records in **NewValues** element and **OriginalValues** element MUST be the same.

-   The number of fields in each record MUST be same for all the records, and MUST match the number and ordering of fields in **FieldNames** element of **dataBaseInfo**.

-   The fields value at an ordinal in a record array from the **OriginalValues** element MUST be of the same data type as specified by the **DataType** element of the **FieldSchema** element at the same ordinal in the **Fields** array of **RecordSet** (section 2.2.1.9), returned in the **Result** element of **ServiceResult** element of a prior call to **GetData** operation (section [3.1.5.1.1](#Section_8e0492c58cb4494cb22457ca68e5386f)).

-   Each field value at an ordinal in a record array from the **NewValues** element MUST be formatted according to the **FormatInfo** (section [2.2.1.6](#Section_fd0bb464b85f4f9c9954afa33cf0a59e)) at the same ordinal in the **FormatInfos** array of the **dataBaseInfo.**

-   Each primary key fields value at an ordinal in a record array from the **NewValues** element, when converted to a number MUST be equal to the value of field at the same ordinal in a record array from the **OriginalValues** element.

-   If value of any field in **OriginalValues** element is "null", that field is ignored by the protocol server and is not updated in the **Updatable Source**.

-   The field value at an ordinal in a record array from the **NewValues** and **OriginalValues** elements MUST be "null" if the **ReadOnly** element of the **FieldSchema** element at the same ordinal in the **Fields** array of the **RecordSet** (section 2.2.1.9), returned in the **Result** element of the **ServiceResult** element from a prior call to the **GetData** operation (section 3.1.5.1.1) is "true".

    1.  ###### <span id="section_ef8f0432c5614f4f9975ca97d5a259bb" class="anchor"><span id="_Toc445116577" class="anchor"></span></span>Response Body

Returns the values of the successfully updated records in the **Values** element of the **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned in the **Result** element of the **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)) in the Response Body. In the event of an error on the protocol server, a **ServiceError** (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) is returned in the **Error** part of **ServiceResult**.

1.  UpdateRecordsResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

**UpdateRecordsResult:** A **ServiceResult** (section 2.2.1.11) that specifies the records which are updated by the protocol server. MUST be present.

-   The **Paging** element of the **RecordSet** MUST be same as the **Paging** element of the **UpdateRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) which is passed in as an input element in the **Request Body** (section [3.1.5.1.3.1](#Section_0cc8edb23c344a2bb05764a2ca83490d)) of the protocol operation.

    1.  ###### <span id="section_104df3bdb8214073ac6ed3bc0757b446" class="anchor"><span id="_Toc445116578" class="anchor"></span></span>Processing Details

The protocol server processes the **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) and **UpdateRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) and updates a record in the **Updatable** **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), specified by **SelectCommand** of **SharedDataBaseInfo**.

The protocol server responds as specified in [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.4.12, except as follows:

-   The new values for the fields of the records to be updated are retrieved from the **NewValues** property of **UpdateRecord**.

-   The original values for the fields of the records to be updated are retrieved from the **OriginalValues** property of **UpdateRecord**.

-   The protocol server retrieves the newly updated records from the **Updatable** **Source** and returns them in the **Values** element of **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) which is returned as the **Result** element of **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)) in Response Body.

    1.  ##### <span id="section_8ebe43b81f7648509f5a99aa00dbf083" class="anchor"><span id="_Toc445116579" class="anchor"></span></span>DeleteRecords

This operation deletes records from an **Updatable** **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), specified in the **SelectCommand** element of **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) in the request body of the operation (section [3.1.5.1.4.1](#Section_86bcde4e522c4edc8f3dc3ac521d9237)).

The protocol server receives a JSON request that contains the **SharedDataBaseInfo** (section 2.2.1.12) and **UpdateRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) objects. The protocol server processes the request and responds with a JSON response that contains **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)). The **Values** element of **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned as the **Result** element of the **ServiceResult** contains a subset of the remaining records from the **Updatable** **Source**, after the requested records have been deleted.

In the event of an application error on the protocol server during this operation, the **ServiceError** element (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) MUST be present in **ServiceResult** (section 2.2.1.11)

This operation is transported by an HTTP **POST**.

The **serviceName** as specified in section [3.1.5.1](#Section_7d55f39e1d1646c9a9b6fdd3024847d1) MUST be "DeleteRecords".

The processing details for this operation are specified by section [3.1.5.1.4.3](#Section_f6a411969aed41c0b05650d7c556f45a).

###### <span id="section_86bcde4e522c4edc8f3dc3ac521d9237" class="anchor"><span id="_Toc445116580" class="anchor"></span></span>Request Body

The **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) and **UpdateRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) objects in Request Body determine the records to be deleted from **Updatable Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)). The **Updatable** **Source** is specified by the **FieldSchema** elements in **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned as the **Result** element in the Response Body of a prior **GetData** operation (section [3.1.5.1.1.2](#Section_85d7012780394666add3e6a167a631dc)).

The **SessionId** element of the **SharedDataBaseInfo** MUST be same as the **SessionId** element of the **PagingInfo** element of **RecordSet**, which is returned in the **Result** element in Response Body of the first **GetData** operation.

1.  DeleteRecordsRequest = dataBaseInfo-member updateRecord-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    updateRecord-member = json-quotation-mark "updateRecord" json-quotation-mark json-name-separator UpdateRecord

**dataBaseInfo:** A **SharedDataBaseInfo** (section 2.2.1.12) that specifies information about the **Updatable Source** from which records are to be deleted.

**updateRecord:** An **UpdateRecord** (section 2.2.1.13) that specifies the original values for the fields of the records to be deleted.

-   The number of fields in each record from **OriginalValues** element of **UpdateRecord** MUST be the same for all the records, and MUST match the number and ordering of fields in the **FieldNames** element of **dataBaseInfo**.

-   The value of primary key fields in **OriginalValues** element MUST NOT be "null".

-   The values of fields which are not primary key, are ignored.

-   The **NewValues** element of the **UpdateRecord** MUST be ignored.

    1.  ###### <span id="section_8623d8e1c2004a68bcb57da39fc0eabf" class="anchor"><span id="_Toc445116581" class="anchor"></span></span>Response Body

Returns the values of a subset of remaining records from the **Updatable Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)) in the **Values** element of the **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned by the **Result** element of the **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)) in the Response Body. In the event of an error on the protocol server, a **ServiceError** (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) is returned in the **Error** part of **ServiceResult.**

1.  DeleteRecordsResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

**DeleteRecordsResult:** A **ServiceResult** (section 2.2.1.11) that specifies a subset of the remaining records from **Updatable Source** after the requested records have been deleted by protocol server. MUST be present.

-   The **Paging** element of the **RecordSet** MUST be same as the **Paging** element of the **UpdateRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) which is passed in as an input element in the **Request Body** (section [3.1.5.1.2.1](#Section_6d8cde1816984f6da8c7a6a7d8a86eb6)) of the protocol operation.

    1.  ###### <span id="section_f6a411969aed41c0b05650d7c556f45a" class="anchor"><span id="_Toc445116582" class="anchor"></span></span>Processing Details

The protocol server processes the **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) and **UpdateRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) and then deletes a collection of records from the **Updatable** **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), which is specified by **SelectCommand** of **SharedDataBaseInfo**.

The protocol server responds as specified in [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.4.2, except as follows:

-   The values of the primary key fields of each records are retrieved from the **OriginalValues** element of **UpdateRecord**.

-   The protocol server returns a subset of the remaining records retrieved according to the **FirstRow** and the **PageSize elements** of the **PagingInfo** element of the **UpdateRecord**.

    1.  ##### <span id="section_15bf48dc3ff24004a3603a82f576419e" class="anchor"><span id="_Toc445116583" class="anchor"></span></span>GetDistinctValues

This operation retrieves records with distinct values for a field from **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), specified in the **SelectCommand** element of **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) in the request body of the operation (section [3.1.5.1.5.1](#Section_dff0edb3c92a4194b829db5ec721c8c5)).

The protocol server receives a JSON request that contains the **SharedDataBaseInfo** and **PagingInfo** (section [2.2.1.7](#Section_e8004e1c5c2e4159a46b84caaf473c5f)) objects. The request also contains a **columnName** for which distinct values are requested. The protocol server processes the request and responds with a JSON response that contains **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)). The **Values** element of **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned as the **Result** element of the **ServiceResult** contains the records from the **Source**, which contain distinct values for the requested **columnName.**

In the event of an application error on the protocol server during this operation, the **ServiceError** element (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) MUST be present in **ServiceResult** (section 2.2.1.11).

This operation is transported by an HTTP **POST**.

The **serviceName** as specified in section [3.1.5.1](#Section_7d55f39e1d1646c9a9b6fdd3024847d1) MUST be "GetDistinctValues".

The processing details for this operation are specified by section [3.1.5.1.5.3](#Section_1d42e373890c4423a4d0c98cdf06cbf8).

###### <span id="section_dff0edb3c92a4194b829db5ec721c8c5" class="anchor"><span id="_Toc445116584" class="anchor"></span></span>Request Body

The **SharedDataBaseInfo (**section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) and **PagingInfo** (section [2.2.1.7](#Section_e8004e1c5c2e4159a46b84caaf473c5f)) objects and the **columnName** element in Request Body determine which records are to be fetched from a **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), which is specified by the **SelectCommand** element of the **SharedDataBaseInfo.**

1.  GetDistinctValuesRequest = dataBaseInfo-member columnName-member pagingInfo-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    columnName-member = json-quotation-mark "columnName" json-quotation-mark json-name-separator json-string

    pagingInfo-member = json-quotation-mark "pagingInfo" json-quotation-mark json-name-separator PagingInfo

**dataBaseInfo:** A **SharedDataBaseInfo** (section 2.2.1.12) that specifies the **Source**, the fields from this **Source**, the sort order and restriction criteria of the records that are retrieved from the database application.

**columnName:** A **json-string** (section [2.2](#Section_1e211795f3c0470bbe90757a76a3f05c)) that specifies the field in the **Source** for which distinct values are retrieved.

**pagingInfo:** A **PagingInfo** (section 2.2.1.7) that specifies which records are retrieved from the database application.

###### <span id="section_bf4d7bb2339d4e81a1e9a54a49f8666c" class="anchor"><span id="_Toc445116585" class="anchor"></span></span>Response Body

Returns the values of field specified by **columnName** from the **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)) in the **Values** element of the **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned by the **Result** element of the **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)) in the Response Body. In the event of an error on the protocol server, a **ServiceError** (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) is returned in the **Error** part of **ServiceResult**

1.  GetDistinctValuesResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

**GetDistinctValuesResult:** A **ServiceResult** (section 2.2.1.11) that specifies the rows containing distinct values for the field specified by **columnName** element. MUST be present.

###### <span id="section_1d42e373890c4423a4d0c98cdf06cbf8" class="anchor"><span id="_Toc445116586" class="anchor"></span></span>Processing Details

The protocol server processes the **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) and **PagingInfo** (section [2.2.1.7](#Section_e8004e1c5c2e4159a46b84caaf473c5f)) objects and returns a subset of records from the **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), which contains distinct values for the field, specified by **columnName** in the Request Body.

The protocol server responds as specified in [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.4.5, except as follows:

-   The protocol server retrieves data from the given **Source** passed in as the **SelectCommand** element of the **SharedDataBaseInfo** (section 2.2.1.12), an input element of the Request Body (section [3.1.5.1.5.1](#Section_dff0edb3c92a4194b829db5ec721c8c5)).

-   Values are retrieved only for the field that is specified by **columnName** input element of the Request Body.

    1.  ##### <span id="section_05532d6eb25e46379a55284b41c96fc2" class="anchor"><span id="_Toc445116587" class="anchor"></span></span>FixupRow

This operation returns the resulting values of modeling a hypothetical update on one of the records in an **Updatable Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), specified in the **SelectCommand** element of **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) in the request body of the operation (section [3.1.5.1.6.1](#Section_410dd1822000446ebda226402f8767bb)).

The protocol server receives a JSON request that contains the **SharedDataBaseInfo** (section 2.2.1.12) and **FixupRecord** (section [2.2.1.5](#Section_bccb561364bb453ca501aea0124333f7)) objects. The protocol server processes the request and responds with a JSON response that contains **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)). The **Values** element of **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned as **Result** element of the **ServiceResult** contains the record from the **Updatable** **Source**, which contains resulting values of hypothetical update on that record.

In the event of an application error on the protocol server during this operation, the **ServiceError** element (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) MUST be present in **ServiceResult** (section 2.2.1.11)

This operation is transported by an HTTP **POST.**

The **serviceName** as specified in section [3.1.5.1](#Section_7d55f39e1d1646c9a9b6fdd3024847d1) MUST be "FixupRow".

The processing details for this operation are specified by section [3.1.5.1.6.3](#Section_842676765d8349a3b329f292a3a32939).

###### <span id="section_410dd1822000446ebda226402f8767bb" class="anchor"><span id="_Toc445116588" class="anchor"></span></span>Request Body

The **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) and **FixupRecord** (section [2.2.1.13](#Section_2ffd6ea911884ef3aaf8aee48f62ae93)) objects in Request Body determine the values for the fields of the record for which an update is to be modeled in the **Updatable** **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)). The **Updatable** **Source** is specified by the **FieldSchema** elements in **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned as the **Result** element in the Response Body of a prior **GetData** operation (section [3.1.5.1.1.2](#Section_85d7012780394666add3e6a167a631dc)). This operation just returns the result of the hypothetical update. The fields in **Updatable Source** are not updated.

1.  FixupRowRequest = dataBaseInfo-member fixupRecord-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    fixupRecord-member = json-quotation-mark "fixupRecord" json-quotation-mark json-name-separator FixupRecord

**dataBaseInfo:** A **SharedDataBaseInfo** (section 2.2.1.12) that specifies information about **Updatable Source** on which hypothetical update is to be performed.

-   The **SessionId** element of **SharedDataBaseInfo** MUST be same as the **SessionId** element of the **PagingInfo** element of **RecordSet** (section 2.2.1.9), which is returned in the **Result** element in Response Body of the first **GetData** operation (section 3.1.5.1.1.2).

**fixupRecord:** A **FixupRecord** (section [2.2.1.5](#Section_bccb561364bb453ca501aea0124333f7)) that specifies the values for the fields of the records which are to be used for the hypothetical update.

-   The values to be updated are specified by the **SupportingFieldValues** element of **FixupRecord.**

-   These values are for the fields whose indexes in **Fields** array of **RecordSet** (section 2.2.1.9), returned in the **Result** element of **ServiceResult** element of a previous call to **GetData** operation (section [3.1.5.1.1](#Section_8e0492c58cb4494cb22457ca68e5386f)) are specified by **SupportingFieldIndexes** element.

-   These values MUST be formatted according to the **FormatInfo** element of **SharedDataBaseInfo.**

-   The number of values in **SupportingFieldValues** element and **SupportingFieldIndexes** element MUST be the same.

-   The value of the primary key field of the **Updatable Source** is specified by the **Key** element of the **FixupRecord**.

    1.  ###### <span id="section_9799b7e3137a49e0aba53a3c32d6f3c8" class="anchor"><span id="_Toc445116589" class="anchor"></span></span>Response Body

Returns the resulting values of the successful hypothetical update in the **Values** element of the **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned in the **Result** element of the **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)) in the Response Body. In the event of an error on the protocol server, a **ServiceError** (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) is returned in the **Error** part of **ServiceResult.**

1.  FixupRowResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

**FixupRowResult**: A **ServiceResult** (section 2.2.1.11) that specifies the row that is the result of hypothetical update. MUST be present.

###### <span id="section_842676765d8349a3b329f292a3a32939" class="anchor"><span id="_Toc445116590" class="anchor"></span></span>Processing Details

The protocol server processes the **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) and **FixupRecord** (section [2.2.1.5](#Section_bccb561364bb453ca501aea0124333f7)) objects and returns a record from the **Updatable Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), which is specified by the **SelectCommand** element of **SharedDataBaseInfo** (section 2.2.1.12)**.** The values contain the resulting values of a hypothetical update performed on that record.

The protocol server responds as specified in [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.4.3, except as follows:

-   The original record is retrieved from **Updatable** **Source** (section 3.1.1). The primary key of the record MUST match the **Key** element from **FixupRecord** (section 2.2.1.5).

-   In the event of an application error on the protocol server during this operation, the **ServiceError**, as specified in section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f), MUST be present in **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)).

    1.  ##### <span id="section_361e998dcfb14886931838624f4b7098" class="anchor"><span id="_Toc445116591" class="anchor"></span></span>GetSearchData

This operation retrieves records from **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), specified in the **SelectCommand** element of **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) in the request body of the operation (section [3.1.5.1.7.1](#Section_5b9af9979b1849e6817a427d881e19fd)).

The protocol server receives a JSON request that contains the **SharedDataBaseInfo** object. The protocol server processes the request and responds with a JSON response that contains **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)). The **Values** element of **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned as the **Result** element of the **ServiceResult** contains the records from the **Source,** which matches the following conditions.

-   A maximum of 9 records are retrieved.

-   In each record, the combination of values of fields whose indexes in **FieldNames** are 0 and 1 MUST be distinct.

-   Only records where value of the field whose index in **FieldNames** is 1, contains the **Restriction** element of **SharedDataBaseInfo** are retrieved.

In the event of an application error on the protocol server during this operation, the **ServiceError** element (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) MUST be present in **ServiceResult** (section 2.2.1.11).

This operation is transported by an HTTP **POST**.

The **serviceName** as specified in section [3.1.5.1](#Section_7d55f39e1d1646c9a9b6fdd3024847d1) MUST be "GetSearchData".

The processing details for this operation are specified by section [3.1.5.1.7.3](#Section_21775758678245f5abc4f623d7b64a5b).

###### <span id="section_5b9af9979b1849e6817a427d881e19fd" class="anchor"><span id="_Toc445116592" class="anchor"></span></span>Request Body

The **SharedDataBaseInfo (**section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) object in Request Body determines fields to be retrieved from a **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), which is specified by the **SelectCommand** element of the **SharedDataBaseInfo.**

1.  GetSearchDataRequest = dataBaseInfo-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

**dataBaseInfo:** A **SharedDataBaseInfo** (section 2.2.1.12) that specifies information about **Source** from which records are to be retrieved from database application.

-   The fields for which data is to be retrieved are specified by the **FieldNames** element of the **SharedDataBaseInfo**.

-   At least two fields MUST be present in the **FieldNames** element.

-   At most three fields MUST be present in the **FieldNames** element.

-   **Restriction** element of **SharedDataBaseInfo** MUST NOT be empty.

    1.  ###### <span id="section_b9d06250920e4b94a2ed6fe495c6053a" class="anchor"><span id="_Toc445116593" class="anchor"></span></span>Response Body

Returns the values of field specified by the **FieldNames** element of **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) from the **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)) in the **Values** element of the **RecordSet** (section [2.2.1.9](#Section_15f468fe332a4c02af4e532b695ea41b)) returned by the **Result** element of the **ServiceResult** (section [2.2.1.11](#Section_ef035760fdc5451387f91ab8b21647cd)) in the Response Body. In the event of an error on the protocol server, a **ServiceError** (section [2.2.1.10](#Section_2af4e1d0808a4cb7801ece964a1a154f)) is returned in the **Error** part of **ServiceResult**.

1.  GetSearchDataResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

**GetSearchDataResult:** A **ServiceResult** (section 2.2.1.11) that specifies the rows containing values for field specified by **FieldNames** element of **SharedDataBaseInfo**. MUST be present.

###### <span id="section_21775758678245f5abc4f623d7b64a5b" class="anchor"><span id="_Toc445116594" class="anchor"></span></span>Processing Details

The protocol server processes the **SharedDataBaseInfo** (section [2.2.1.12](#Section_ee5da76004b540218b22c12c042648cc)) object and returns at most 9 records from the **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)), which contains distinct values for the combination of fields, with indexes 0 and 1 in the **FieldNames** element of **SharedDataBaseInfo** element in the Request Body.

The processing is done as follows.

-   The protocol server retrieves data from the given **Source** passed in as the **SelectCommand** element of the **SharedDataBaseInfo** (section 2.2.1.12), an input element of the Request Body (section [3.1.5.1.5.1](#Section_dff0edb3c92a4194b829db5ec721c8c5)).

-   Values are retrieved only for the first three fields specified by the **FieldNames** element of the **SharedDataBaseInfo** input element of the Request Body.

-   In each record, the combination of values of fields whose indexes in **FieldNames** are 0 and 1 MUST be distinct.

-   Only records where value of the field whose index in **FieldNames** is 1, contains the **Restriction** element of **SharedDataBaseInfo** are retrieved.

    1.  ### <span id="section_022cf89865cd475c828b4762c8eca124" class="anchor"><span id="_Toc445116595" class="anchor"></span></span>Timer Events

        1.  #### <span id="section_7ace28d63235440e9e5171c695ee305a" class="anchor"><span id="_Toc445116596" class="anchor"></span></span>Session Timeout

Session Timeout, as specified by [\[MS-ADR\]](file:///E:\Target\Office\Published\Books\MS-ART\%5bMS-ADR%5d.pdf#Section_0b384f8d26a64cb3a4acc32a18f1f2aa) section 3.1.5.1.

### <span id="section_6450a57666ee46ca95fac480b045d2c8" class="anchor"><span id="_Toc445116597" class="anchor"></span></span>Other Local Events

None.

1.  <span id="section_3706288fe6c54bf5a81506b62e8166e9" class="anchor"><span id="_Toc445116598" class="anchor"></span></span>Protocol Examples
    ==========================================================================================================================================

    1.  <span id="section_8a35d4b8dedc4d648c12cf778e301d20" class="anchor"><span id="_Toc445116599" class="anchor"></span></span>GetData Service Operation
        --------------------------------------------------------------------------------------------------------------------------------------------------

This example shows fetching a subset of rows from a **Source** (section [3.1.1](#Section_87227a78be1246b3b49414d9e1e7c416)).

The protocol client sends the following message to the protocol server to perform a **GetData** operation.

1.  { "dataBaseInfo" : { "AllowAdditions" : true,

    "AllowDeletions" : true,

    "AllowEdits" : true,

    "FetchSchema" : true,

    "SelectCommand" : "Employees"

    },

    "pagingInfo" : { "CacheCommands" : 8,

    "FirstRow" : 0,

    "PageSize" : 50,

    "SortExpression" : "&lt;Ordering xmlns=\\"http://schemas.microsoft.com/office/accessservices/2010/12/application\\" &gt;&lt;Order Name=\\"FirstName\\" Direction=\\"Ascending\\" /&gt;&lt;/Ordering&gt;",

    "UseCache" : false

    }

    }

The protocol server sends back the following response.

1.  { "d" : { "Error" : null,

    "Result" : { "AggregateLocalized" : null,

    "AggregateValues" : null,

    "AnonymousCanInsert" : false,

    "AnonymousCanRead" : true,

    "DataMacroInstanceIds" : null,

    "Fields" : \[ { "AllowMultipleValues" : false,

    "ColumnName" : "ID",

    "CurrencySymbol" : null,

    "DataType" : "Int",

    "DecimalPlaces" : -1,

    "DefaultExpression" : null,

    "DefaultValue" : "",

    "DependentFields" : null,

    "FormatString" : null,

    "IsKey" : true,

    "IsTableQueryLookup" : false,

    "KeyIndex" : -1,

    "LookupBoundField" : null,

    "LookupDisplayField" : null,

    "LookupSortType" : null,

    "LookupSource" : null,

    "MaxLength" : 4,

    "ReadOnly" : true,

    "Required" : true,

    "SourceObject" : null,

    "TextType" : null,

    "ValidationMessage" : null,

    "ValidationScript" : null

    },

    { "AllowMultipleValues" : false,

    "ColumnName" : "FirstName",

    "CurrencySymbol" : null,

    "DataType" : "NVarChar",

    "DecimalPlaces" : -1,

    "DefaultExpression" : null,

    "DefaultValue" : "",

    "DependentFields" : null,

    "FormatString" : null,

    "IsKey" : false,

    "IsTableQueryLookup" : false,

    "KeyIndex" : -1,

    "LookupBoundField" : null,

    "LookupDisplayField" : null,

    "LookupSortType" : null,

    "LookupSource" : null,

    "MaxLength" : 220,

    "ReadOnly" : false,

    "Required" : false,

    "SourceObject" : null,

    "TextType" : "SingleLine",

    "ValidationMessage" : null,

    "ValidationScript" : null

    },

    { "AllowMultipleValues" : false,

    "ColumnName" : "LastName",

    "CurrencySymbol" : null,

    "DataType" : "NVarChar",

    "DecimalPlaces" : -1,

    "DefaultExpression" : null,

    "DefaultValue" : "",

    "DependentFields" : null,

    "FormatString" : null,

    "IsKey" : false,

    "IsTableQueryLookup" : false,

    "KeyIndex" : -1,

    "LookupBoundField" : null,

    "LookupDisplayField" : null,

    "LookupSortType" : null,

    "LookupSource" : null,

    "MaxLength" : 220,

    "ReadOnly" : false,

    "Required" : false,

    "SourceObject" : null,

    "TextType" : "SingleLine",

    "ValidationMessage" : null,

    "ValidationScript" : null

    }

    \],

    "FormatInfos" : \[ \[ { "Currency" : null,

    "Format" : null,

    "Precision" : -1,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.FormatInfo"

    } \],

    \[ { "Currency" : null,

    "Format" : null,

    "Precision" : -1,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.FormatInfo"

    } \],

    \[ { "Currency" : null,

    "Format" : null,

    "Precision" : -1,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.FormatInfo"

    } \]

    \],

    "IsAnonymous" : false,

    "Localized" : \[ \[ null,

    null,

    null

    \] \],

    "Paging" : { "CacheCommands" : 8,

    "Filter" : null,

    "FirstRow" : 0,

    "Moniker" : null,

    "PageSize" : 50,

    "SessionId" : "36.31b40d30-46c9-4850-9546-3ac936024abd163.1.V22.50DEXMZ5ML2xUiPMVnvjBS90.5.en-US5.en-US73.+0480\#0000-11-00-01T02:00:00:0000\#+0000\#0000-03-00-02T02:00:00:0000\#-006036.00000000-0000-0000-0000-0000000000001.U",

    "SortExpression" : "&lt;Ordering xmlns=\\"http://schemas.microsoft.com/office/accessservices/2010/12/application\\" &gt;&lt;Order Name=\\"FirstName\\" Direction=\\"Ascending\\" /&gt;&lt;/Ordering&gt;",

    "TotalRows" : 1,

    "UseCache" : false,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.PagingInfo"

    },

    "RecordStatuses" : null,

    "Values" : \[ \[ 1,

    "Updated First Name",

    "Last Name"

    \] \]

    },

    "\_\_type" : "Microsoft.Office.Access.Services.UI.ServiceResult"

    } }

    1.  <span id="section_0bb3d689a4fe45e88a372ca5a9843dad" class="anchor"><span id="_Toc445116600" class="anchor"></span></span>InsertRecords Service Operation
        --------------------------------------------------------------------------------------------------------------------------------------------------------

This example describes how to use the **InsertRecords** Service Operation method (section [3.1.5.1.2](#Section_66bcd29499404b03901d44f89d0ed240)) to insert an item into a table.

The protocol client sends the following message to the protocol server to insert an item into a table.

1.  { "dataBaseInfo" : { "AggregateExpressions" : null,

    "AggregateFormatInfos" : \[ \],

    "AllowAdditions" : true,

    "AllowDeletions" : true,

    "AllowEdits" : true,

    "FetchSchema" : false,

    "FieldNames" : \[ "ID",

    "FirstName",

    "LastName"

    \],

    "FormatInfos" : \[ \[ { "Currency" : null,

    "Format" : null,

    "Precision" : -1

    } \] \],

    "ParameterValues" : null,

    "SelectCommand" : "Employees",

    "SessionId" : "36.31b40d30-46c9-4850-9546-3ac936024abd163.1.V22.47oNwJCV0bA0inRQRXCt3u90.5.en-US5.en-US73.+0480\#0000-11-00-01T02:00:00:0000\#+0000\#0000-03-00-02T02:00:00:0000\#-006036.00000000-0000-0000-0000-0000000000001.U"

    },

    "updateRecord" : { "NewValues" : \[ \[ null,

    "First Name",

    "Last Name"

    \] \],

    "Paging" : { "CacheCommands" : 0,

    "Filter" : null,

    "FirstRow" : 0,

    "Moniker" : null,

    "PageSize" : 1,

    "SessionId" : null,

    "SortExpression" : "&lt;Ordering xmlns=\\"http://schemas.microsoft.com/office/accessservices/2010/12/application\\" &gt;&lt;Order Name=\\"FirstName\\" Direction=\\"Ascending\\" /&gt;&lt;/Ordering&gt;",

    "TotalRows" : 1,

    "UseCache" : true

    },

    "ReturnDataMacroIds" : false

    }

    }

The protocol server sends back the following response.

1.  { "d" : { "Error" : null,

    "Result" : { "AggregateLocalized" : null,

    "AggregateValues" : null,

    "AnonymousCanInsert" : false,

    "AnonymousCanRead" : true,

    "DataMacroInstanceIds" : null,

    "Fields" : null,

    "FormatInfos" : \[ \[ { "Currency" : null,

    "Format" : null,

    "Precision" : -1,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.FormatInfo"

    } \],

    \[ { "Currency" : null,

    "Format" : null,

    "Precision" : -1,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.FormatInfo"

    } \],

    \[ { "Currency" : null,

    "Format" : null,

    "Precision" : -1,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.FormatInfo"

    } \]

    \],

    "IsAnonymous" : false,

    "Localized" : \[ \[ null,

    null,

    null

    \] \],

    "Paging" : { "CacheCommands" : 0,

    "Filter" : null,

    "FirstRow" : 0,

    "Moniker" : null,

    "PageSize" : 1,

    "SessionId" : null,

    "SortExpression" : "&lt;Ordering xmlns=\\"http://schemas.microsoft.com/office/accessservices/2010/12/application\\" &gt;&lt;Order Name=\\"FirstName\\" Direction=\\"Ascending\\" /&gt;&lt;/Ordering&gt;",

    "TotalRows" : 1,

    "UseCache" : true,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.PagingInfo"

    },

    "RecordStatuses" : null,

    "Values" : \[ \[ 1,

    "First Name",

    "Last Name"

    \] \]

    },

    "\_\_type" : "Microsoft.Office.Access.Services.UI.ServiceResult"

    } }

    1.  <span id="section_0c3904c915bc4818baa68674636e91cb" class="anchor"><span id="_Toc445116601" class="anchor"></span></span>UpdateRecords Service Operation
        --------------------------------------------------------------------------------------------------------------------------------------------------------

This example describes how to use the **UpdateRecords** Service Operation method (section [3.1.5.1.3](#Section_c08b87c6f773453a99078f8c66d2b613)) to update an item into a table.

The protocol client sends the following message to the protocol server to update an item into a table:

1.  { "dataBaseInfo" : { "AggregateExpressions" : null,

    "AggregateFormatInfos" : \[ \],

    "AllowAdditions" : true,

    "AllowDeletions" : true,

    "AllowEdits" : true,

    "FetchSchema" : false,

    "FieldNames" : \[ "ID",

    "FirstName",

    "LastName"

    \],

    "FormatInfos" : \[ \[ { "Currency" : null,

    "Format" : null,

    "Precision" : -1

    } \] \],

    "ParameterValues" : null,

    "SelectCommand" : "Employees",

    "SessionId" : "36.31b40d30-46c9-4850-9546-3ac936024abd163.1.V22.47oNwJCV0bA0inRQRXCt3u90.5.en-US5.en-US73.+0480\#0000-11-00-01T02:00:00:0000\#+0000\#0000-03-00-02T02:00:00:0000\#-006036.00000000-0000-0000-0000-0000000000001.U"

    },

    "updateRecord" : { "NewValues" : \[ \[ "1",

    "Updated First Name",

    null

    \] \],

    "OriginalValues" : \[ \[ 1,

    "First Name",

    null

    \] \],

    "Paging" : { "CacheCommands" : 0,

    "Filter" : null,

    "FirstRow" : 0,

    "Moniker" : null,

    "PageSize" : 1,

    "SessionId" : null,

    "SortExpression" : "&lt;Ordering xmlns=\\"http://schemas.microsoft.com/office/accessservices/2010/12/application\\" &gt;&lt;Order Name=\\"FirstName\\" Direction=\\"Ascending\\" /&gt;&lt;/Ordering&gt;",

    "TotalRows" : 1,

    "UseCache" : true,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.PagingInfo"

    },

    "ReturnDataMacroIds" : false

    }

    }

The protocol server sends back the following response.

1.  { "d" : { "Error" : null,

    "Result" : { "AggregateLocalized" : null,

    "AggregateValues" : null,

    "AnonymousCanInsert" : false,

    "AnonymousCanRead" : true,

    "DataMacroInstanceIds" : null,

    "Fields" : null,

    "FormatInfos" : \[ \[ { "Currency" : null,

    "Format" : null,

    "Precision" : -1,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.FormatInfo"

    } \],

    \[ { "Currency" : null,

    "Format" : null,

    "Precision" : -1,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.FormatInfo"

    } \],

    \[ { "Currency" : null,

    "Format" : null,

    "Precision" : -1,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.FormatInfo"

    } \]

    \],

    "IsAnonymous" : false,

    "Localized" : \[ \[ null,

    null,

    null

    \] \],

    "Paging" : { "CacheCommands" : 0,

    "Filter" : null,

    "FirstRow" : 0,

    "Moniker" : null,

    "PageSize" : 1,

    "SessionId" : null,

    "SortExpression" : "&lt;Ordering xmlns=\\"http://schemas.microsoft.com/office/accessservices/2010/12/application\\" &gt;&lt;Order Name=\\"FirstName\\" Direction=\\"Ascending\\" /&gt;&lt;/Ordering&gt;",

    "TotalRows" : 1,

    "UseCache" : true,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.PagingInfo"

    },

    "RecordStatuses" : null,

    "Values" : \[ \[ 1,

    "Updated First Name",

    "Last Name"

    \] \]

    },

    "\_\_type" : "Microsoft.Office.Access.Services.UI.ServiceResult"

    } }

    1.  <span id="section_c3ad0c7c9a1f49e38359da4d68257509" class="anchor"><span id="_Toc445116602" class="anchor"></span></span>DeleteRecords Service Operation
        --------------------------------------------------------------------------------------------------------------------------------------------------------

This example describes how to use the **DeleteRecords** Service Operation method (section [3.1.5.1.4](#Section_8ebe43b81f7648509f5a99aa00dbf083)) to delete an item from a table.

The protocol client sends the following message to the protocol server to delete an item from a table.

1.  { "dataBaseInfo" : { "AggregateExpressions" : null,

    "AggregateFormatInfos" : \[ \],

    "AllowAdditions" : true,

    "AllowDeletions" : true,

    "AllowEdits" : true,

    "FetchSchema" : false,

    "FieldNames" : \[ "ID",

    "FirstName",

    "LastName"

    \],

    "FormatInfos" : \[ \[ { "Currency" : null,

    "Format" : null,

    "Precision" : -1

    } \] \],

    "ParameterValues" : null,

    "SelectCommand" : "Employees",

    "SessionId" : "36.31b40d30-46c9-4850-9546-3ac936024abd163.1.V22.51RMVPQFdeHSB2Ag5Mm53S90.5.en-US5.en-US73.+0480\#0000-11-00-01T02:00:00:0000\#+0000\#0000-03-00-02T02:00:00:0000\#-006036.00000000-0000-0000-0000-0000000000001.U"

    },

    "updateRecord" : { "OriginalValues" : \[ \[ 2,

    "First Name 1",

    "Last Name 1"

    \] \],

    "Paging" : { "CacheCommands" : 0,

    "Filter" : null,

    "FirstRow" : 1,

    "Moniker" : null,

    "PageSize" : 1,

    "SessionId" : null,

    "SortExpression" : "&lt;Ordering xmlns=\\"http://schemas.microsoft.com/office/accessservices/2010/12/application\\" &gt;&lt;Order Name=\\"FirstName\\" Direction=\\"Ascending\\" /&gt;&lt;/Ordering&gt;",

    "TotalRows" : 2,

    "UseCache" : true,

    "\_\_type" : "Microsoft.Office.Access.Services.UI.PagingInfo"

    },

    "ReturnDataMacroIds" : false

    }

    }

The protocol server sends back the following response.

1.  { "d" : { "Error" : null,

"Result" : { "AggregateLocalized" : null,

"AggregateValues" : null,

"AnonymousCanInsert" : false,

"AnonymousCanRead" : true,

"DataMacroInstanceIds" : null,

"Fields" : null,

"FormatInfos" : \[ \[ { "Currency" : null,

"Format" : null,

"Precision" : -1,

"\_\_type" : "Microsoft.Office.Access.Services.UI.FormatInfo"

} \],

\[ { "Currency" : null,

"Format" : null,

"Precision" : -1,

"\_\_type" : "Microsoft.Office.Access.Services.UI.FormatInfo"

} \],

\[ { "Currency" : null,

"Format" : null,

"Precision" : -1,

"\_\_type" : "Microsoft.Office.Access.Services.UI.FormatInfo"

} \]

\],

"IsAnonymous" : false,

"Localized" : \[ \[ null,

null,

null

\] \],

"Paging" : { "CacheCommands" : 0,

"Filter" : null,

"FirstRow" : 0,

"Moniker" : null,

"PageSize" : 1,

"SessionId" : "36.31b40d30-46c9-4850-9546-3ac936024abd163.1.V22.51RMVPQFdeHSB2Ag5Mm53S90.5.en-US5.en-US73.+0480\#0000-11-00-01T02:00:00:0000\#+0000\#0000-03-00-02T02:00:00:0000\#-006036.00000000-0000-0000-0000-0000000000001.U",

"SortExpression" : "&lt;Ordering xmlns=\\"http://schemas.microsoft.com/office/accessservices/2010/12/application\\" &gt;&lt;Order Name=\\"FirstName\\" Direction=\\"Ascending\\" /&gt;&lt;/Ordering&gt;",

"TotalRows" : 1,

"UseCache" : true,

"\_\_type" : "Microsoft.Office.Access.Services.UI.PagingInfo"

},

"RecordStatuses" : null,

"Values" : \[ \[ 1,

"First Name",

"Last Name"

\] \]

},

"\_\_type" : "Microsoft.Office.Access.Services.UI.ServiceResult"

1.  } }

<!-- -->

1.  <span id="section_48a54a50bb5541efa63990081e9e348f" class="anchor"><span id="_Toc445116603" class="anchor"></span></span>Security
    =================================================================================================================================

    1.  <span id="section_23d93042067e46f2aa41093499969a25" class="anchor"><span id="_Toc445116604" class="anchor"></span></span>Security Considerations for Implementers
        -----------------------------------------------------------------------------------------------------------------------------------------------------------------

In addition to the security considerations applicable to the underlying protocols, there are security risks associated with exposing [**session identifiers**](#gt_95849ec1-2a77-48db-816f-187fdd7c992a). If a session identifier is exposed, it is possible for an attacker to read information from, or modify data in, a session on the protocol server. An implementer of this protocol needs to consider keeping session identifiers protected. There could be some cases where it is desirable to expose a session identifier, however, an implementer is to use caution in how they expose session identifiers and consider the security risks.

<span id="section_8812a29bd3674a648014b0973a50c35f" class="anchor"><span id="_Toc445116605" class="anchor"></span></span>Index of Security Parameters
-----------------------------------------------------------------------------------------------------------------------------------------------------

None.

<span id="section_96cf1baab7154b2cb70771faaad84b66" class="anchor"><span id="_Toc445116606" class="anchor"></span></span>Appendix A: Full JSON ABNF
===================================================================================================================================================

1.  ClientMessage = json-object

    MessageID = json-quotation-mark "MessageID" json-quotation-mark json-name-separator  ClientMessageID

    Context =  json-quotation-mark "Context" json-quotation-mark json-name-separator  JsonArrayOfAnyType

    CurrentUserPermissions = json-object

    Read = json-quotation-mark "Read" json-quotation-mark json-name-separator  json-bool

    Write = json-quotation-mark "Write" json-quotation-mark json-name-separator  json-bool

    Author = json-quotation-mark "Author" json-quotation-mark json-name-separator  json-bool

    IsAuthenticated = json-quotation-mark "IsAuthenticated" json-quotation-mark json-name-separator  json-bool

    FieldSchema = json-object

    ColumnName = json-quotation-mark "ColumnName" json-quotation-mark json-name-separator json-string

    DataType = json-quotation-mark " DataType" json-quotation-mark json-name-separator json-string

    DefaultValue = json-quotation-mark "DefaultValue" json-quotation-mark json-name-separator json-string

    IsKey = json-quotation-mark "IsKey" json-quotation-mark json-name-separator json-bool

    Required = json-quotation-mark "Required" json-quotation-mark json-name-separator json-bool

    ReadOnly = json-quotation-mark " ReadOnly" json-quotation-mark json-name-separator json-bool

    MaxLength = json-quotation-mark "MaxLength" json-quotation-mark json-name-separator json-int

    DefaultExpression = json-quotation-mark "DefaultExpression" json-quotation-mark json-name-separator json-string

    ValidationScript = json-quotation-mark "ValidationScript" json-quotation-mark json-name-separator  json-string

    ValidationMessage = json-quotation-mark "ValidationMessage" json-quotation-mark json-name-separator ClientMessage

    KeyIndex = json-quotation-mark "KeyIndex" json-quotation-mark json-name-separator json-int

    SourceObject = json-quotation-mark "SourceObject" json-quotation-mark json-name-separator json-string

    DependentFields = json-quotation-mark "DependentFields" json-quotation-mark json-name-separator JsonArrayOfInt

    AllowMultipleValues = json-quotation-mark "AllowMultipleValues" json-quotation-mark json-name-separator json-bool

    FormatString = json-quotation-mark "FormatString" json-quotation-mark json-name-separator json-string

    CurrencySymbol = json-quotation-mark "CurrencySymbol" json-quotation-mark json-name-separator json-string

    DecimalPlaces = json-quotation-mark "DecimalPlaces" json-quotation-mark json-name-separator json-int

    TextType = json-quotation-mark "TextType" json-quotation-mark json-name-separator json-string

    IsTableQueryLookup = json-quotation-mark "IsTableQueryLookup" json-quotation-mark json-name-separator json-bool

    LookupSource = json-quotation-mark "LookupSource" json-quotation-mark json-name-separator json-string

    LookupBoundField = json-quotation-mark "LookupBoundField" json-quotation-mark json-name-separator json-string

    LookupDisplayField = json-quotation-mark "LookupDisplayField" json-quotation-mark json-name-separator json-string

    FilterInfo = json-object

    Culture = json-quotation-mark "Culture" json-quotation-mark json-name-separator  json-string

    Expression =  json-quotation-mark "Expression" json-quotation-mark json-name-separator  json-string

    Fields = json-quotation-mark "Fields" json-quotation-mark json-name-separator  JsonArrayOfStrings

    Text = json-quotation-mark "Text" json-quotation-mark json-name-separator json-string

    FixupRecord = json-object

    Key = json-quotation-mark "Key" json-quotation-mark json-name-separator json-string

    SupportingFieldIndexes = json-quotation-mark "SupportingFieldIndexes" json-quotation-mark json-name-separator JsonArrayOfInt

    SupportingFieldValues = json-quotation-mark "SupportingFieldValues" json-quotation-mark json-name-separator JsonArrayOfString

    FormatInfo = json-object

    Currency = json-quotation-mark "Currency" json-quotation-mark json-name-separator json-string

    Format = json-quotation-mark "Format" json-quotation-mark json-name-separator json-string

    Precision = json-quotation-mark "Precision" json-quotation-mark json-name-separator json-int

    PagingInfo = json-object

    FirstRow = json-quotation-mark "FirstRow" json-quotation-mark json-name-separator json-int

    PageSize = json-quotation-mark "PageSize" json-quotation-mark json-name-separator json-int

    Moniker = json-quotation-mark "Moniker" json-quotation-mark json-name-separator (json-string / json-null)

    UseCache = json-quotation-mark "UseCache" json-quotation-mark json-name-separator json-bool

    CacheCommands = json-quotation-mark "CacheCommands" json-quotation-mark json-name-separator CacheCommands

    SortExpression = json-quotation-mark "SortExpression" json-quotation-mark json-name-separator json-string

    Filter = json-quotation-mark "Filter" json-quotation-mark json-name-separator FilterInfo

    TotalRows = json-quotation-mark "TotalRows" json-quotation-mark json-name-separator json-int

    SessionId = json-quotation-mark "SessionId" json-quotation-mark json-name-separator json-string

    RetrieveExactRowCount = json-quotation-mark "RetrieveExactRowCount" json-quotation-mark json-name-separator json-bool

    RowKey = json-quotation-mark "RowKey" json-quotation-mark json-name-separator json-int

    ParameterValue = json-object

    Name = json-quotation-mark "Name" json-quotation-mark json-name-separator json-string

    Value = json-quotation-mark "Value" json-quotation-mark json-name-separator json-value

    RecordSet = json-object

    Values = json-quotation-mark "Values" json-quotation-mark json-name-separator JsonArrayOfArrayOfAnyType

    Localized = json-quotation-mark "Localized" json-quotation-mark json-name-separator JsonArrayOfArrayOfArrayOfString

    Paging = json-quotation-mark "Paging" json-quotation-mark json-name-separator PagingInfo

    Fields = json-quotation-mark " Fields" json-quotation-mark json-name-separator json-begin-array \[FieldSchema \*( json-value-separator FieldSchema) \] json-end-array

    FormatInfos = json-quotation-mark "FormatInfos" json-quotation-mark json-name-separator json-begin-array \[FormatInfo \*( json-value-separator FormatInfo) \] json-end-array

    AutoSumValues = json-quotation-mark "AutoSumValues" json-quotation-mark json-name-separator JsonArrayOfAnyType

    CurrentUserPermissions = json-quotation-mark "CurrentUserPermissions" json-quotation-mark json-name-separator CurrentUserPermissions

    RelatedFieldInfos = json-quotation-mark "RelatedFieldInfos" json-quotation-mark json-name-separator json-begin-array \[FieldSchema \*( json-value-separator FieldSchema) \] json-end-array

    ServiceError = json-object

    Message = json-quotation-mark "Message" json-quotation-mark json-name-separator ClientMessage

    Caption = json-quotation-mark "Caption" json-quotation-mark json-name-separator (json-string / json-null)

    HelpText = json-quotation-mark "HelpText" json-quotation-mark json-name-separator (json-string / json-null)

    HelpId = json-quotation-mark "HelpId" json-quotation-mark json-name-separator (json-string / json-null)

    Severity = json-quotation-mark "Severity" json-quotation-mark json-name-separator MessageSeverity

    Number = json-quotation-mark "Number" json-quotation-mark json-name-separator json-value

    ServiceResult = json-object

    Result = json-quotation-mark "Result" json-quotation-mark json-name-separator json-value

    Error = json-quotation-mark "Error" json-quotation-mark json-name-separator ServiceError

    SharedDataBaseInfo = json-object

    SessionId = json-quotation-mark "SessionId" json-quotation-mark json-name-separator (json-string | json-null)

    SelectCommand = json-quotation-mark "SelectCommand" json-quotation-mark json-name-separator (json-string | json-null)

    ParameterValues = json-quotation-mark "ParameterValues" json-quotation-mark json-name-separator json-begin-array \[ParameterValue \*( json-value-separator ParameterValue) \] json-end-array

    OriginalCommand = json-quotation-mark "OriginalCommand" json-quotation-mark json-name-separator (json-string | json-null)

    AggregateExpressions = json-quotation-mark "AggregateExpressions" json-quotation-mark json-name-separator (json-string | json-null)

    AggregateFormatInfos = json-quotation-mark "AggregateFormatInfos" json-quotation-mark json-name-separator json-begin-array \[FormatInfo \*( json-value-separator FormatInfo) \] json-end-array

    Restriction = json-quotation-mark "Restriction" json-quotation-mark json-name-separator (json-string | json-null)

    Ordering = json-quotation-mark "Ordering" json-quotation-mark json-name-separator (json-string | json-null)

    AllowEdits = json-quotation-mark "AllowEdits" json-quotation-mark json-name-separator (json-string | json-null)

    AllowAdditions = json-quotation-mark "AllowAdditions" json-quotation-mark json-name-separator (json-string | json-null)

    AllowDeletions = json-quotation-mark "AllowDeletions" json-quotation-mark json-name-separator (json-string | json-null)

    DataEntry = json-quotation-mark "DataEntry" json-quotation-mark json-name-separator json-bool

    FieldNames = json-quotation-mark "FieldNames" json-quotation-mark json-name-separator (json-string | json-null)

    FormatInfos = json-quotation-mark "FormatInfos" json-quotation-mark json-name-separator json-begin-array \[FormatInfo \*( json-value-separator FormatInfo) \] json-end-array

    DataLevelFormat = json-quotation-mark "DataLevelFormat" json-quotation-mark json-name-separator json-bool

    ShowHeaders = json-quotation-mark "ShowHeaders" json-quotation-mark json-name-separator json-bool

    InitialPage = json-quotation-mark "InitialPage" json-quotation-mark json-name-separator (json-string | json-null)

    FetchSchema = json-quotation-mark "FetchSchema" json-quotation-mark json-name-separator json-bool

    FetchKeyFields = json-quotation-mark "FetchKeyFields" json-quotation-mark json-name-separator json-bool

    FetchDisplayFields = json-quotation-mark "FetchDisplayFields" json-quotation-mark json-name-separator json-bool

    DoNotPrefetchImages = json-quotation-mark "DoNotPrefetchImages" json-quotation-mark json-name-separator json-bool

    AutoSumFields = json-quotation-mark "AutoSumFields" json-quotation-mark json-name-separator JsonArrayOfString

    AutoSumFunctions = json-quotation-mark "AutoSumFunctions" json-quotation-mark json-name-separator JsonArrayOfString

    UpdateRecord = json-object

    OriginalValues = json-quotation-mark "OriginalValues" json-quotation-mark json-name-separator JsonArrayOfArrayOfAnyType

    NewValues = json-quotation-mark "NewValues" json-quotation-mark json-name-separator JsonArrayOfArrayOfString

    Paging = json-quotation-mark "Paging" json-quotation-mark json-name-separator PagingInfo

    ReturnDataMacroIds = json-quotation-mark "ReturnDataMacroIds" json-quotation-mark json-name-separator json-bool

    CacheCommands = json-int

    ClientMessageID = json-string

    MessageSeverity = json-string

    GetDataRequest = dataBaseInfo-member pagingInfo-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    pagingInfo-member = json-quotation-mark "pagingInfo" json-quotation-mark json-name-separator PagingInfo

    GetDataResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

    InsertRecordsRequest = dataBaseInfo-member updateRecord-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    InsertRecordsResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

    UpdateRecordsRequest = dataBaseInfo-member updateRecord-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    updateRecord-member = json-quotation-mark "updateRecord" json-quotation-mark json-name-separator UpdateRecord

    UpdateRecordsResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

    DeleteRecordsRequest = dataBaseInfo-member updateRecord-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    updateRecord-member = json-quotation-mark "updateRecord" json-quotation-mark json-name-separator UpdateRecord

    DeleteRecordsResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

    GetDistinctValuesRequest = dataBaseInfo-member columnName-member pagingInfo-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    columnName-member = json-quotation-mark "columnName" json-quotation-mark json-name-separator json-string

    pagingInfo-member = json-quotation-mark "pagingInfo" json-quotation-mark json-name-separator PagingInfo

    GetDistinctValuesResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

    FixupRowRequest = dataBaseInfo-member fixupRecord-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    fixupRecord-member = json-quotation-mark "fixupRecord" json-quotation-mark json-name-separator FixupRecord

    FixupRowResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

    GetSearchDataRequest = dataBaseInfo-member

    dataBaseInfo-member = json-quotation-mark "dataBaseInfo" json-quotation-mark json-name-separator SharedDataBaseInfo

    GetSearchDataResult = json-null | serviceResult-member

    serviceResult-member = json-quotation-mark "d" json-quotation-mark json-name-separator ServiceResult

<span id="section_28b28c0cae6741eeb8ad30b1dcd85667" class="anchor"><span id="_Toc445116607" class="anchor"></span></span>Appendix B: Product Behavior
=====================================================================================================================================================

The information in this specification is applicable to the following Microsoft products or supplemental software. References to product versions include released service packs.

-   Microsoft Access 2013

-   Microsoft SharePoint Server 2013

-   Microsoft Access 2016

-   Microsoft SharePoint Server 2016

Exceptions, if any, are noted below. If a service pack or Quick Fix Engineering (QFE) number appears with the product version, behavior changed in that service pack or QFE. The new behavior also applies to subsequent service packs of the product unless otherwise specified. If a product edition appears with the product version, behavior is different in that product edition.

Unless otherwise specified, any statement of optional behavior in this specification that is prescribed using the terms SHOULD or SHOULD NOT implies product behavior in accordance with the SHOULD or SHOULD NOT prescription. Unless otherwise specified, the term MAY implies that the product does not follow the prescription.

<span id="section_9998f008c5d9488383a537ef6bb86ebc" class="anchor"><span id="_Toc445116608" class="anchor"></span></span>Change Tracking
========================================================================================================================================

This section identifies changes that were made to this document since the last release. Changes are classified as New, Major, Minor, Editorial, or No change.

The revision class **New** means that a new document is being released.

The revision class **Major** means that the technical content in the document was significantly revised. Major changes affect protocol interoperability or implementation. Examples of major changes are:

-   A document revision that incorporates changes to interoperability requirements or functionality.

-   The removal of a document from the documentation set.

The revision class **Minor** means that the meaning of the technical content was clarified. Minor changes do not affect protocol interoperability or implementation. Examples of minor changes are updates to clarify ambiguity at the sentence, paragraph, or table level.

The revision class **Editorial** means that the formatting in the technical content was changed. Editorial changes apply to grammatical, formatting, and style issues.

The revision class **No change** means that no new technical changes were introduced. Minor editorial and formatting changes may have been made, but the technical content of the document is identical to the last released version.

Major and minor changes can be described further using the following change types:

-   New content added.

-   Content updated.

-   Content removed.

-   New product behavior note added.

-   Product behavior note updated.

-   Product behavior note removed.

-   New protocol syntax added.

-   Protocol syntax updated.

-   Protocol syntax removed.

-   New content added due to protocol revision.

-   Content updated due to protocol revision.

-   Content removed due to protocol revision.

-   New protocol syntax added due to protocol revision.

-   Protocol syntax updated due to protocol revision.

-   Protocol syntax removed due to protocol revision.

-   Obsolete document removed.

Editorial changes are always classified with the change type **Editorially updated**.

Some important terms used in the change type descriptions are defined as follows:

-   **Protocol syntax** refers to data elements (such as packets, structures, enumerations, and methods) as well as interfaces.

-   **Protocol revision** refers to changes made to a protocol that affect the bits that are sent over the wire.

The changes made to this document are listed in the following table. For more information, please contact <dochelp@microsoft.com>.

| Section                                                                     | Tracking number (if applicable) and description | Major change (Y or N) | Change type                               |
|-----------------------------------------------------------------------------|-------------------------------------------------|-----------------------|-------------------------------------------|
| [7](#Section_28b28c0cae6741eeb8ad30b1dcd85667) Appendix B: Product Behavior | Updated list of supported products.             | Y                     | Content updated due to protocol revision. |
| 7 Appendix B: Product Behavior                                              | Updated list of supported products.             | Y                     | Content updated due to protocol revision. |

<span id="section_619e6fa1f578443d89a947311a5cd43a" class="anchor"><span id="_Toc445116609" class="anchor"></span></span>Index
==============================================================================================================================

A

Abstract data model

[server](#section_87227a78be1246b3b49414d9e1e7c416) 27

[Applicability](#section_8fb8a66e01244c06a8d474ed16d0130e) 7

C

[Capability negotiation](#section_c82d8de0685f411987e9a2ed1b1184d7) 8

[Change tracking](#section_9998f008c5d9488383a537ef6bb86ebc) 58

[Complex types](#section_5ef9e8f98cc844158994cb7c5d6f2b1e) 10

D

Data model – abstract

[server](#section_87227a78be1246b3b49414d9e1e7c416) 27

[DeleteRecords service operation example](#section_c3ad0c7c9a1f49e38359da4d68257509) 47

E

Events

timer – server

[session timeout](#section_7ace28d63235440e9e5171c695ee305a) 40

Examples

[DeleteRecords service operation](#section_c3ad0c7c9a1f49e38359da4d68257509) 47

[DeleteRecords Service Operation example](#section_c3ad0c7c9a1f49e38359da4d68257509) 47

[GetData service operation](#section_8a35d4b8dedc4d648c12cf778e301d20) 41

[GetData Service Operation example](#section_8a35d4b8dedc4d648c12cf778e301d20) 41

[InsertRecords service operation](#section_0bb3d689a4fe45e88a372ca5a9843dad) 43

[InsertRecords Service Operation example](#section_0bb3d689a4fe45e88a372ca5a9843dad) 43

[UpdateRecords service operation](#section_0c3904c915bc4818baa68674636e91cb) 45

[UpdateRecords Service Operation example](#section_0c3904c915bc4818baa68674636e91cb) 45

F

[Fields - vendor-extensible](#section_7493a5f5ec934fd69048b12250b58d83) 8

G

[GetData service operation example](#section_8a35d4b8dedc4d648c12cf778e301d20) 41

[Glossary](#section_46b952aeeb1043c7971ad5ab0a0386dc) 5

I

[Implementer - security considerations](#section_23d93042067e46f2aa41093499969a25) 50

[Index of security parameters](#section_8812a29bd3674a648014b0973a50c35f) 50

[Informative references](#section_8da12ec75c284eb29d53346df1239938) 6

[InsertRecords service operation example](#section_0bb3d689a4fe45e88a372ca5a9843dad) 43

[Introduction](#section_fe694013d9d84727b4e6f88e417d4de3) 5

M

Message processing

[server](#section_da3d178827fa4328bb37f77d8349a7f1) 27

Messages

[complex types](#section_5ef9e8f98cc844158994cb7c5d6f2b1e) 10

[simple types](#section_55121303aee2478c92d3b5aa08737a1f) 22

[syntax](#section_1e211795f3c0470bbe90757a76a3f05c) 9

[transport](#section_0d6e56cfd12f40e4a67cfcdde6ba3f2c) 9

N

[Normative references](#section_30be68b021e44bb5a9be36fe35695688) 6

O

[Overview (synopsis)](#section_5282b034621d4d659f990994de1fd9ed) 7

P

[Parameters - security index](#section_8812a29bd3674a648014b0973a50c35f) 50

[Preconditions](#section_ffd0658f6a9a483aae65d8aa70e127a2) 7

[Prerequisites](#section_ffd0658f6a9a483aae65d8aa70e127a2) 7

[Product behavior](#section_28b28c0cae6741eeb8ad30b1dcd85667) 57

Protocol Details

[Server](#section_e9fb58d578d945088004776294b33914) 27

Protocol examples

[DeleteRecords Service Operation](#section_c3ad0c7c9a1f49e38359da4d68257509) 47

[GetData Service Operation](#section_8a35d4b8dedc4d648c12cf778e301d20) 41

[InsertRecords Service Operation](#section_0bb3d689a4fe45e88a372ca5a9843dad) 43

[UpdateRecords Service Operation](#section_0c3904c915bc4818baa68674636e91cb) 45

R

References

[informative](#section_8da12ec75c284eb29d53346df1239938) 6

[normative](#section_30be68b021e44bb5a9be36fe35695688) 6

[Relationship to other protocols](#section_77723f42041e40e9bb970755c46eb887) 7

S

Security

[implementer considerations](#section_23d93042067e46f2aa41093499969a25) 50

[parameter index](#section_8812a29bd3674a648014b0973a50c35f) 50

Server

[Abstract data model](#section_87227a78be1246b3b49414d9e1e7c416) 27

[Higher-layer triggered events](#section_575d52e15c7e4b83b3e958f24e96342a) 27

[Initialization](#section_47ba0f6d247045f1a8ade432e5ebd19f) 27

[message processing](#section_da3d178827fa4328bb37f77d8349a7f1) 27

[Message processing events and sequencing rules](#section_da3d178827fa4328bb37f77d8349a7f1) 27

[Other local events](#section_6450a57666ee46ca95fac480b045d2c8) 40

[sequencing rules](#section_da3d178827fa4328bb37f77d8349a7f1) 27

timer events

[session timeout](#section_7ace28d63235440e9e5171c695ee305a) 40

[Timers](#section_2be35f1bc0634612b7ed9758390348d6) 27

[Session timeout](#section_7ace28d63235440e9e5171c695ee305a) 40

[Simple types](#section_55121303aee2478c92d3b5aa08737a1f) 22

[Standards assignments](#section_4598ffb2570849f0be8451a17b822a04) 8

[Syntax](#section_1e211795f3c0470bbe90757a76a3f05c) 9

T

Timer events

server

[session timeout](#section_7ace28d63235440e9e5171c695ee305a) 40

Timers

[server](#section_2be35f1bc0634612b7ed9758390348d6) 27

[Tracking changes](#section_9998f008c5d9488383a537ef6bb86ebc) 58

[Transport](#section_0d6e56cfd12f40e4a67cfcdde6ba3f2c) 9

Types

[complex](#section_5ef9e8f98cc844158994cb7c5d6f2b1e) 10

[simple](#section_55121303aee2478c92d3b5aa08737a1f) 22

U

[UpdateRecords service operation example](#section_0c3904c915bc4818baa68674636e91cb) 45

V

[Vendor-extensible fields](#section_7493a5f5ec934fd69048b12250b58d83) 8

[Versioning](#section_c82d8de0685f411987e9a2ed1b1184d7) 8

<span id="EndOfDocument_ST" class="anchor"></span>
