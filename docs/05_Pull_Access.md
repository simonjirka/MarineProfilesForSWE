---
title: 5. Interfaces for Pull-based Data Access
layout: page
---
# Interfaces for Pull-based Data Access

## OGC Sensor Observation Service 2.0

* Explain operations with a few sentences and provide explanatory list of parameters
* Show sequence diagrams to illustrate the workflow
* Limit to version 2.0.0

### Data Access

#### GetCapabilities

#### DescribeSensor

* Optional: Versioning of SensorML files; using validity time as query parameter

#### GetObservation

* parameters
 * Offering: explain what an offering is
* ObservedProperty
* Feature of interest
 * By ID
 * By spatial filter (only the basic mandatory SOS filters )
* Temporal filter
* Only the basic mandatory SOS filters
* Include spatial filtering profile

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
