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

* Explain basic data types
* text
* quantity
* count
* Boolean
* dataArra
* dataRecord
* timeInstant
* timePeriod
* position
* boudingbox
* polygon
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


#### sml:classification

| sml:classification    |
| ------------------|----------------------------------------------------------|
| Recommendation    | Mandatory                                                |
| Explanation       |      j   |
| Comment           | Optional in the SensorML 2.0 standard but essential for categorizing the described resource (e.g. platform type, application domain, etc.) |

##### Example
    TODO


#### sml:capabilities

| sml:capabilities   |
| ------------------|----------------------------------------------------------|
| Recommendation    |  Optional, recommended                                   |
| Explanation       |      j   |
| Comment           | Important to assess the suitability of a certain sensor or platform for certain applications (e.g. maximum depth of a glider, resolution of a detector, etc.) |

##### Example
    TODO


#### sml:characteristics

| sml:characteristics    |
| ------------------|----------------------------------------------------------|
| Recommendation    | Optional, recommended                                    |
| Explanation       |      j   |
| Comment           | re |

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
