---
title: |
    Georeferencing and mapping FAME data
authors:
- Nicolas Palominos
date: 2018-06-26
reviewers:
layout: lesson
---

## Georeferencing and mapping FAME data

Learn how to georeference FAME data and create an interactive map in CARTO


## Contents

[1. Lesson goals](#1.-Lesson-goals)

[2. Lesson structure](#2.-Lesson-structure)

[3. Getting Started](#3.-Getting-Started)

[4. Creating an interactive map of FAME data](#4.-Creating-an-interactive-map-of-FAME-data)

   * [Georeferencing FAME data in QGIS](#*-Georeferencing-FAME-data-in-QGIS)
    
   * [Mapping FAME data in CARTO](#*-Mapping-FAME-data-in-CARTO)


### 1. Lesson goals

The purpose of this lesson is to learn how to create an interactive map that enables the user to explore the geographic and spatial relations between economic activities according to their trading addresses.
By the end of this lesson you would be able to:
* Identify and collect the relevant data
* Perform basic operations to manipulate the data in QGIS
* Create an interactive map to visualise the data in CARTO

### 2. Lesson structure

The lesson is organised in three sections. The first section is an introduction to the resources needed to perform the next steps. The second section will focus on data manipulation in the QGIS environment. The final section refers to creating an interactive map in the CARTO platform.

### 3. Getting Started

Disclaimer: 

**Mapping**
While the definition of [maps](https://en.wikipedia.org/wiki/Mapping) refers in general to the description of relationships between elements (e.g.: ideas, nodes) for the purpose of this lesson we will understand mapping in the [cartographic](https://en.wikipedia.org/wiki/Cartography) sense, which states *that reality can be modeled in ways that communicate spatial information effectively*. As such, in the information age, mapping has emerged as a means to make the complex accesible, the hidden visible (Abrams and Hall, 2004).

> Think for example of attempting to understand the relationship between businesses from a list of addressess.

**Georeferencing**
In simple terms [georeferencing](https://www.ordnancesurvey.co.uk/support/understanding-gis/georeferencing.html) means referencing spatial data to a location on the earth's surface. The expresion of the position (or the location) of the data is done according to a reference and [coordinate systems](https://en.wikipedia.org/wiki/Coordinate_system)(mathematical determination of an element's position). Briefly speaking, spatial reference systems (SRS) or coordinate reference systems (CRS) are standarized by the OGC (Open Geospatial Consortium) and defines a specific map projection (e.g.: Mercator, Gall-Peters, Robinson, Stereographic). The selection of the correct CRS is crucial because the spatial representation varies considerably between the different reference systems.

![Projection comparison](https://snag.gy/sSRXdb.jpg)

> Most maps are based on the [Mercator projection](https://www.huffingtonpost.co.uk/entry/true-size-map-relative-size-of-countries_us_55eed0f5e4b002d5c076789d?guccounter=1), which has been critisized for misrepresenenting Europe and North America as larger areas *giving white nations a sense of supremacy over non-white nations* (Source: [Geoawsomeness](http://geoawesomeness.com/best-map-projection/)).

### 4. Creating an interactive map of FAME data

For the creation of an interactive map we will follow two steps

**\* Georeferencing FAME data in QGIS**
* Mapping FAME data in CARTO
