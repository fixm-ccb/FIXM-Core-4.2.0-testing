# Sample XML

Below is a sample XML document that validates against the Example
Extension described in this Appendix:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<xmg:ExampleMessage xsi:type="xmg:ExampleDA_ExampleMessageType" xmlns:xmg="http://www.fixm.aero/app/example/1.0" xmlns:fb="http://www.fixm.aero/base/4.2" xmlns:fx="http://www.fixm.aero/flight/4.2" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <xmg:flight>
    <fx:departure>
      <fx:actualTimeOfDeparture>2020-01-15T00:00:00Z</fx:actualTimeOfDeparture>
      <fx:aerodrome>
        <fb:locationIndicator>KBOS</fb:locationIndicator>
      </fx:aerodrome>
    </fx:departure>
    <fx:flightIdentification>
      <fx:aircraftIdentification>ABC1234</fx:aircraftIdentification>
    </fx:flightIdentification>
    <fx:gufi codeSpace="urn:uuid">3e7f6a63-6c3b-4f0f-844b-4b84338ed103</fx:gufi>
  </xmg:flight>
  <xmg:recipient>
    <fb:name>RECIPIENT 1</fb:name>
  </xmg:recipient>
  <xmg:recipient>
    <fb:name>RECIPIENT 2</fb:name>
  </xmg:recipient>
  <xmg:sender>
    <fb:name>SENDER</fb:name>
  </xmg:sender><xmg:timestamp>2020-01-15T00:00:01Z</xmg:timestamp>
  <xmg:type>DEPARTURE</xmg:type>
</xmg:ExampleMessage>

```

## Rulebook

Versioning & namespace

- An Extension should employ semantic versioning (major.minor.micro)
    with version number starting at 1.0.0.

- ...

Diagrams

- Include copyright notice in each model diagram

Naming

- Name characters limited to upper and lower case, digits and
    underscore

- Use InterCap notation (= “Camel Case”) for all model elements

- Use starting capital for packages and classes

- Use starting miniscule for attributes and roles

- Use all capitals for enumeration values

- Names should be expressive of data content or relationship

- Names should not be of unwieldy length

Inheritance

- Abstract classes are allowed

- Root classes are forbidden

- Leaf classes must be justified

Datatypes

- ...

Stereotypes

- ...

## Creating an Extension step by step

- When creating a restriction, XML elements are eliminated by removing them from the model
- Optionality, cardinality, and pattern restrictions can all be further restricted by applying the desired changes to the restricted class.
- Because XSD complex type restrictions must use the same namespace as the types they restrict, it is necessary to change their names.
