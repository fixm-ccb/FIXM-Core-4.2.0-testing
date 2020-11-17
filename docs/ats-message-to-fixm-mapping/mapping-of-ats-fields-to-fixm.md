# Mapping of ATS Fields to FIXM

This section provides a mapping from fields in PANS-ATM ATS messages to
the FIXM Logical Model, one ATS message field per subsection. The
columns in the mapping tables are defined in Table 8.

Table 8: Column
Definitions

| **Column** | **Description** |
|------------|-----------------|
| PANS-ATM Field   | The field number as defined in ICAO Doc 4444 \[PANS-ATM\]<sup>[[4]](#references)</sup>. |
| Package          | The package that contains the definition of the PANS-ATM field in the logical model.                                                                |
| Class            | The class (in the specified package) that models the PANS-ATM field.                                                                                |
| Path from Flight | Starting from class *Flight* in package *Flight.FlightData*, this defines the path to the location in the logical model where the field is encoded. |

Table 9 provides an explanation of an entry in the map using the flight
identifier recorded in field 7a of an ICAO ATS message (see [Field
7](#Field-7)).

Table 9: Example

| Column           | Value                                       | Description                                                                                                                                                                                                          |
|------------------|---------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PANS-ATM Field   | 7a                                          | This is the field number from PANS-ATM that represents the flight identifier, which is being mapped to the logical model.                                                                                            |
| Package          | Base.Types                                  | The flight identifier is modelled in the *Base.Types* package.                                                                                                                                                       |
| Class            | AircraftIdentification                      | The name of the class that models a flight identifier is *AircraftIdentification*.                                                                                                                                   |
| Path from Flight | flightIdentification.aircraftIdentification | Starting at class *Flight*, follow the *flightIdentification* association to class *FlightIdentification*, then to the *aircraftIdentification* attribute of that class (which is of type *AircraftIdentification*). |

A PANS-ATM ATS message field may be mapped to different FIXM elements
depending on context. A simple constraint notation based on logic and
set theory is employed to specify these conditions. The notation is
described in Table 10.

Table 10: Constraint
Notation

| Notation      | Description                                                                                                       |
|---------------|-------------------------------------------------------------------------------------------------------------------|
| \[ . . . . \] | A constraint. The field in question is only encoded in the specified FIXM element if the constraint is satisfied. |
| A ∧ B         | Logical conjunction: both A and B are true.                                                                       |
| A ∨ B         | Logical disjunction: A is true or B is true.                                                                      |
| A = B         | Equality: A and B are equal.                                                                                      |
| A ≠ B         | Inequality: A and B are not equal.                                                                                |
| A ∈ B         | Set membership: the item A is contained in the set/list B.                                                        |
| A ∉ B         | Set exclusion: the item A is not contained in the set/list B.                                                     |
| Free text     | If the constraint is not amenable to formal specification, it is described in text.                               |

The term ‘〈kind〉’ in the subsequent tables (fields 8, 13, 15, 16 and
18) is a reference to the kind of route/trajectory information to which
a field is mapped. That route information is dependent on the message
type. Refer to section Varieties of Route for a mapping between the
message type and the kind of route information.

## Field 3

Field 3 in an ATS message denotes the message type. FIXM is concerned
with modelling information that may be included in a message, but FIXM
itself does not define messages. As such, there is no equivalent of ATS field 3 in FIXM.

## Field 5

| ICAO 4444 Field | Package          | Class           | Path from Flight                            |
|-----------------|------------------|-----------------|---------------------------------------------|
| 5a              | Flight.Emergency | EmergencyPhase  | emergency.phase                             |
| 5b              | Base.Types       | TextName        | emergency.originator.atcUnitNameOrAlternate |
| 5c              | Base.Types       | CharacterString | emergency.emergencyDescription              |

## Field 7

| ICAO 4444 Field | Package    | Class                  | Path from Flight                            |
|-----------------|------------|------------------------|---------------------------------------------|
| 7a              | Base.Types | AircraftIdentification | flightIdentification.aircraftIdentification |
| 7b/c            | Base.Types | ModeACode              | enRoute.currentModeACode                    |

## Field 8

| ICAO 4444 Field | Package                                      | Class               | Path from Flight                                                   |
|-----------------|----------------------------------------------|---------------------|--------------------------------------------------------------------|
| 8a              | Flight.FlightRouteTrajectory.RouteTrajectory | FlightRulesCategory | routeTrajectoryGroup.〈kind〉.routeInformation.flightRulesCategory |
| 8b              | Flight.FlightData                            | TypeOfFlight        | flightType                                                         |

## Field 9

<table>
<thead>
<tr class="header">
<th>ICAO 4444 Field</th>
<th>Package</th>
<th>Class</th>
<th>Path from Flight</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>9a</td>
<td>Base.Types</td>
<td>Count</td>
<td><p>aircraft.formationCount</p>
<p>If the FIXM number of aircraft is greater than 99, set field 9a to 99.</p></td>
</tr>
<tr class="even">
<td>9b</td>
<td>Base.Types</td>
<td>AircraftTypeDesignator</td>
<td><p>[9b≠ZZZZ]</p>
<p>aircraft.aircraftType.type.icaoAircraftTypeDesignator</p></td>
</tr>
<tr class="odd">
<td>9c</td>
<td>Flight.Aircraft</td>
<td>WakeTurbulenceCategory</td>
<td>aircraft.wakeTurbulence</td>
</tr>
</tbody>
</table>

## Field 10

| ICAO 4444 Field | Package           | Class                               | Path from Flight                                                        |
|-----------------|-------------------|-------------------------------------|-------------------------------------------------------------------------|
| 10a             | Flight.Capability | StandardCapabilitiesIndicator       | aircraft.capabilities.standardCapabilities                              |
|                 |                   | CommunicationCapabilityCode         | aircraft.capabilities.communication.communicationCapabilityCode         |
|                 |                   | DatalinkCommunicationCapabilityCode | aircraft.capabilities.communication.datalinkCommunicationCapabilityCode |
|                 |                   | NavigationCapabilityCode            | aircraft.capabilities.navigation.navigationCapabilityCode               |
| 10b             | Flight.Capability | SurveillanceCapabilityCode          | aircraft.capabilities.surveillance.surveillanceCapabilityCode           |

## Field 13

<table>
<thead>
<tr class="header">
<th>ICAO 4444 Field</th>
<th>Package</th>
<th>Class</th>
<th>Path from Flight</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>13a</td>
<td>Base.Organization</td>
<td>LocationIndicator</td>
<td><p>[13a≠AFIL ∧ 13a≠ZZZZ]</p>
<p>departure.aerodrome.locationIndicator</p></td>
</tr>
<tr class="even">
<td></td>
<td>Flight.Departure</td>
<td>AirfileIndicator</td>
<td><p>[13a=AFIL]</p>
<p>departure.airfileIndicator = AIRFILE</p></td>
</tr>
<tr class="odd">
<td>13b</td>
<td>Base.Types</td>
<td>Time</td>
<td><p>[13a≠AFIL ∧ message∈{FPL,ARR,CHG,CNL,DLA,RQS,RQP}]</p>
<p>departure.estimatedOffBlockTime</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td></td>
<td><p>[13a≠AFIL ∧ message∈{ALR,DEP,SPL}]</p>
<p>departure.actualTimeOfDeparture</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
<td><p>[13a=AFIL]</p>
<p>routeTrajectoryGroup.〈kind〉.routeInformation.airfileRouteStartTime</p></td>
</tr>
</tbody>
</table>

## Field 14

| ICAO 4444 Field | Package                    | Class                       | Path from Flight                                                            |
|-----------------|----------------------------|-----------------------------|-----------------------------------------------------------------------------|
| 14a             | Base.AeronauticalReference | SignificantPointChoice      | enroute.boundaryCrossingCoordination.crossingPoint                          |
| 14b             | Base.Types                 | Time                        | enroute.boundaryCrossingCoordination.crossingTime                           |
| 14c             | Base.RangesAndChoices      | FlightLevelOrAltitudeChoice | enroute.boundaryCrossingCoordination.clearedLevel                           |
| 14d             | Flight.EnRoute             | FlightLevelOrAltitudeChoice | enroute.boundaryCrossingCoordination.altitudeInTransition.level             |
| 14e             | Flight.EnRoute             | BoundaryCrossingCondition   | enroute.boundaryCrossingCoordination.altitudeInTransition.crossingCondition |

## Field 15

<table>
<thead>
<tr class="header">
<th>ICAO 4444 Field</th>
<th>Package</th>
<th>Class</th>
<th>Path from Flight</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>15a</td>
<td>Base.Measures</td>
<td>TrueAirspeed</td>
<td>routeTrajectoryGroup.〈kind〉.routeInformation.cruisingSpeed</td>
</tr>
<tr class="even">
<td>15b</td>
<td>Base.RangesAndChoices</td>
<td>FlightLevelOrAltitudeChoice</td>
<td><p>[15b≠VFR]</p>
<p>routeTrajectoryGroup.〈kind〉.routeInformation.cruisingLevel</p></td>
</tr>
<tr class="odd">
<td>15c</td>
<td>Flight.FlightRouteTrajectory.RouteTrajectory</td>
<td>RouteTrajectoryElement</td>
<td>routeTrajectoryGroup.〈kind〉.element</td>
</tr>
<tr class="even">
<td></td>
<td>Base.Types</td>
<td>CharacterString</td>
<td>routeTrajectoryGroup.〈kind〉.routeInformation.routeText</td>
</tr>
<tr class="odd">
<td>15c1</td>
<td>Base.AeronauticalReference</td>
<td>SidStarReference</td>
<td>routeTrajectoryGroup.〈kind〉.element.routeDesignatorToNextElement.standardInstrumentDeparture</td>
</tr>
<tr class="even">
<td>15c2</td>
<td>Base.AeronauticalReference</td>
<td>RouteDesignator</td>
<td>routeTrajectoryGroup.〈kind〉.element.routeDesignatorToNextElement.routeDesignator</td>
</tr>
<tr class="odd">
<td>15c3</td>
<td>Base.AeronauticalReference</td>
<td>SignificantPointChoice</td>
<td>routeTrajectoryGroup.〈kind〉.element.elementStartPoint</td>
</tr>
<tr class="even">
<td>15c4</td>
<td>Base.AeronauticalReference</td>
<td>SignificantPointChoice</td>
<td>routeTrajectoryGroup.〈kind〉.element.elementStartPoint</td>
</tr>
<tr class="odd">
<td></td>
<td>Base.Measures</td>
<td>TrueAirspeed</td>
<td>routeTrajectoryGroup.〈kind〉.element.routeChange.speed.speed</td>
</tr>
<tr class="even">
<td></td>
<td>Base.RangesAndChoices</td>
<td>FlightLevelOrAltitudeChoice</td>
<td>routeTrajectoryGroup.〈kind〉.element.routeChange.level.level</td>
</tr>
<tr class="odd">
<td>15c5</td>
<td>Flight.FlightRouteTrajectory.RouteTrajectory</td>
<td>FlightRules</td>
<td><p>[15c5=IFR ∨ 15c5=VFR]</p>
<p>routeTrajectoryGroup.〈kind〉.element.flightRulesChange</p></td>
</tr>
<tr class="even">
<td></td>
<td>Flight.FlightRouteTrajectory.RouteTrajectory</td>
<td>OtherRouteDesignator</td>
<td><p>[15c5=DCT]</p>
<p>routeTrajectoryGroup.〈kind〉.element.routeDesignatorToNextElement.otherRouteDesignator = DIRECT</p></td>
</tr>
<tr class="odd">
<td></td>
<td>Flight.FlightRouteTrajectory.RouteTrajectory</td>
<td>RouteTruncationIndicator</td>
<td><p>[15c5=T]</p>
<p>routeTrajectoryGroup.〈kind〉.element.routeTruncationIndicator = ROUTE_TRUNCATION</p></td>
</tr>
<tr class="even">
<td>15c6</td>
<td>Base.AeronauticalReference</td>
<td>SignificantPointChoice</td>
<td>routeTrajectoryGroup.〈kind〉.element.elementStartPoint</td>
</tr>
<tr class="odd">
<td></td>
<td>Base.Measures</td>
<td>TrueAirspeed</td>
<td>routeTrajectoryGroup.〈kind〉.element.routeChange.cruiseClimbStart.speed</td>
</tr>
<tr class="even">
<td></td>
<td>Base.RangesAndChoices</td>
<td>VerticalRange</td>
<td><p>[PLUS∉15c6]</p>
<p>routeTrajectoryGroup.〈kind〉.element.routeChange.cruiseClimbStart.level.flightLevelOrAltitudeRange</p></td>
</tr>
<tr class="odd">
<td></td>
<td>Base.RangesAndChoices</td>
<td>FlightLevelOrAltitudeChoice</td>
<td><p>[PLUS∈15c6]</p>
<p>routeTrajectoryGroup.〈kind〉.element.routeChange.cruiseClimbStart.level.flightLevelOrAltitudeValue</p></td>
</tr>
<tr class="even">
<td>15c7</td>
<td>Base.AeronauticalReference</td>
<td>SidStarReference</td>
<td>routeTrajectoryGroup.〈kind〉.element.routeDesignatorToNextElement.standardInstrumentArrival</td>
</tr>
</tbody>
</table>

## Field 16

<table>
<thead>
<tr class="header">
<th>ICAO 4444 Field</th>
<th>Package</th>
<th>Class</th>
<th>Path from Flight</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>16a</td>
<td>Base.Organization</td>
<td>LocationIndicator</td>
<td><p>[16a≠ZZZZ]</p>
<p>arrival.destinationAerodrome.locationIndicator</p></td>
</tr>
<tr class="even">
<td>16b</td>
<td>Base.Types</td>
<td>Duration</td>
<td>routeTrajectoryGroup.〈kind〉.routeInformation.totalEstimatedElapsedTime</td>
</tr>
<tr class="odd">
<td>16c</td>
<td>Base.Organization</td>
<td>LocationIndicator</td>
<td><p>[16c≠ZZZZ]</p>
<p>arrival.destinationAerodromeAlternate.locationIndicator</p>
<p>If there are more than two FIXM destination alternates, only the first two are used when translating to field 16c.</p></td>
</tr>
</tbody>
</table>

## Field 17

<table>
<thead>
<tr class="header">
<th>ICAO 4444 Field</th>
<th>Package</th>
<th>Class</th>
<th>Path from Flight</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>17a</td>
<td>Base.Organization</td>
<td>LocationIndicator</td>
<td><p>[17a≠ZZZZ]</p>
<p>arrival.arrivalAerodrome.locationIndicator</p></td>
</tr>
<tr class="even">
<td>17b</td>
<td>Base.Types</td>
<td>Time</td>
<td>arrival.actualTimeOfArrival</td>
</tr>
<tr class="odd">
<td>17c</td>
<td>Base.Aerodrome</td>
<td>AerodromeName</td>
<td><p>[17a=ZZZZ]</p>
<p>arrival.arrivalAerodrome.name</p></td>
</tr>
</tbody>
</table>

## Field 18

<table>
<thead>
<tr class="header">
<th>ICAO 4444 Field</th>
<th>Package</th>
<th>Class</th>
<th>Path from Flight</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>STS</td>
<td>Flight.FlightData</td>
<td>SpecialHandlingReasonCode</td>
<td>specialHandling</td>
</tr>
<tr class="even">
<td>PBN</td>
<td>Flight.Capability</td>
<td>PerformanceBasedNavigationCapabilityCode</td>
<td><p>[R∈10a]</p>
<p>aircraft.capabilities.navigation.performanceBasedCode</p>
<p>If there are more than eight FIXM PBN codes, apply the rules defined in FF-ICE Implementation Guidance section 13.2.2 s) when translating to field 18 PBN.</p></td>
</tr>
<tr class="odd">
<td>NAV</td>
<td>Base.Types</td>
<td>CharacterString</td>
<td><p>[Z∈10a]</p>
<p>aircraft.capabilities.navigation.otherNavigationCapabilities</p></td>
</tr>
<tr class="even">
<td>COM</td>
<td>Base.Types</td>
<td>CharacterString</td>
<td><p>[Z∈10a]</p>
<p>aircraft.capabilities.communication.otherCommunicationCapabilities</p></td>
</tr>
<tr class="odd">
<td>DAT</td>
<td>Base.Types</td>
<td>CharacterString</td>
<td><p>[Z∈10a]</p>
<p>aircraft.capabilities.communication.otherDatalinkCapabilities</p></td>
</tr>
<tr class="even">
<td>SUR</td>
<td>Base.Types</td>
<td>CharacterString</td>
<td>aircraft.capabilities.surveillance.otherSurveillanceCapabilities</td>
</tr>
<tr class="odd">
<td>DEP</td>
<td>Base.Aerodrome</td>
<td>AerodromeReference</td>
<td><p>[13a=ZZZZ]</p>
<p>departure.aerodrome.name</p>
<p>departure.aerodrome.referencePoint</p></td>
</tr>
<tr class="even">
<td></td>
<td>Base.Types</td>
<td>TextName</td>
<td><p>[13a=AFIL]</p>
<p>flightPlanSubmitter.name</p></td>
</tr>
<tr class="odd">
<td>DEST</td>
<td>Base.Aerodrome</td>
<td>AerodromeReference</td>
<td><p>[16a=ZZZZ]</p>
<p>destination.destinationAerodrome.name</p>
<p>destination.destinationAerodrome.referencePoint</p></td>
</tr>
<tr class="even">
<td>DOF</td>
<td>Base.Types</td>
<td>Time</td>
<td><p>[13a≠AFIL]</p>
<p>departure.estimatedOffBlockTime</p>
<p>[13a=AFIL]</p>
<p>routeTrajectoryGroup.〈kind〉.route.airfileRouteStartTime</p>
<p>Note: DOF is not modelled as a distinct attribute in FIXM, it is a component of the departure or air filed start date/time (see field 13b on page 111)</p></td>
</tr>
<tr class="odd">
<td>REG</td>
<td>Flight.Aircraft</td>
<td>AircraftRegistration</td>
<td><p>aircraft.registration</p>
<p>If there is more than one FIXM registration, insert the first only in field 18 REG.</p></td>
</tr>
<tr class="even">
<td>EET</td>
<td>Base.AeronauticalReference</td>
<td>AirspaceDesignator</td>
<td><p>[Airspace boundary specified]</p>
<p>routeTrajectoryGroup.〈kind〉.routeInformation.estimatedElapsedTime.location.region</p></td>
</tr>
<tr class="odd">
<td></td>
<td>Base.AeronauticalReference</td>
<td>SignificantPointChoice</td>
<td><p>[Significant point specified]</p>
<p>routeTrajectoryGroup.〈kind〉.routeInformation.estimatedElapsedTime.location.point</p></td>
</tr>
<tr class="even">
<td></td>
<td>Base.AeronauticalReference</td>
<td>Longitude</td>
<td><p>[Longitude specified]</p>
<p>routeTrajectoryGroup.〈kind〉.routeInformation.estimatedElapsedTime.location.longitude</p></td>
</tr>
<tr class="odd">
<td></td>
<td>Base.Types</td>
<td>Duration</td>
<td>routeTrajectoryGroup.〈kind〉.routeInformation.estimatedElapsedTime.elapsedTime</td>
</tr>
<tr class="even">
<td>SEL</td>
<td>Flight.Capability</td>
<td>SelectiveCallingCode</td>
<td>aircraft.capabilities.communication.selectiveCallingCode</td>
</tr>
<tr class="odd">
<td>TYP</td>
<td>Base.Types</td>
<td>Count</td>
<td><p>[9b=ZZZZ]</p>
<p>aircraft.aircraftType.numberOfAircraft</p></td>
</tr>
<tr class="even">
<td></td>
<td>Base.Types</td>
<td>CharacterString</td>
<td><p>[9b=ZZZZ]</p>
<p>aircraft.aircraftType.type.otherAircraftType</p></td>
</tr>
<tr class="odd">
<td>CODE</td>
<td>Flight.Aircraft</td>
<td>AircraftAddress</td>
<td>aircraft.aircraftAddress</td>
</tr>
<tr class="even">
<td>DLE</td>
<td>Base.AeronauticalReference</td>
<td>SignificantPoint</td>
<td>routeTrajectoryGroup.〈kind〉.element.elementStartPoint (see also field 15c3, 15c4 and 15c6)</td>
</tr>
<tr class="odd">
<td></td>
<td>Base.Types</td>
<td>Duration</td>
<td>routeTrajectoryGroup.〈kind〉.element.enRouteDelay.delayValue</td>
</tr>
<tr class="even">
<td>OPR</td>
<td>Base.Organization</td>
<td>AircraftOperatorDesignator</td>
<td><p>[ICAO designator specified]</p>
<p>operator.designatorIcao</p></td>
</tr>
<tr class="odd">
<td></td>
<td>Base.Types</td>
<td>TextName</td>
<td><p>[ICAO designator not specified]</p>
<p>operator.operatingOrganization.name</p></td>
</tr>
<tr class="even">
<td>ORGN</td>
<td>Base.Types</td>
<td>TextName</td>
<td>flightPlanOriginator.name</td>
</tr>
<tr class="odd">
<td>PER</td>
<td>Flight.Aircraft</td>
<td>AircraftApproachCategory</td>
<td>aircraft.aircraftApproachCategory</td>
</tr>
<tr class="even">
<td>ALTN</td>
<td>Base.Aerodrome</td>
<td>OtherReference</td>
<td><p>[ZZZZ∈16c]</p>
<p>arrival.destinationAerodromeAlternate.name</p>
<p>arrival.destinationAerodromeAlternate.referencePoint</p></td>
</tr>
<tr class="odd">
<td>RALT</td>
<td>Base.Aerodrome</td>
<td>AerodromeReference</td>
<td>enRoute.alternateAerodrome</td>
</tr>
<tr class="even">
<td>TALT</td>
<td>Base.Aerodrome</td>
<td>AerodromeReference</td>
<td>departure.takeOffAlternateAerodrome</td>
</tr>
<tr class="odd">
<td>RIF</td>
<td>Base.Types</td>
<td>CharacterString</td>
<td>arrival.reclearanceInFlight.routeToRevisedDestination</td>
</tr>
<tr class="even">
<td></td>
<td>Base.Aerodrome</td>
<td>AerodromeReference</td>
<td>arrival.reclearanceInFlight.filedRevisedDestinationAerodrome</td>
</tr>
<tr class="odd">
<td>RMK</td>
<td>Base.Types</td>
<td>CharacterString</td>
<td>remarks</td>
</tr>
</tbody>
</table>

## Field 19

| ICAO 4444 Field | Package           | Class                        | Path from Flight                                               |
|-----------------|-------------------|------------------------------|----------------------------------------------------------------|
| 19a             | Base.Types        | Duration                     | supplementaryData.fuelEndurance                                |
| 19b             | Base.Types        | Count                        | supplementaryData.personsOnBoard                               |
| 19c             | Flight.Capability | EmergencyRadioCapabilityType | aircraft.capabilities.survival.emergencyRadioCapabilityType    |
| 19d             | Flight.Capability | SurvivalEquipmentType        | aircraft.capabilities.survival.survivalEquipmentType           |
| 19e             | Flight.Capability | LifeJacketType               | aircraft.capabilities.survival.lifeJacketType                  |
| 19f             | Base.Types        | Count                        | aircraft.capabilities.survival.dinghyInformation.number        |
|                 | Base.Types        | Count                        | aircraft.capabilities.survival.dinghyInformation.totalCapacity |
|                 | Flight.Capability | DinghyCoverIndicator         | aircraft.capabilities.survival.dinghyInformation.covered       |
|                 | Base.Types        | CharacterString              | aircraft.capabilities.survival.dinghyInformation.colour        |
| 19g             | Base.Types        | CharacterString              | aircraft.coloursAndMarkings                                    |
|                 | ~~Base.Types~~    | ~~CharacterString~~          | ~~aircraft.significantMarkings~~                               |
| 19h             | Base.Types        | CharacterString              | aircraft.capabilities.survival.survivalEquipmentRemarks        |
| 19i             | Base.Types        | TextName                     | supplementaryData.pilotInCommand.name                          |

## Field 20

<table>
<thead>
<tr class="header">
<th>ICAO 4444 Field</th>
<th>Package</th>
<th>Class</th>
<th>Path from Flight</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>20a<sup><a href="#ats-message-to-fixm-mapping/mapping-of-ats-fields-to-fixm?id=notes">[note 1]</a></sup></td>
<td>Base.Organization</td>
<td>AircraftOperatorDesignator</td>
<td><p>[ICAO designator specified]</p>
<p>operator.designatorIcao</p></td>
</tr>
<tr class="even">
<td></td>
<td>Base.Types</td>
<td>TextName</td>
<td><p>[ICAO designator not specified]</p>
<p>operator.operatingOrganization.name</p></td>
</tr>
<tr class="odd">
<td>20b</td>
<td>Base.AeronauticalReference</td>
<td>AtcUnitName</td>
<td>emergency.lastContact.lastContactUnit</td>
</tr>
<tr class="even">
<td>20c</td>
<td>Base.Types</td>
<td>Time</td>
<td>emergency.lastContact.lastContactTime</td>
</tr>
<tr class="odd">
<td>20d</td>
<td>Base.Measures</td>
<td>Frequency</td>
<td>emergency.lastContact.lastContactFrequency</td>
</tr>
<tr class="even">
<td>20e</td>
<td>Base.AeronauticalReference</td>
<td>SignificantPointChoice</td>
<td>emergency.lastContact.position.position</td>
</tr>
<tr class="odd">
<td></td>
<td>Base.Types</td>
<td>Time</td>
<td>emergency.lastContact.position.timeAtPosition</td>
</tr>
<tr class="even">
<td>20f</td>
<td>Base.Types</td>
<td>CharacterString</td>
<td>emergency.lastContact.position.determinationMethod</td>
</tr>
<tr class="odd">
<td>20g</td>
<td>Base.Types</td>
<td>CharacterString</td>
<td>emergency.actionTaken</td>
</tr>
<tr class="even">
<td>20h</td>
<td>Base.Types</td>
<td>CharacterString</td>
<td>emergency.otherInformation</td>
</tr>
</tbody>
</table>
<section class="footnotes" role="doc-endnotes">
<hr />
<ol>
<li id="fn1" role="doc-endnote"><p>Field 20a maps to the same FIXM field as field 18 OPR. An ALR can include field 18 and field 20 with potentially conflicting values. Further consideration of this is required.<a href="#fnref1" class="footnote-back" role="doc-backlink">↩︎</a></p></li>
</ol>
</section>

## Field 21

| ICAO 4444 Field | Package                    | Class                  | Path from Flight                                          |
|-----------------|----------------------------|------------------------|-----------------------------------------------------------|
| 21a             | Base.Types                 | Time                   | radioCommunicationFailure.contact.lastContactTime         |
| 21b             | Base.Measures              | Frequency              | radioCommunicationFailure.contact.lastContactFrequency    |
| 21c             | Base.AeronauticalReference | SignificantPointChoice | radioCommunicationFailure.contact.position.position       |
| 21d             | Base.Types                 | Time                   | radioCommunicationFailure.contact.position.timeAtPosition |
| 21e             | Base.Types                 | CharacterString        | radioCommunicationFailure.remainingComCapability          |
| 21f             | Base.Types                 | CharacterString        | radioCommunicationFailure.radioFailureRemarks             |

## Field 22

In an ATS message, field 22 specifies a change to the information
associated with a flight. It does not define new information elements,
just a modification to elements that appear in other fields. As such,
there are no mapping rules for field 22. The mapping of the information
that can be specified in field 22 is captured in the other fields. For
example, the entry *-7/NEWACID* in field 22 has the same mapping as if
*–NEWACID* appeared in field 7 (on page 110).

## Notes

[1]: Field 20a maps to the same FIXM field as field 18 OPR. An ALR can include field 18 and field 20 with potentially conflicting values. Further consideration of this is required.

## References

[4]: PANS-ATM: Procedures for Air Navigation Services: Air Traffic Management, ICAO Doc 4444, 16th edition
