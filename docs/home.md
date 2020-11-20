# Welcome to the FIXM User Manual

The FIXM User Manual, formerly known as *Implementation Guidance*, is developed and maintained by the FIXM Community. Content has been subject to FIXM CCB review and endorsement and is therefore the official recommendation of the FIXM CCB. 

*Note: The content of this user manual is informative. The use of the words `shall` or `required` indicates a requirement to be strictly followed in order to conform to this guidance. The use of the words `should` or `recommended` indicates that there may may be valid reasons, in particular circumstances, to ignore a particular aspect of the guidance.*

## Guidance on  FIXM Releases

| FIXM Release | FIXM Application | User Manual | Schema Documentation |
|:-|:-|:-|:-----|
| **[FIXM Core 4.2.0](https://fixm.aero/release.pl?rel=FIXM-4.2.0)**<br><br><br> | **<br>[FF-ICE Application 1.0.0](https://fixm.aero/release.pl?rel=FFICE-Msg-1.0.0)**<br>**[Basic Application 1.0.0](https://fixm.aero/release.pl?rel=Basic-Msg-1.0.0)** | **[HTML](home "This web site")**, [PDF](tbd.pdf "Download the contents of this web site as a PDF file")<br><br><br> | [HTML](https://fixm.aero/releases/FIXM-4.2.0/doc/schema_documentation/Fixm.html)<br>[HTML](https://fixm.aero/releases/FFICE-Msg-1.0.0/doc/schema_documentation/ffice_message/FficeMessage.html "View FIXM FF-ICE Message v1.0.0 Schema Documentation"), [HTML](https://www.fixm.aero/releases/FFICE-Msg-1.0.0/doc/schema_documentation/ffice_templates/FficeTemplates.html "View FIXM FF-ICE Message v1.0.0 Templates Schema Documentation")<br>[HTML](https://fixm.aero/releases/Basic-Msg-1.0.0/doc/schema_documentation/BasicMessage.html) | [HTML](https://fixm.aero/releases/Basic-Msg-1.0.0/doc/schema_documentation/BasicMessage.html) |
| *[FIXM Core 4.1.0](https://fixm.aero/release.pl?rel=FIXM-4.1.0)* | - | *[ZIP](https://www.fixm.aero/documents/FIXM%20Implementation%20Guidance_FIXM%20v4.1.0.zip)* | *[HTML](https://fixm.aero/releases/FIXM-4.1.0/doc/schema_documentation_core/index.html)* |

## Content and Target audience

- The part [GENERAL GUIDANCE](general-guidance/fixm-core) provides explanations about the main FIXM components and describes the general rules (encoding rules, data plausibility rules, rules for absent data…) that are always applicable whatever the implementation context.
- The part [USING FIXM IN SUPPORT OF FF-ICE](fixm-in-support-of-ffice/ffice-application-for-fixm) provides specific guidance in support of the implementation of FF-ICE using FIXM.
- The part [USING FIXM FOR OTHER USE CASES](fixm-for-other-use-cases/using-fixm-core-without-an-application) provides explanations and guidance for implementing FIXM in support of use cases not handled the FIXM CCB.
- The "How to" parts [HOW TO CREATE A FIXM APPLICATION](how-to-create-application/initial-download-and-setup), [HOW TO CREATE A FIXM EXTENSION](how-to-create-fixm-extension/initial-download-and-setup) and [HOW TO GENERATE XML SCHEMAS ...](how-to-generate-xml-schemas/generating-schemas-from-the-logical-model) provide step-by-step guidance for producing new FIXM Applications and FIXM extensions (UML and XSD).
- The part [FIXM DEVELOPMENT TOOL COMPATIBILITY](fixm-development-tool-compatibility/introduction) provides information about the tools and technologies for which compability tests have been performed for FIXM.

| Your FIXM use case | Chapters relevant to you |
|:-|:---|
| I want to use FIXM to implement ICAO FF-ICE Service(s) without local/regional arrangements | [GENERAL GUIDANCE](general-guidance/fixm-core), [FIXM DEVELOPMENT TOOL COMPATIBILITY](fixm-development-tool-compatibility/introduction), [USING FIXM IN SUPPORT OF FF-ICE](fixm-in-support-of-ffice/ffice-application-for-fixm) |
| I want to use FIXM to implement ICAO FF-ICE Service(s) with local/regional arrangements | [GENERAL GUIDANCE](general-guidance/fixm-core), [FIXM DEVELOPMENT TOOL COMPATIBILITY](fixm-development-tool-compatibility/introduction), [USING FIXM IN SUPPORT OF FF-ICE](fixm-in-support-of-ffice/ffice-application-for-fixm), [HOW TO CREATE A FIXM APPLICATION](how-to-create-application/initial-download-and-setup), [HOW TO CREATE A FIXM EXTENSION](how-to-create-fixm-extension/initial-download-and-setup), [HOW TO GENERATE XML SCHEMAS ...](how-to-generate-xml-schemas/generating-schemas-from-the-logical-model)|
| I want to use FIXM to exchange flight data based on my own organisation's needs | [GENERAL GUIDANCE](general-guidance/fixm-core), [FIXM DEVELOPMENT TOOL COMPATIBILITY](fixm-development-tool-compatibility/introduction), [USING FIXM FOR OTHER USE CASES](fixm-for-other-use-cases/using-fixm-core-without-an-application), [HOW TO CREATE A FIXM APPLICATION](how-to-create-application/initial-download-and-setup), [HOW TO CREATE A FIXM EXTENSION](how-to-create-fixm-extension/initial-download-and-setup), [HOW TO GENERATE XML SCHEMAS ...](how-to-generate-xml-schemas/generating-schemas-from-the-logical-model) |

## Contribute

This sites aims to build a "community knowledge" about the implementation of FIXM. You can contribute to its evolution by submitting content and by supporting the technical exchanges of the FIXM Community using the FIXM Work Area.

- [SUBMIT CONTENT][SUBMIT CONTENT]
- [ACCESS THE FIXM WORK AREA][ACCESS THE FIXM WORK AREA]

?> No access yet to the FIXM Work Area? Register now!

1. Create a OneSky Online account (*This step can be skipped if you have already an account*) : Access [OneSky Online][OneSky Online], click on `New user? Register now.`, fill in the form and click on `Submit`
2. Get access to OneSky Teams: Access [OneSky Teams][OneSky Teams], and log in with your credentials obtained in Step 1
3. Request access to the FIXM Work Area: Click on `All Teams` in the top navigation, browse for the FIXM Work Area and click on its title, click on `Access can be requested via this link`, and send the access request.
4. You will then receive an email when the request is approved, with the link to the FIXM Work Area

## How to use this web site

- Use the side bar opposite to access the various sections of the user manual;
- Use the search engine to look for a specific entry;
- Use the buttons `< Previous` and `Next >` at the bottom of each page to navigate across the different sections of the manual.

## References

### FIXM references

[1]: [FIXM Strategy v1.1](https://fixm.aero/documents/FIXM%20Strategy.pdf)

[2]: [FIXM web site](https://fixm.aero/)

[3]: [FIXM Work Area](https://ost.eurocontrol.int/sites/FIXM/SitePages/Home.aspx)

### ICAO references

[4]: PANS-ATM: Procedures for Air Navigation Services: Air Traffic Management, ICAO Doc 4444, 16th edition

[5]: [ICAO Doc 9965](http://www.icao.int/Meetings/anconf12/Documents/9965_cons_en.pdf): Manual on Flight and Flow Information for a Collaborative Environment

[6]: [ATMRPP/3-WP/766](https://ost.eurocontrol.int/sites/FIXM/Shared%20Documents/ICAO%20ATMRPP%20inputs%20for%20FIXM%204.1.0/ATMRPP3_WP_766_FF-ICE1%20Implementation%20Guidance_All.pdf): “Manual on FF-ICE Implementation Guidance”

[7]: ICAO Doc 7910: Location Indicators

[8]: [ICAO Doc 8643](https://www.icao.int/publications/DOC8643/Pages/default.aspx): Aircraft Type Designators

[9]: PAN AIDC ICD: PAN Regional (NAT and APAC) Interface Control Document for ATC Interfacility Data Communications (PAN AIDC ICD), version 1.0

[10]: ICAO Doc 10039: Manual on System Wide Information Management (SWIM) Concept

[11]: ATMRPP-WG/24-WP/564: Flight Plan Filing Provisions for FF-ICE

### Other references

[12]: [Donlon AIP data Set](https://github.com/aixm/donlon): a fictitious set of digital AIS data sets complying with the ICAO Annex 15, 16th edition and the new PANS-AIM provisions, in AIXM 5.1.1 format.

[13]: [W3C XML Linking Language (xlink) v1.1](https://www.w3.org/TR/xlink11/)

## Acronyms

| **Acronym** |                                                                          |
|-------------|--------------------------------------------------------------------------|
| AIDC             | ATS Interfacility Data Communications |
| AIP       | Aeronautical information publication |
| AIRM     | ATM Information Reference Model |
| AIS       | Aeronautical information services |
| AIXM    | Aeronautical Information Exchange Model |
| AMDB     | Aerodrome Mapping Database |
| AMXM             | Aerodrome Mapping Exchange Model |
| ATM       | Air Traffic Management |
| ATMRPP           | ATM Requirements and Performance Panel |
| ATS       | Air Traffic Services |
| CCB              | Change Control Board |
| DME      | Distance measuring equipment |
| EAD              | European AIS Database |
| FF-ICE | Flight and Flow Information for a Collaborative Environment |
| FF-ICE/R1        | FF-ICE Release 1 |
| FIXM     | Flight Information Exchange Model |
| FPL      | Filed Flight Plan |
| GML              | Geography Markup Language |
| GUFI    | Globally Unique Flight Identifier |
| ICAO     | International Civil Aviation Organisation |
| IDE              | Integrated development environment |
| IFPS    | Integrated Initial Flight Plan Processing System |
| IFR      | Instrument Flight Rules |
| ISO       | International Organization for Standardization |
| JMS              | Java Message Service |
| MSL       | Mean sea level |
| NAS (US) | (US) National Airspace System |
| Navaid | Navigational Aid |
| NDB       | Non-directional radio beacon |
| NM (EUROCONTROL) | (EUROCONTROL) Network Manager |
| OGC      | Open Geospatial Consortium |
| PBN       | Performance Based Navigation |
| REST             | Representational state transfer |
| SID       | Standard Instrument Departure |
| SOAP             | Simple Object Access Protocol |
| SSR       | Secondary Surveillance Radar |
| STAR     | Standard instrument arrival |
| SWIM     | System Wide Information Management |
| UML       | Unified Modeling Language |
| UPR       | User Preferred Route |
| URL              | Uniform Resource Locator |
| UTC     | Coordinated Universal Time |
| UUID             | Universally unique identifier |
| VFR       | Visual Flight Rules |
| VOR     | VHF omnidirectional radio range |
| W3C      | World Wide Web Consortium |
| WGS-84 | World Geodetic System - 1984 |
| WSDL             | Web Services Description Language |
| XML              | Extensible Markup Language |
| XSD              | XML Schema Definition |
| XSLT             | Extensible Stylesheet Language Transformations |

[FIXM Core 4.2.0]: https://www.fixm.aero/release.pl?rel=FIXM-4.2.0
[FF-ICE Application]: https://www.fixm.aero/release.pl?rel=FFICE-Msg-1.0.0
[Basic Application]: https://www.fixm.aero/release.pl?rel=Basic-Msg-1.0.0

[OneSky Online]: https://ext.eurocontrol.int/
[OneSky Teams]: https://ost.eurocontrol.int/Pages/default.aspx
[ACCESS THE FIXM WORK AREA]: https://ost.eurocontrol.int/sites/FIXM/SitePages/Home.aspx
[SUBMIT CONTENT]: https://www.fixm.aero/content/contact.pl?category=Technical&version=Other&versionOther=FIXM%20User%20Manual&details=Describe%20proposed%20content%20here
