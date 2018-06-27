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

[3. Introduction(#3.-Introduction)

[4. Getting started](#4.-Getting started)

[5. Georeferencing FAME data in QGIS](#5.-Georeferencing-FAME-data-in-QGIS)
    
[6. Mapping FAME data in CARTO](#6.-Mapping-FAME-data-in-CARTO)


### 1. Lesson goals

The purpose of this lesson is to learn how to create an interactive map that enables the user to explore geographic and spatial relations between economic activities according to their trading addresses.
By the end of this lesson you would be able to:
* Identify and collect the relevant data
* Perform basic operations to manipulate the data in QGIS
* Create an interactive map to visualise the data in CARTO

### 2. Lesson structure

The lesson is organised in four sections. The first section is an introduction to basic concepts of cartography and mapping. The following section describes the resources needed to create an interactive map. The third section will focus on data manipulation in the QGIS environment. Finally, the last section refers to creating an interactive map on the CARTO platform.

### 3. Introduction

Disclaimer: 

**Mapping**

While the definition of [maps](https://en.wikipedia.org/wiki/Mapping) refers in general to the description of relationships between elements (e.g.: ideas, nodes) for the purpose of this lesson we will understand mapping in the [cartographic](https://en.wikipedia.org/wiki/Cartography) sense, which states *that reality can be modeled in ways that communicate spatial information effectively*. As such, in the information age, mapping has emerged as a means to make the complex accesible, the hidden visible (Abrams and Hall, 2004).

> Think for example of attempting to understand the relationship between businesses from a list of addressess.

**Georeferencing**

In simple terms [georeferencing](https://www.ordnancesurvey.co.uk/support/understanding-gis/georeferencing.html) means referencing spatial data to a location on the earth's surface. The expresion of the position (or the location) of the data is done according to a reference and [coordinate systems](https://en.wikipedia.org/wiki/Coordinate_system)(mathematical determination of an element's position). Briefly speaking, spatial reference systems (SRS) or coordinate reference systems (CRS) are standarized by the OGC (Open Geospatial Consortium) and defines a specific map projection (e.g.: Mercator, Gall-Peters, Robinson, Stereographic). The selection of the correct CRS is crucial because the spatial representation varies considerably between the different reference systems.

![Projection comparison](https://snag.gy/sSRXdb.jpg)

> Most maps are based on the [Mercator projection](https://www.huffingtonpost.co.uk/entry/true-size-map-relative-size-of-countries_us_55eed0f5e4b002d5c076789d?guccounter=1), which has been critisized for misrepresenenting Europe and North America as larger areas *giving white nations a sense of supremacy over non-white nations* (Source: [Geoawsomeness](http://geoawesomeness.com/best-map-projection/)).

### 4. Getting started

For the creation of an interactive map we will follow two general stages: 1) Georeferencing and 2) Mapping. For this purpose you will need to have QGIS installed in your computer and an account on CARTO. 

[QGIS](https://en.wikipedia.org/wiki/QGIS) is a free and open-source cross-platform desktop geographic information system (GIS) application that supports viewing, editing, and analysis of geospatial data. To install it navigate to the [QGIS download page](https://qgis.org/en/site/forusers/download.html) an follow the instructions. For more a more detailed set of instructions and troubleshooting you can consult this guide to [installing QGIS](https://programminghistorian.org/en/lessons/qgis-layers).

[CARTO](https://en.wikipedia.org/wiki/CartoDB) is a cloud computing platform that provides GIS and web mapping tools for display in a web browser. CARTO is offered as freemium service, where accounts are free up to a certain time. Current free account options include a [CARTO 30 days trial](https://carto.com/get-started/) and a [student account in partnership with Github](https://carto.com/community/ambassadors/) (this one might take longer to get).

### 5. Georeferencing FAME data in QGIS

The first step before going into QGIS is getting the data from the FAME database (Financial Management Made Easy) published by Bureau van Dijk. The access to the FAME database you will need to log in to the [UCL library database](http://www.ucl.ac.uk/library/electronic-resources/databases) resources with your student credentials. After loging into the FAME website the first step is to search by geographic area and postcode (Geographic/Postcode). We need to specify a Postcode range indicating the 'from' and 'to' (Outward code should be enough to perform the query).

[![https://gyazo.com/5944f1918b4eb35648448d3dcee5a10d](https://i.gyazo.com/5944f1918b4eb35648448d3dcee5a10d.png)](https://gyazo.com/5944f1918b4eb35648448d3dcee5a10d)




search for the European Classification of Economic Activities code, or NACE code (Other activities classification/All NACE Rev. 2 codes)

### 6. Mapping FAME data in CARTO
