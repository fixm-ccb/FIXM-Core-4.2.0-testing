# Welcome to the FIXM User Manual

**Implementation guidance for FIXM** developed and maintained by the FIXM Community. Content has been subject to FIXM CCB review and endorsement and is therefore the official recommendation of the FIXM CCB.

*Note: The content of this user manual is informative. The use of the words `shall` or `required` indicates a requirement to be strictly followed in order to conform to this guidance. The use of the words `should` or `recommended` indicates that there may may be valid reasons, in particular circumstances, to ignore a particular aspect of the guidance.*

## Applicable FIXM Release

|Applicable Release| Implementation Guidance |
|:-|:------|
| **[FIXM Core 4.2.0][FIXM Core 4.2.0]**<br>and related applications<br>- **[FF-ICE Application][FF-ICE Application]**<br>- **[Basic Application][Basic Application]** | [HTML]() (This web site)<br>[zip]()<br><br><br>|

*Note: Implementation guidance for the older FIXM Core 4.1.0 version can be downloaded as a [zip](https://www.fixm.aero/documents/FIXM%20Implementation%20Guidance_FIXM%20v4.1.0.zip) file.*

## Content and Target audience

- The part `GENERAL GUIDANCE` provides explanations about the main FIXM components and describes the general rules (encoding rules, data plausibility rules, rules for absent data…) that are always applicable whatever the implementation context.
- The part `USING FIXM IN SUPPORT OF FF-ICE` provides specific guidance in support of the implementation of FF-ICE using FIXM.
- The part `USING FIXM FOR OTHER USE CASES` provides explanations and guidance for implementing FIXM in support of use cases not handled the FIXM CCB.
- The "How to" parts `HOW TO CREATE A FIXM APPLICATION`, `HOW TO CREATE A FIXM EXTENSION` and `HOW TO GENERATE XML SCHEMAS ...` provide step-by-step guidance for producing new FIXM Applications and FIXM extensions (UML and XSD).
- The part `FIXM DEVELOPMENT TOOL COMPATIBILITY` provides information about the tools and technologies for which compability tests have been performed for FIXM.

| Your FIXM use case | Chapters relevant to you |
|:-|:---| 
| I want to use FIXM to implement ICAO FF-ICE Service(s) without local/regional arrangements | `GENERAL GUIDANCE`, `FIXM DEVELOPMENT TOOL COMPATIBILITY`, `USING FIXM IN SUPPORT OF FF-ICE` |
| I want to use FIXM to implement ICAO FF-ICE Service(s) with local/regional arrangements | `GENERAL GUIDANCE`, `FIXM DEVELOPMENT TOOL COMPATIBILITY`, `USING FIXM IN SUPPORT OF FF-ICE`, `HOW TO CREATE A FIXM APPLICATION`, `HOW TO CREATE A FIXM EXTENSION`, `HOW TO GENERATE XML SCHEMAS ...`|
| I want to use FIXM to exchange flight data based on my own organisation's needs | `GENERAL GUIDANCE`, `FIXM DEVELOPMENT TOOL COMPATIBILITY`, `USING FIXM FOR OTHER USE CASES`, `HOW TO CREATE A FIXM APPLICATION`, `HOW TO CREATE A FIXM EXTENSION`, `HOW TO GENERATE XML SCHEMAS ...` |


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

> TODO

## Acronyms

| **Acronym** |                                                                          |
|-------------|--------------------------------------------------------------------------|
| AIDC             | ATS Interfacility Data Communications |
| [AIP][AIP]       | Aeronautical information publication |
| [AIRM][AIRM]     | ATM Information Reference Model |
| [AIS][AIS]       | Aeronautical information services |
| [AIXM][AIXM]     | Aeronautical Information Exchange Model |
| [AMDB][AMDB]     | Aerodrome Mapping Database |
| AMXM             | Aerodrome Mapping Exchange Model |
| [ATM][ATM]       | Air Traffic Management |
| ATMRPP           | ATM Requirements and Performance Panel |
| [ATS][ATS]       | Air Traffic Services |
| CCB              | Change Control Board |
| [DME][DME]       | Distance measuring equipment |
| EAD              | European AIS Database |
| [FF-ICE][FF-ICE] | Flight and Flow Information for a Collaborative Environment |
| FF-ICE/R1        | FF-ICE Release 1 |
| [FIXM][FIXM]     | Flight Information Exchange Model |
| [FPL][FPL]       | Filed Flight Plan |
| GML              | Geography Markup Language |
| [GUFI][GUFI]     | Globally Unique Flight Identifier |
| [ICAO][ICAO]     | International Civil Aviation Organisation |
| IDE              | Integrated development environment |
| [IFPS][IFPS]     | Integrated Initial Flight Plan Processing System |
| [IFR][IFR]       | Instrument Flight Rules |
| [ISO][ISO]       | International Organization for Standardization |
| JMS              | Java Message Service |
| [MSL][MSL]       | Mean sea level |
| [NAS (US)][NAS (US)] | (US) National Airspace System |
| [Navaid][Navaid] | Navigational Aid |
| [NDB][NDB]       | Non-directional radio beacon |
| NM (EUROCONTROL) | (EUROCONTROL) Network Manager |
| [OGC][OGC]       | Open Geospatial Consortium |
| [PBN][PBN]       | Performance Based Navigation |
| REST             | Representational state transfer |
| [SID][SID]       | Standard Instrument Departure |
| SOAP             | Simple Object Access Protocol |
| [SSR][SSR]       | Secondary Surveillance Radar |
| [STAR][STAR]     | Standard instrument arrival |
| [SWIM][SWIM]     | System Wide Information Management |
| [UML][UML]       | Unified Modeling Language |
| [UPR][UPR]       | User Preferred Route |
| URL              | Uniform Resource Locator |
| [UTC][UTC]       | Coordinated Universal Time |
| UUID             | Universally unique identifier |
| [VFR][VFR]       | Visual Flight Rules |
| [VOR][VOR]       | VHF omnidirectional radio range |
| [W3C][W3C]       | World Wide Web Consortium |
| [WGS-84][WGS-84] | World Geodetic System - 1984 |
| WSDL             | Web Services Description Language |
| XML              | Extensible Markup Language |
| XSD              | XML Schema Definition |
| XSLT             | Extensible Stylesheet Language Transformations |


[FIXM Core 4.2.0]: https://www.fixm.aero/release.pl?rel=FIXM-4.2.0
[FF-ICE Application]: https://www.fixm.aero/release.pl?rel=FFICE-Msg-1.0.0
[Basic Application]: https://www.fixm.aero/release.pl?rel=Basic-Msg-1.0.0

[AIP]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#AIP
[AIRM]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#AIRM
[AIS]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#AIS
[AIXM]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#AIXM
[AMDB]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#AMDB
[ATM]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#ATM
[ATS]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#ATS
[DME]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#DME
[FF-ICE]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#FF-ICE
[FIXM]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#FIXM
[FPL]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#FPL
[GUFI]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#GUFI
[ICAO]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#ICAO
[IFPS]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#IFPS
[IFR]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#IFR
[ISO]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#ISO
[MSL]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#MSL
[NAS (US)]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#NAS
[Navaid]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#Navaid
[NDB]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#NDB
[OGC]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#OGC
[PBN]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#PBN
[SID]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#SID
[SSR]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#SSR
[STAR]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#STAR
[SWIM]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#SWIM
[UML]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#UML
[UPR]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#UPR
[UTC]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#UTC
[VFR]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#VFR
[VOR]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#VOR
[W3C]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#W3C
[WGS-84]: http://airm.aero/viewer/1.0.0/includes-supplements/contextual-model-abbreviations.html#WGS84

[OneSky Online]: https://ext.eurocontrol.int/
[OneSky Teams]: https://ost.eurocontrol.int/Pages/default.aspx
[ACCESS THE FIXM WORK AREA]: https://ost.eurocontrol.int/sites/FIXM/SitePages/Home.aspx
[SUBMIT CONTENT]: https://www.fixm.aero/content/contact.pl?category=Technical&version=Other&versionOther=FIXM%20User%20Manual&details=Describe%20proposed%20content%20here
