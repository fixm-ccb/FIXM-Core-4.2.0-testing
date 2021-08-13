# FIXM Development Guidelines

This section provides guidelines to assist with FIXM model development. The guidelines are presented at a high level, providing general principles rather than firm requirements.
As such, exceptions are possible. However, exceptions should be made explicit and justified.

1)	**The FIXM model should at all times be driven by content and structure concerns.**

    FIXM is only concerned with information modelling. The presentation of that information does not influence the construction of the model. Other considerations like how the 
    information is packaged, transmitted or used should not influence the way the information is modelled. As FIXM evolves it will become necessary to address messages and             services to ensure global interoperability. A first step towards addressing message packaging concerns has been incorporated in FIXM v4.

2)	**The FIXM model should avoid unnecessary complexity.**

    Complexity inhibits understanding and increases implementation effort. The less complex the model, the less likely information exchange results in different or ambiguous 
    interpretation.
 
3)	**The FIXM model should be compatible with existing ICAO standards.**
 
    Existing standards, even if they plan to be phased out through FF-ICE, will continue to be employed for some time. FIXM must be able to interoperate with these standards
    during transition. Note this does not mean FIXM must directly mimic those standards, just that it be semantically compatible.

4)	**The FIXM model should delineate primitive values in the structure of the model.**
 
    It should not be necessary to decode or parse primitive values in the model to extract information content. Multiple primitive values should not be coalesced into a single 
    compound value encoded in a string.

5)	**The FIXM model should not be influenced by the concerns of a single or small group of stakeholders.**
   
    FIXM is a global standard for information exchange. The incorporation of requirements for individual or small groups of stakeholders would inevitably lead to an explosion 
    in the complexity of the model. The extension mechanism is available to address the specific needs of these individual or small groups of stakeholders.

6)	**The FIXM model should allow the representation of a snapshot of the most up to date information known about the flight.**

    The FIXM model allows the most accurate known information about the flight to be disseminated. All stakeholders will not necessarily hold all information about a flight, 
    but the model should allow each stakeholder to represent the most up to date information they hold.

7)	**The FIXM model should not contain historic information about a flight except where specific use cases make such information desirable.**

    Modelling should include specific historic information in FIXM Core where the inclusion of such information is justified and of common interest. That justification must be 
    explicit and documented to avoid excess complexity, and avoid FIXM XML documents growing to an unmanageable size.

8)	**The FIXM model should limit redundancy of information.**

    Redundant information is a source of model inconsistencies that can result in misunderstanding, ambiguity, and incorrect information usage. Redundancy also increases object
    size and entails business rules external to the model.

9)	**The FIXM model should be constructed to facilitate the creation of extensions.**

    There are cases where it is necessary to allow the model to be extended to support legacy operations/systems/standards. The model should not place an undue burden on those
    who would create extensions.

10)	**Content must be in scope.**

    Each release of FIXM incorporates new elements as defined in the FIXM roadmap. All content added must trace to the scope approved by the CCB.

11)	**If an entity in FIXM is directly related to an entity in AIXM, FIXM will import the AIXM definition, or define its own version, semantically equivalent to the AIXM 
definition.**

    Ideally FIXM would directly import concepts from AIXM, but such incorporation is a significant undertaking and has wide reaching consequences. For practical purposes, 
    FIXM (as of v4) defines its own constructs, which are equivalent to AIXM.

12)	**If an entity in FIXM is directly related to an entity in WXXM, FIXM will import the WXXM definition, or define its own version, semantically equivalent to the WXXM 
definition.**

    Ideally FIXM would directly import concepts from WXXM, but such incorporation is a significant undertaking and has wide reaching consequences. For practical purposes, 
    FIXM (as of v4) defines it s own constructs, which are equivalent to WXXM.

13)	**If an entity in FIXM is directly related to an entity in GML, FIXM will import the GML definition, or define its own version, semantically equivalent to the GML definition.**

    Ideally FIXM would directly import concepts from GML, but such incorporation is a significant undertaking and has wide reaching consequences. For practical purposes, 
    FIXM (as of v4) defines its own constructs, which are equivalent to GML.

14)	**Information elements of the model must be based on concepts from the ICAO ATM Information Reference Model (AIRM).**

    The AIRM captures concepts for all features that eventually will be included in FIXM. A model element must trace to the AIRM, except where the model element is introduced purely
    as a 'container' element. As of FIXM v4 the AIRM is still under development so the mapping from FIXM to AIRM has yet to be performed.

15)	**Information elements in FIXM must be semantically consistent with corresponding elements in AIDX.**
   
    AIDX is widely used by airport and aircraft operators. To facilitate interoperability, FIXM should ensure semantic consistency with concepts in AIDX where the two standards
    overlap.

16)	**Exceptions are possible.**
   
    Notwithstanding the previous guidelines, exceptions are possible where justification is provided. Exceptions must be approved by the FIXM CCB.
