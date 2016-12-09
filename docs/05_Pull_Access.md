---
title: 5. Interfaces for Pull-based Data Access
layout: page
---
# Interfaces for Pull-based Data Access

## OGC Sensor Observation Service 2.0

* Introduce the purpose of the SOS standard and reference to the specification

* Explain operations with a few sentences and provide explanatory list of parameters
* Show sequence diagrams to illustrate the workflow
* Limit to version 2.0.0

### Data Access
The following SOS operations are necessary for enabling the access to observation data:

| Operation            |           | Remarks                              |
| ---------------------|-----------|--------------------------------------|
| GetCapabilities      | Mandatory | As specified in the SOS 2.0 standard |
| GetObservaton        | Mandatory | As specified in the SOS 2.0 standard |
| DescribeSensor       | Mandatory | As specified in the SOS 2.0 standard |
| GetFeatureOfInterest | Optional  | As specified in the SOS 2.0 standard |
| GetDataAvailability  | Optional  | Not part of the SOS 2.0 standard; should be implemented as specified in the INSPIRE Technical Guidance Documents on O&M and SOS-based Download Services |

#### GetCapabilities
This operation is the main entry point to every OGC Web Services. A GetCapabilities
response provides metadata on an SOS servers' capabilities (e.g. supported
operations) and an overview description of it contents. The content of an SOS
server is organised as so called "ObservationOfferings" which can be considered
as the datasets offered by the SOS server.

The SOS standard allows different ways how to organise the available observation
data into ObservationOfferings. Due to the heterogeneity of the marine use cases
that may benefit from the SOS interface, it is not possible to provide a common
rule how such data sets shall be defined.

**Recommendation SOS_01: An SOS server shall provide all marine datasets via
separate ObservationOfferings. In addition, the SOS 2.0 standard requires that one
ObservationOffering may only contain one procedure.**

Typical approaches for structuring ObservationOfferings are:
* All measurements taken by a specific sensor
* All measurements taken by a sensor during a certain time period
* All measurements taken by a sensor network (modelled a single procedure) for an observed property
* All measurements taken during a voyage of a research vessel (vessel modelled as a procedure)
* ...

#### DescribeSensor
This operation allows the retrieval of metadata describing the process through
which observation data were generated. In the marine domain, this is often a
sensor (e.g. detector, instrument) or sensor system (e.g. research vessel, buoy,
glider).

**Recommendation SOS_02: The response to the DescribeSensor operation should be
a SensorML 2.0 document that complies with the recommendations provided in
section 4.**

Besides the mandatory DescribeSensor request parameters, there may be a need to
consider the temporal dynamics of sensor/sensor system metadata. For example,
settings of an instrument may vary, the instruments mounted to a platform (e.g.
buoy, glider or research vessel) may change. Thus, an SOS server for marine
observation data should consider the dynamics of metadata:

**Recommendation SOS_03: An SOS server should support the validTime parameter
for the DescribeSensor operation.**

#### GetObservation
The GetObservation method allows clients to access the observations offered by an
SOS server. For this purpose, the OGC SOS 2.0 standard offers a range of query
parameters which also apply to marine applications:

| Parameter         | Explanation                                              |
| ------------------|----------------------------------------------------------|
| procedure         | Query for observations taken by a specific procedure (e.g. instrument, platform, etc.) |
| offering          | Query for observation that belong to a specific dataset (~ data set) |
| observed property | Query for observations of a specific parameter |
| temporal filter   | Query for observations that fulfil a temporal filter (e.g. within a time period) |
| featureOfInterest | Query for observations that relate to a given feature of interest (e.g. observations taken at a certain station) |
| spatialFilter     | Query for observations that fulfil a spatial filter (e.g. within a bounding box) |

* **TODO Explain spatial and temporal filters**
* **TODO Explain feature model in general consideration**

Many marine sensors are mounted on mobile platforms such as gliders or research
vessels. Thus, the data delivered by these sensors does not relate to one single
position but to changing locations. Depending on the platform and sensors, each
observation might refer to a different location. To allow an efficient spatial
filtering of observations in GetObservation requests, the Spatial Filtering
Profile of the SOS 2.0 standard allows to handle the location of an observation
as an O&M parameter of the observation.

**Recommendation SOS_04: SOS servers that provide access to observations of mobile
sensors shall support the Spatial Filtering Profile as defined in the SOS 2.0
standard.**

#### GetFeatureOfInterest

* Strong recommendation
* Similar to SOS Hydrology profile

#### GetDataAvailability

* Strong recommendation
* Consider approach from the INSPIRE SOS TG proposal

#### ResultHandling

* Optional

##### DescribeResultTemplate

##### GetResult

### Data Publication

#### Transactional SOS operations

* InsertSensor
* InsertObservation

#### Result Handling

* InsertResultTemplate
* InsertResult
