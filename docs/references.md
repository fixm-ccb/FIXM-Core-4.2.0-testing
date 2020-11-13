# This is the title of a page

## How we encode notes

This is text with a footnote <sup>[[note 1]](#notes)</sup>

## How we could encode external references

### When we have a URL (A)

When the type of aircraft that conducts a flight does not have an ICAO aircraft type designator [ICAO Doc 8643] <sup>[[12]](#references)</sup> or the flight is a formation, the value ZZZZ is inserted in field 9b and the aircraft type information is inserted in field 18 TYP. The following fragment is an example.

When the type of aircraft that conducts a flight does not have an ICAO aircraft type designator [ICAO Doc 8643] <sup id=when-we-have-a-url-1>[[12]](#references)</sup> or the flight is a formation, the value ZZZZ is inserted in field 9b and the aircraft type information is inserted in field 18 TYP. The following fragment is an example.

### When we have a URL (B)

When the type of aircraft that conducts a flight does not have an ICAO aircraft type designator [[ICAO Doc 8643]][16] or the flight is a formation, the value ZZZZ is inserted in field 9b and the aircraft type information is inserted in field 18 TYP. The following fragment is an example.

### When we don't have a URL

This chapter provides a mapping between the Flight Information Exchange Model (FIXM) Logical Model v4.1.0 and International Civil Aviation Organisation (ICAO) Air Traffic Services (ATS) message content as defined in ICAO Doc 4444 [PANS-ATM] <sup>[[8]](#references)</sup>.

## Notes

[1] This is a Note

[2] This is another Note

## References

[1] This is a Reference

[2] This is another Reference

[8] PANS-ATM: Procedures for Air Navigation Services: Air Traffic Management, ICAO Doc 4444, 16th edition

[12] [ICAO Doc 8643: Aircraft Type Designators](https://www.icao.int/publications/DOC8643/Pages/default.aspx)

[12] [^](#when-we-have-a-url-1) [ICAO Doc 8643: Aircraft Type Designators](https://www.icao.int/publications/DOC8643/Pages/default.aspx)

[16]: https://www.icao.int/publications/DOC8643/Pages/default.aspx
