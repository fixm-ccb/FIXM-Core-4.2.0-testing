# Sample XML

Below is a sample XML document that validates against the Example
Extension described in this Appendix:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<msg:Message xmlns:xmp="http://www.fixm.aero/ext/example/1.0" xmlns:fx="http://www.fixm.aero/flight/4.2" xmlns:fb="http://www.fixm.aero/base/4.2" xmlns:msg="http://www.fixm.aero/app/msg/1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <msg:extension xsi:type="xmp:ExampleMessageType">
    <xmp:sequenceNumber>1903</xmp:sequenceNumber>
  </msg:extension>
  <msg:flight>
    <fx:enRoute>
      <fx:extension xsi:type="xmp:ExampleEnRouteType">
        <xmp:position srsName="urn:ogc:def:crs:EPSG::4326">
          <fb:pos>36.019970 -75.668760</fb:pos>
        </xmp:position>
      </fx:extension>
    </fx:enRoute>
  </msg:flight>
</msg:Message>
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
