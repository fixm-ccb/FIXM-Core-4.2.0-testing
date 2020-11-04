# Fixm User Manual

**Implementation guidance for FIXM** developed and maintained by the FIXM Community. Content has been subject to FIXM CCB review and endorsement and is therefore the official recommendation of the FIXM CCB. 

*Note: The content of this user manual is informative. The use of the words `shall` or `required` indicates a requirement to be strictly followed in order to conform to this guidance. The use of the words `should` or `recommended` indicates that there may may be valid reasons, in particular circumstances, to ignore a particular aspect of the guidance.*

## Applicable FIXM Release

|Applicable Release| Implementation Guidance |
|:-|:--|
| **[FIXM Core 4.2.0](https://www.fixm.aero/release.pl?rel=FIXM-4.2.0)**<br>and related applications<br>- **[FF-ICE Application](https://www.fixm.aero/release.pl?rel=FFICE-Msg-1.0.0)**<br>- **[Basic Application](https://www.fixm.aero/release.pl?rel=Basic-Msg-1.0.0)** | [HTML]() (This web site)<br>[zip]()<br><br><br>|

*Note: Implementation guidance for the older FIXM Core 4.1.0 version can be downloaded as a [zip](https://www.fixm.aero/documents/FIXM%20Implementation%20Guidance_FIXM%20v4.1.0.zip) file.*

## Content and Target audience

- The part `GENERAL GUIDANCE` provides explanations about the main FIXM components and describes the general rules (encoding rules, data plausibility rules, rules for absent data…) that are always applicable whatever the implementation context.
- The part `USING FIXM IN SUPPORT OF FF-ICE` provides specific guidance in support of the implementation of FF-ICE using FIXM.
- The parts `USING FIXM FOR OTHER USE CASES`, `HOW TO CREATE A FIXM APPLICATION`, `HOW TO CREATE A FIXM EXTENSION` and `HOW TO GENERATE XML SCHEMAS ...` provide explanations and guidance for implementing FIXM in support of use cases not handled the FIXM CCB.
- The part `FIXM DEVELOPMENT TOOL COMPATIBILITY` provides a Platform Support Matrix listing the tools and technologies for which compability tests have been performed for FIXM.

| Your FIXM use case | Chapters relevant to you |
|:-|:---| 
| I want to use FIXM to implement ICAO FF-ICE Service(s) without local/regional arrangements | `GENERAL GUIDANCE`, `FIXM DEVELOPMENT TOOL COMPATIBILITY`, `USING FIXM IN SUPPORT OF FF-ICE` |
| I want to use FIXM to implement ICAO FF-ICE Service(s) with local/regional arrangements | `GENERAL GUIDANCE`, `FIXM DEVELOPMENT TOOL COMPATIBILITY`, `USING FIXM IN SUPPORT OF FF-ICE`, `HOW TO CREATE A FIXM APPLICATION`, `HOW TO CREATE A FIXM EXTENSION`, `HOW TO GENERATE XML SCHEMAS ...`|
| I want to use FIXM to exchange flight data based on my own organisation's needs | `GENERAL GUIDANCE`, `FIXM DEVELOPMENT TOOL COMPATIBILITY`, `USING FIXM FOR OTHER USE CASES`, `HOW TO CREATE A FIXM APPLICATION`, `HOW TO CREATE A FIXM EXTENSION`, `HOW TO GENERATE XML SCHEMAS ...` |


## Contribute

This sites aims to build a "community knowledge" about the implementation of FIXM. You can contribute to its evolution by submitting content and by supporting the technical exchanges of the FIXM Community using the FIXM Work Area.

- [SUBMIT CONTENT](https://www.fixm.aero/content/contact.pl?category=Technical&version=Other&versionOther=FIXM%20User%20Manual&details=Describe%20proposed%20content%20here)
- [ACCESS THE FIXM WORK AREA](https://ost.eurocontrol.int/sites/FIXM/SitePages/Home.aspx)

?> No access yet to the FIXM Work Area? Register now!

1. Create a OneSky Online account (*This step can be skipped if you have already an account*) : Access [OneSky Online](https://ext.eurocontrol.int/), click on `New user? Register now.`, fill in the form and click on `Submit`
2. Get access to OneSky Teams: Access [OneSky Teams](https://ost.eurocontrol.int/Pages/default.aspx), and log in with your credentials obtained in Step 1
3. Request access to the FIXM Work Area: Click on `All Teams` in the top navigation, browse for the FIXM Work Area and click on its title, click on `Access can be requested via this link`, and send the access request.
4. You will then receive an email when the request is approved, with the link to the FIXM Work Area

## How to use this web site

- Use the side bar opposite to access the various sections of the user manual
- Use the search to look for a specific entry
- Use the buttons `< Previous` and `Next >` at the bottom of each page to navigate across the different sections of the manual.


## References

> TODO

## Acronyms and Definitions

| **Acronym** |                                                                          |
|-------------|--------------------------------------------------------------------------|
| AIDC        | ATS Interfacility Data Communications                                    |
| AIXM        | Aeronautical Information Exchange Model                                  |
| AMXM        | Aerodrome Mapping Exchange Model                                         |
| ATM         | Air Traffic Management                                                   |
| ATMRPP      | ATM Requirements and Performance Panel                                   |
| ATS         | Air Traffic Services                                                     |
| CCB         | Change Control Board                                                     |
| FF-ICE      | Flight and Flow Information for a Collaborative Environment              |
| FIXM        | Flight Information Exchange Model                                        |
| FPL         | Flight Plan                                                              |
| GML         | Geography Markup Language                                                |
| GUFI        | Globally Unique Flight Identifier                                        |
| ICAO        | International Civil Aviation Organisation                                |
| IFR         | Instrument Flight Rules                                                  |
| ISO         | International Organization for Standardization                           |
| Navaid      | Navigational Aid                                                         |
| OGC         | Open Geospatial Consortium                                               |
| PBN         | Performance Based Navigation                                             |
| SID         | Standard Instrument Departure                                            |
| SOAP        | Simple Object Access Protocol                                            |
| SSR         | Secondary Surveillance Radar                                             |
| STAR        | Standard Terminal Arrival Route                                          |
| SWIM        | System Wide Information Management                                       |
| UPR         | User Preferred Route                                                     |
| URL         | Uniform Resource Locator                                                 |
| US NAS      | US National Airspace System                                              |
| UTC         | Coordinated Universal Time                                               |
| VFR         | Visual Flight Rules                                                      |
| WGS-84      | World Geodetic System - 1984                                             |
| WSDL        | Web Services Description Language                                        |
| XML         | Extensible Markup Language                                               |
| XSD         | XML Schema Definition                                                    |
| XSLT        | Extensible Stylesheet Language Transformations                           |

