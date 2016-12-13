---
title: 4. Metadata Models And Encodings
layout: page
---
# Metadata Models And Encodings

##	OGC Sensor Model Language (SensorML) 2.0

* SensorML Introduction

## Sensor Types and Instances

* Explain the differences

## Hierarchy Levels

* Not all must be included in every SensorML description but these are the suggested levels.

## Organisation of Sensor Metadata

* How to distribute the information between SensorML files (also all information in one file?)

## Basic Data Types for Providing Metadata

* Explain basic SWE Common data components
* swe:text
* swe:quantity
* swe:count
* Boolean
* dataArra
* dataRecord
* timeInstant
* timePeriod
* position
* boudingbox
* geometry
* ...

## Recommended Metadata Elements

* Diagrams with explanations of the elements
* Define subset which is mandatory
* Minimize the number of mandatory fields: only a real minimum set
*	Refer to the work on vocabularies; Minimum set of terms/elements must be available in vocabularies
* Values may be terms from vocabulary; map core elements to the basic data types; map certain properties to recommendations for the best suited swe data type

### Common Metadata Elements

The metadata elements introcued in this subsection are independent from a
specific hierarchy level. They may be used in different contexts (e.g. sensor
systems, components, etc.).

#### gml:idenfifier

| gml:identifier    |
| ------------------|----------------------------------------------------------|
| Recommendation    | Mandatory                                                |
| Explanation       | The gml:identifier is usused to identify the described object. Identifiers should be URIs (e.g. a DOI). |
| Comment           | Required by the SensorML standard; the codespace attribute shall be set to "uid" |

**TODO: Check: SensorML spec refers described object while other approaches refer to the description object.**

##### Example
    TODO <gml:identifier codeSpace="uid">xx</gml:identifier>


#### gml:name

| gml:name          |
| ------------------|----------------------------------------------------------|
| Recommendation    | Optional, not recommended                                |
| Explanation       | This element provides a common name for the described resource (e.g. instrument, platform, etc.).  |
| Comment           | sml:identifier elements may be used instead.             |

##### Example
    <gml:name>Example hydrophone 123</gml:name>


#### gml:description

| gml:description   |
| ------------------|----------------------------------------------------------|
| Recommendation    | Optional, recommended                                    |
| Explanation       | This element provides a textual description of the described resource (e.g. instrument, platform, etc.). |
| Comment           | This is very useful when displaying the results of a catalog search.|

##### Example
    <gml:description>This is an exmaple of a hydrophone attached to the example obsevatory operated by an example organisation. </gml:description>


#### sml:keywords

| sml:keywords      |
| ------------------|----------------------------------------------------------|
| Recommendation    | Optional, recommended                                  |
| Explanation       | The keywords element may contain multiple KeywordList elements which may again multiple keyword elements. The keyword elements may either contain human readable terms or URIs pointing to dictionary entries. |
| Comment           | Very useful for charaterizing a described resource and important for discovery purposes. It is recommended to have one KeywordList with human readable terms. These can be for example displayed within result lists of sensor discovery tools. |

**TODO: What about terms from vocabularies?**

##### Example
    <sml:keywords>
       <sml:KeywordList>
          <sml:keyword>Ocean Acoustics</sml:keyword>
          <sml:keyword>Hydrophone</sml:keyword>
          <sml:keyword>North Sea</sml:keyword>
       </sml:KeywordList>
    </sml:keywords>   


#### sml:identification

| sml:identification |
| -------------------|---------------------------------------------------------|
| Recommendation     | Mandatory                                               |
| Explanation        | The identification element may contain multiple IdentifierList elements which may again multiple indentifier elements. Each identifier element takes a Term as its value. The Term element has an optional but strongly recommended definition attribute that should reference a resolvable definition of the term within an online vocabulary. |
| Comment            | See below for required/recommended identifier definitions for which identifiers shall/should be provided. |

##### Required/Recommended Types of Identifiers
| Name              | Requiered/Recommended | Reference to Vocabulary | Explanation |
|-------------------|-----------------------|-------------------------|-------------|
| Unique ID         | Required              | ** TODO **              | Unique id for referring to the specific ressource (e.g. instrument, platform, etc.). |
| Short name        |
| Long name         |
| Serial number     |
| Model number      |
| Manufacturer name |
| ** TODO **        |

##### Example
    TODO


#### sml:classification

| sml:classification |
| -------------------|---------------------------------------------------------|
| Recommendation     | Mandatory                                               |
| Explanation        | The classification element may contain multiple ClassifierList elements which may again multiple classifier elements. Each classifier element takes a Term as its value. The Term element has an optional but strongly recommended definition attribute that should reference a resolvable definition of the term within an online vocabulary. |
| Comment            | Optional in the SensorML 2.0 standard but essential for categorizing the described resource (e.g. platform type, application domain, etc.). See below for required/recommended identifier definitions for which identifiers shall/should be provided. |

##### Required/Recommended Types of Classifiers
| Name               | Requiered/Recommended | Reference to Vocabulary | Explanation |
|--------------------|-----------------------|-------------------------|-------------|
| Applicaton domain  | Recommended           | ** TODO **              | Application domain for which the described resource is intended (e.g. marine science) |
| Platform type      | Recommended           | ** TODO **              | Type of the platform that is described by the SensorML document (e.g. buoy, glider, etc.). |
| Instrument type    |
| ** TODO **         |

##### Example
    TODO


#### sml:capabilities

| sml:capabilities   |
| ------------------|----------------------------------------------------------|
| Recommendation    |  Optional, recommended                                   |
| Explanation       |  This element may be used for describing what a resource (e.g. instrument or platform) is capable of. The capabilities element contains a CapabilitiesList as its value. The CapabilitiesList element consists of capability elements which may contain any SWE Common data component (see above) as value. The SWE Common data components have an optional but strongly recommended definition attribute that should reference a resolvable definition of the term within an online vocabulary. |
| Comment           | Important to assess the suitability of a certain sensor or platform for certain applications (e.g. maximum depth of a glider, resolution of a detector, etc.) |


##### Required/Recommended Types of Capabilities
| Name                    | Requiered/Recommended | Reference to Vocabulary | Suitable SWE Common Data Component | Explanation |
|-------------------------|-----------------------|-------------------------|------------------------------------|-------------|
| Temporal resolution     | Recommended           | ** TODO **              | swe:Quantity                       | ** TODO **  |
| Maximum operating depth | Recommended           | ** TODO **              | swe:Quantity                       | ** TODO **  |
| Spectral resolution     |
| Sensitivity             |
| ** TODO **              |

##### Example
    TODO


#### sml:characteristics

| sml:characteristics    |
| ------------------|----------------------------------------------------------|
| Recommendation    | Optional, recommended                                    |
| Explanation       | This element may be used for describing properties/characteristics of a resource (e.g. instrument or platform). The characteristics element contains a CharacteristicsList as its value. The CharacteristicsList element consists of characteristic elements which may contain any SWE Common data component (see above) as value. The SWE Common data components have an optional but strongly recommended definition attribute that should reference a resolvable definition of the term within an online vocabulary. |
| Comment           |  |


##### Required/Recommended Types of Characteristics
| Name                    | Requiered/Recommended | Reference to Vocabulary | Suitable SWE Common Data Component | Explanation |
|-------------------------|-----------------------|-------------------------|------------------------------------|-------------|
| Material                | Recommended           | ** TODO **              | swe:Text                           | ** TODO **  |
| Length                  | Recommended           | ** TODO **              | swe:Quantity                       | ** TODO **  |
| Width                   |
| Height                  |
| Weight                  |
| ** TODO **              |


##### Example
    TODO


#### sml:outputs

| sml:outputs   |
| ------------------|-----------------------------------------------------------------|
| Recommendation    | Optional, recommended / Mandatory for detectors and instruments |
| Explanation       |      j   |
| Comment           | Important to describe the data of an instrument, platform, etc..  |


##### Example
    TODO


### Network

### Platform

#### Platform Types

#### Platform Instance

### Instrument

#### Instrument Types

#### Instrument Instance

### Detector

#### Detector Types

#### Detector Instance
