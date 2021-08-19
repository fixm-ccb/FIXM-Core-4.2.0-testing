# Guidelines for FIXM Development
This section provides guidelines for the development of FIXM, and addresses the often competing requirements of a forward-looking 'ideal' model and the support of legacy systems and formats during transition. 

## Content versus Presentation
The intent of FIXM is to model the information elements and structure of flight information. That is, the concern is what constitutes a flight, and how the elements relate to each other. FIXM does not dictate how that flight information is packaged, transmitted, used, or presented to human
stakeholders. The physical FIXM model is encoded as Extensible Markup Language (XML). XML is aimed at system-to-system communication. While humans can read XML, it is not designed for human consumption. Certainly, a flight dispatcher or air traffic controller would never be exposed to FIXM XML. Rath er, a user interface would be provided for such stakeholders, which presents  the content of the FIXM encoded flight information in an operationally meaningful manner.
FIXM reflects the modern best practice that content and presentation should be separate concerns. The benefit of such an approach is that development of FIXM can focus purely on content. Model development is not distracted by issues such as whether a FIXM encoded flight is directly understandable by a human; the concern is "what is a flight".
 
The related Aeronautical Information Exchange Model (AIXM) and Weather Information Exchange Model (WXXM) standards for resource and environmental information exchange similarly focus on content and structure.

## Structure vs. Custom Decoding
