# Date/Time Specification & AIRAC

## Date/Time
FIXM requires times to be expressed in UTC. A constraint is therefore placed on the FIXM classes used to represent date/time values that imposes the use of the trailing character `Z` to indicate UTC, in line with the W3C XSD specification.

Sub-second precision is considered unneeded for most aviation data, but other fields such as message timestamps can still benefit from higher precision date/times.

---

`FIXM Core 4.3.0` defines two types for representing date/time values
- `DateTimeUtc`, that restricts the standard XML dateTime, is constrained to only allow whole second precision. `DateTimeUtc` is used for typing all aviation-related times, such as the EOBT.
- `DateTimeUtcHighPrecision`, that restricts the standard XML dateTime, employs unrestricted sub-second precision. `DateTimeUtcHighPrecision` is used for typing the message timestamps in the FIXM Applications.

Examples: 
- for aviation-related times, *20th July 1969 at 20:18 UTC* is expressed as `1969-07-20T20:18:00Z`
- for message timestamps, higher precision can be provided: `1969-07-20T20:18:00.458Z`

---

`FIXM Core 4.2.0` defines only one type for representing date/time values, named `Time`, which employs unrestricted sub-second precision and is used for typing aviation-related times and message timestamps. For aviation-related times, it is recommended to encode times with trailing characters `.000Z`. Message timestamps can use higher precision, as needed.


Examples: 
- for aviation-related times, *20th July 1969 at 20:18 UTC* is expressed as `1969-07-20T20:18:00.000Z`
- for message timestamps, higher precision can be provided: `1969-07-20T20:18:00.458Z`

---

!> **Note to implementers:** The mapping of the XSD type `dateTime` to native structures in various development contexts is not always 1-1 and may exhibit a wide variety of difficulties depending on the tooling and runtime context. In particular, the trailing character `Z` indicating UTC may actually be stripped/omitted, leading to FIXM times being interpreted as local times instead of UTC times by some applications. FIXM implementers are therefore invited to crosscheck that their systems correctly interpret FIXM times as UTC time.


## AIRAC references

