# Fixm User Manual

!> This page requires an update. It has not been processed in the preparation of this baseline version. Please do not review the contents.

This site provides guidance and clarifications for the
implementation of FIXM.

It aims to build a "community knowledge" about the
implementation of FIXM. It will therefore evolve over time in order to
capture more alternatives, options and recommendations related to the
use of FIXM.

## Purpose and content

This document provides guidance and clarifications for the
implementation of FIXM. It aims to build a "community knowledge" about
the implementation of FIXM. It will therefore evolve over time in order
to capture more alternatives, options and recommendations related to the
use of FIXM.

The implementation guidance provided in this document is structured as
follows:

-   **General Guidance on FIXM implementation**

This chapter provides general guidance for understanding the main FIXM
components, outlines general requirements for valid FIXM core and FIXM
extensions usage and describes the general rules (encoding rules, data
plausibility rules, rules for absent data…) that are always applicable
whatever the implementation context.

-   **Guidance for Using FIXM in Support of FF-ICE**

This chapter provides specific guidance in support of the
implementation of FF-ICE using FIXM. It introduces the FF-ICE
Application, identifies a candidate set of FIXM-Based services
enabling (part of) the information exchanges defined by the ICAO
ATMRPP in the Manual on FF-ICE Implementation Guidance \[10\] and
provides detailed examples of FF-ICE/R1 Services realizations.

-   **Guidance for Translating FF-ICE FIXM Messages to ATS Messages**

This chapter defines a formal mapping between the FIXM Logical Model
and Air Traffic Services (ATS) message content as defined in ICAO Doc
4444 \[8\].

-   **Guidance for Using FIXM for other use cases**

This chapter provides guidance for using FIXM in a context other than
FF-ICE. In particular, it helps FIXM implementers create their own
application libraries and extensions.

*Note: The present version of the document captures the guidance
information agreed by the FIXM community as of March 2018. Readers are
invited to monitor the FIXM community discussions in the FIXM Work Area*
*\[6\] about the implementation of FIXM, which may serve as useful
complement or clarification.*

## Applicable FIXM version

The present version of the document supports the implementation of the
following FIXM components:

-   **FIXM Core v4.2.0** \[1\]

-   **FIXM Applications**

    -   **FF-ICE Message v1.0.0**

    -   **Basic Message v1.0.0**

**What is new in FIXM Core 4.2.0?**

At high level, the scope declaration of FIXM Core 4.2.0 is the same as
FIXM 4.1.0, namely to provide harmonised representation of the flight
data structures exchanged in the context of FF-ICE/R1. FIXM Core 4.2.0,
however, implements significant improvements compared to FIXM 4.1.0:

-   FIXM Core 4.2.0 is based on the draft FF-ICE/R1 Implementation
    Guidance Manual version 0.91, therefore reflecting a more mature -
    but yet not final - version of the FF-ICE/R1 requirements specified
    by the ICAO ATMRPP;

-   FIXM Core 4.2.0 contains more usable data structures for enabling a
    better representation of the feedback that an eAU can get from an
    eASP after submitting an FF-ICE flight plan;

-   FIXM Core 4.2.0 supports nillable properties (which FIXM 4.1.0 did
    not)[1] that enable proper FF-ICE Flight Plan updates as described
    in the FF-ICE/R1 Implementation Guidance Manual;

-   FIXM Core 4.2.0 comes together with a new FF-ICE Application
    that addresses the use of FIXM Core in the specific context of
    FF-ICE and which provides formal representation of the individual
    FF-ICE messages. A new “Basic Message” application is also available in
    order to provide basic messaging support for FIXM.

-   FIXM Core 4.2.0 also implements a number of technical improvements
    and bug corrections.

Important note: This document does not detail the individual changes
implemented in this new FIXM release. More information about these
changes can be found in the FIXM Release Note and in the online
repository of FIXM Change Requests from the FIXM Work Area. This
document rather focuses on how to use the various FIXM components and
data structures.

## Document terms

This is a guidance document describing recommended practices related to
the use and implementation of FIXM. It has been subject to FIXM CCB
review and endorsement and is therefore the official recommendation of
the FIXM CCB.

This document is, however, non-normative and requirements described in
it shall be considered mandatory only for those aiming to comply with
this guidance.

The use of the word "SHALL" or "REQUIRED" indicates an absolute
requirement of this guidance, i.e. a requirement to be strictly followed
in order to conform to this document.

The use of the word "SHOULD" or "RECOMMENDED" indicates that there may
exist valid reasons, in particular circumstances, to ignore a particular
aspect of the guidance.

## Improving this site

Suggested additions, changes and comments on this document
are welcome and encouraged. These suggestions should be sent to the [FIXM
CCB](https://fixm.aero/content/contact.pl) or posted to the FIXM Work Area.

## Acronyms and Definitions

| **Acronym** |                                                                          |
|-------------|--------------------------------------------------------------------------|
| AIDC        | ATS Interfacility Data Communications                                    |
| AIXM        | Aeronautical Information Exchange Model                                  |
| AMQP        | Advanced Message Queuing Protocol                                        |
| AMXM        | Aerodrome Mapping Exchange Model                                         |
| ASBU        | Aviation System Block Upgrade                                            |
| ASP         | ATM Service Provider                                                     |
| ATM         | Air Traffic Management                                                   |
| ATMRPP      | ATM Requirements and Performance Panel                                   |
| ATS         | Air Traffic Services                                                     |
| AU          | Airspace User                                                            |
| CCB         | Change Control Board                                                     |
| CDM         | Collaborative Decision Making                                            |
| eASP        | Enhanced ATM Service Provider (i.e. FF-ICE capable ATM service provider) |
| eAU         | Enhanced Airspace User (i.e. FF-ICE capable Airspace user)               |
| FF-ICE      | Flight and Flow Information for a Collaborative Environment              |
| FIR         | Flight Information Region                                                |
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
| R/R         | Request/Reply                                                            |
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



| **Term**           | **Definition**                                                                                                                                                                              |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| FIXM XML schemas   | The XML-based physical realization of the FIXM Logical Model                                                                                                                                |
| FIXM-based message | A message exchanged by a flight information service which has a content that satisfies the applicable FIXM requirements in terms of data structure, data completeness and data correctness. |
| FIXM-based service | A service created in accordance with the recommendations described in this guidance document.                                                                                               |

