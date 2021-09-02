# FIXM Development Guidelines

This section provides guidelines for the development of FIXM and addresses the often-competing requirements of a forward-looking 'ideal' model and the support of legacy systems and formats during transition. The guidelines are followed in the development of FIXM and endorsed by the FIXM Change Control Board (CCB). Stakeholders are free to adopt any convention they choose when developing extensions; it is recommended that stakeholder extensions follow these guidelines. 

## Detailed Guidelines Discussion

### Content versus Presentation
The intent of FIXM is to model the information elements and structure of flight information. That is, the concern is what constitutes a flight, and how the elements relate to each other. FIXM does not dictate how that flight information is packaged, transmitted, used, or presented to human stakeholders. The physical FIXM model is encoded as Extensible Markup Language (XML). XML is aimed at system-to-system communication. While humans can read XML, it is not designed for human consumption. Certainly, a flight dispatcher or air traffic controller would never be exposed to FIXM XML. Rath er, a user interface would be provided for such stakeholders, which presents the content of the FIXM encoded flight information in an operationally meaningful manner.

FIXM reflects the modern best practice that content and presentation should be separate concerns. The benefit of such an approach is that development of FIXM can focus purely on content. Model development is not distracted by issues such as whether a FIXM encoded flight is directly understandable by a human; the concern is "what is a flight". The related Aeronautical Information Exchange Model (AIXM) and Weather Information Exchange Model (WXXM) standards for resource and environmental information exchange similarly focus on content and structure.

### Structure versus Custom Decoding
It is stated in the FF- ICE manual: "Inefficient constraints, such as fixed data length s or free text information, should be minimized."

The direction espoused by this statement is that representing flight information in a textual format which must be decoded should be avoided whenever possible. Legacy formats in aviation suffer significantly from the presence of text that needs to be decoded. In the present context this is most readily seen in field 15 (route) and various field 18 items in ATS messages. Whenever such text is present, any receiving system, to benefit from the operational content, must decode the text to extract the embedded information. In general, the ATS message information is received by multiple stake holders, and is decoded multiple times, with different systems applying different rules and logic leading to misinterpretation and ambiguity. At worst, this could lead to safety incidents.

The point in employing a formal language such as XML for the representation of information is that the structure and individual data values are delineated by the data representation format. The XML together with the associated schema precisely and unambiguously identify the structure of the information and allow the primitive data values to be easily identified. As a result, the intent of the originator of the information is clear, and the receiver is able to process the information as intended by the originator. Another example of a problematic legacy format is the Notice to Airmen (NOTAM) that often contains large areas of unstructured or semi-structured free text in the E field. Validation of the content of a NOTAM is largely a manual process due to the lack of rules around the free text E field item. AIXM explicitly addresses this problem with the introduction of the Digital NOTAM concept. The various changes to the base resource information have been analysed and codified as 'events', allowing the precise and unambiguous representation of the intent of a NOTAM.

FIXM must achieve for flight information what AIXM achieves for aeronautical resource information. As such, the inherent structure of any flight information must be made explicit in the model. Multiple values must never be coalesced into a single data element that requires a receiver to decode via custom business logic. It is acknowledged that, at times, it is advisable to allow free text items to support legacy systems during the transition to FF-ICE.


### Model and Legacy Concerns
As a result of the need to support legacy approaches during the transition to FF-ICE operations, at times it may be judicious to introduce components in the FIXM model that do not directly contribute to the FF-ICE operations, but which facilitate integration of legacy systems and formats. This may not always be consistent with a purist FIXM approach, and some guidelines are needed to help resolve such situations.

If a significant change to the model was proposed to provide a relatively small benefit for a legacy approach, we clearly would not want such a change. On the other hand, if a small change to the model provides very significant benefit for legacy systems, then there is strong justification for incorporating the change in the model. Less clear is the situation where the change to the model and the benefits to legacy stakeholders are of a similar magnitude. Such cases should be addressed by the CCB on an individual basis.

One option available is when modifications to the model are proposed purely to assist legacy systems, that those modifications be implemented as FIXM extensions. Where this is relevant to individual stakeholders, it is a local concern and would not be considered for the global FIXM. However, where such a change is relevant to multiple stakeholders, then the required change could become a FIXM extension.

### Historic versus Snapshot
FIXM has adopted the approach that a flight document is a snapshot of the flight containing the information known about the flight at a point in time. However, this approach can be relaxed where specific use cases dictate it is desirable to hold limited historic information. Such information elements must be endorsed by the CCB.

A small amount of historic information was maintained in earlier versions of FIXM, however as of v4 there is none.
If one considers the wide variety of information elements that constitute a flight, and the rate at which these values can change, adopting a 'historic' model would lead to a very large flight information document that could become unwieldy. The maintenance of historic flight information is considered a system implementation concern.

### Reuse of Standards
FIXM does not exist in a vacuum. It co-exists with many other standards, the two most closely related being AIXM and WXXM. FIXM development should be cognizant of the content of these related standards and seek to re-use definitions where possible rather than creating its own definition for the same concept. Redefinition leads to redundant elements, and ambiguity if the competing definitions are not consistent.

The harmonization of AIXM, FIXM and WXXM is a desirable goal. However, such harmonization is a large undertaking with significant impact on the model. As of FIXM v4 the focus has been to create semantically equivalent elements in the FIXM model. The same approach applies to standards that have more of a foundational nature. For example, the Geography Markup Language {GML) captures generic definitions that are applicable to aviation, such as the location of an aerodrome, the route of a flight, or the description of the bounds of airspace.

An associated standard is the International Air Transport Association (IATA) Aviation Information Data Exchange (AIDX) standard. This standard is widely employed by aircraft and airport operators but is also applicable to ASPs for information exchange with these operators. AIDX has a different focus than FIXM; for example, it incorporates data elements for baggage handling and catering.
However, there is an overlap between AIDX and FIXM, and where they overlap semantic consistency should be achieved. Different design approaches have been adopted for AIDX and FIXM, and it seems unlikely they will be harmonized in the manner planned among AIXM, FIXM and WXXM.

## Summary of Guidelines

This section provides guidelines to assist with model development. The guidelines are presented at a high level, providing general principles rather than firm requirements.
As such, exceptions are possible. However, exceptions should be made explicit and justified.

1)	**The FIXM model should at all times be driven by content and structure concerns.**

    FIXM is only concerned with information modelling. The presentation of that information does not influence the construction of the model. Other considerations like how the information is packaged, transmitted, or used should not influence the way the information is modelled. As FIXM evolves it will become necessary to address messages and services to ensure global interoperability. A first step towards addressing message packaging concerns has been incorporated in FIXM v4.

2)	**The FIXM model should avoid unnecessary complexity.**

    Complexity inhibits understanding and increases implementation effort. The less complex the model, the less likely information exchange results in different or ambiguous interpretation.
 
3)	**The FIXM model should be compatible with existing ICAO standards.**
 
    Existing standards, even if they plan to be phased out through FF-ICE, will continue to be employed for some time. FIXM must be able to interoperate with these standards during transition. Note this does not mean FIXM must directly mimic those standards, just that it be semantically compatible.

4)	**The FIXM model should delineate primitive values in the structure of the model.**
 
    It should not be necessary to decode or parse primitive values in the model to extract information content. Multiple primitive values should not be coalesced into a single compound value encoded in a string.

5)	**The FIXM model should not be influenced by the concerns of a single or small group of stakeholders.**
   
    FIXM is a global standard for information exchange. The incorporation of requirements for individual or small groups of stakeholders would inevitably lead to an explosion in the complexity of the model. The extension mechanism is available to address the specific needs of these individual or small groups of stakeholders.

6)	**The FIXM model should allow the representation of a snapshot of the most up to date information known about the flight.**

    The FIXM model allows the most accurate known information about the flight to be disseminated. All stakeholders will not necessarily hold all information about a flight, but the model should allow each stakeholder to represent the most up to date information they hold.

7)	**The FIXM model should not contain historic information about a flight except where specific use cases make such information desirable.**

    Modelling should include specific historic information in FIXM Core where the inclusion of such information is justified and of common interest. That justification must be explicit and documented to avoid excess complexity and avoid FIXM XML documents growing to an unmanageable size.

8)	**The FIXM model should limit redundancy of information.**

    Redundant information is a source of model inconsistencies that can result in misunderstanding, ambiguity, and incorrect information usage. Redundancy also increases object size and entails business rules external to the model.

9)	**The FIXM model should be constructed to facilitate the creation of extensions.**

    There are cases where it is necessary to allow the model to be extended to support legacy operations/systems/standards. The model should not place an undue burden on those who would create extensions.

10)	**Content must be in scope.**

    Each release of FIXM incorporates new elements as defined in the FIXM roadmap. All content added must trace to the scope approved by the CCB.

11)	**If an entity in FIXM is directly related to an entity in AIXM, FIXM will import the AIXM definition, or define its own version, semantically equivalent to the AIXM definition.**

    Ideally FIXM would directly import concepts from AIXM, but such incorporation is a significant undertaking and has wide reaching consequences. For practical purposes, FIXM (as of v4) defines its own constructs, which are equivalent to AIXM.

12)	**If an entity in FIXM is directly related to an entity in WXXM, FIXM will import the WXXM definition, or define its own version, semantically equivalent to the WXXM definition.**

    Ideally FIXM would directly import concepts from WXXM, but such incorporation is a significant undertaking and has wide reaching consequences. For practical purposes, FIXM (as of v4) defines its own constructs, which are equivalent to WXXM.

13)	**If an entity in FIXM is directly related to an entity in GML, FIXM will import the GML definition, or define its own version, semantically equivalent to the GML definition.**

    Ideally FIXM would directly import concepts from GML, but such incorporation is a significant undertaking and has wide reaching consequences. For practical purposes, FIXM (as of v4) defines its own constructs, which are equivalent to GML.

14)	**Information elements of the model must be based on concepts from the ICAO ATM Information Reference Model (AIRM).**

    The AIRM captures concepts for all features that eventually will be included in FIXM. A model element must trace to the AIRM, except where the model element is introduced purely as a 'container' element. As of FIXM v4 the AIRM is still under development so the mapping from FIXM to AIRM has yet to be performed.

15)	**Information elements in FIXM must be semantically consistent with corresponding elements in AIDX.**
   
    AIDX is widely used by airport and aircraft operators. To facilitate interoperability, FIXM should ensure semantic consistency with concepts in AIDX where the two standards overlap.

16)	**Exceptions are possible.**
   
    Notwithstanding the previous guidelines, exceptions are possible where justification is provided. Exceptions must be approved by the FIXM CCB.
