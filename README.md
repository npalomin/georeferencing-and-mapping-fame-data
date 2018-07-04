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

[3. Introduction](#3.-Introduction)

[4. Getting started](#4.-Getting-started)

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

> Most maps are based on the [Mercator projection](https://www.huffingtonpost.co.uk/entry/true-size-map-relative-size-of-countries_us_55eed0f5e4b002d5c076789d?guccounter=1), however, it has been critisized for misrepresenenting Europe and North America as larger areas *giving white nations a sense of supremacy over non-white nations* (Source: [Geoawsomeness](http://geoawesomeness.com/best-map-projection/)).

### 4. Getting started

For the creation of an interactive map we will follow two general stages: 1) Georeferencing and 2) Mapping. For this purpose you will need to have QGIS installed in your computer and an account on CARTO. 

[QGIS](https://en.wikipedia.org/wiki/QGIS) is a free and open-source cross-platform desktop geographic information system (GIS) application that supports viewing, editing, and analysis of geospatial data. To install it navigate to the [QGIS download page](https://qgis.org/en/site/forusers/download.html) an follow the instructions. For more a more detailed set of instructions and troubleshooting you can consult this guide to [installing QGIS](https://programminghistorian.org/en/lessons/qgis-layers). The version used in this lesson is QGIS 2.18 Las Palmas.

[CARTO](https://en.wikipedia.org/wiki/CartoDB) is a cloud computing platform that provides GIS and web mapping tools for display in a web browser. CARTO is offered as freemium service, where accounts are free up to a certain time. Current free account options include a [CARTO 30 days trial](https://carto.com/get-started/) and a [student account in partnership with Github](https://carto.com/community/ambassadors/) (this one might take longer to get).

### 5. Georeferencing FAME data in QGIS

The first step before going into QGIS is getting the data from the FAME database (Financial Management Made Easy) published by Bureau van Dijk. The access to the FAME database you will need to log in to the [UCL library database](http://www.ucl.ac.uk/library/electronic-resources/databases) resources with your student credentials. After loging in to the FAME website the first step is to search by geographic area and postcode (**Geographic / Postcode**). To get a reference of postcode geographic coverage vist the [Office for National Statistics postcode directory](https://onsdigital.github.io/postcode-lookup/) lookup. We need to specify a Postcode range indicating the 'from' and 'to' (Outward code should be enough to perform the query).

[![https://gyazo.com/5944f1918b4eb35648448d3dcee5a10d](https://i.gyazo.com/5944f1918b4eb35648448d3dcee5a10d.png)](https://gyazo.com/5944f1918b4eb35648448d3dcee5a10d)

After indicating the postcode range you should be able to perform the query. 

Add / Ok / View results > / Add/remove columns 

[![https://gyazo.com/cb4d8dd7c62e72773ed2d5b37e101ab9](https://i.gyazo.com/cb4d8dd7c62e72773ed2d5b37e101ab9.gif)](https://gyazo.com/cb4d8dd7c62e72773ed2d5b37e101ab9)

Then, to obtain the latitude and longitude of the primary trading address from the selected activities click on the following sections:

**Add/remove columns /
Trading addresses / 
Primary trading address / 
Primary trading address Latitude / 
Primary trading address Longitude / 
Apply / 
Excel / 
Export / 
Download**

The sheet named 'Results' on your exported excel file should look like this:

[![https://gyazo.com/92f3cdf905dd68b128dfee6f2e0a4228](https://i.gyazo.com/92f3cdf905dd68b128dfee6f2e0a4228.png)](https://gyazo.com/92f3cdf905dd68b128dfee6f2e0a4228)

Note that some activities don't have the Latitude-Longitude information. Also, others are located in the same geographic position (equal coordinates) which might imply that these are in the same building.

Next step is to save the 'Results' sheet as a CSV file.

Comma Separared Values(.csv) - (not CSV UTF-8) / Save Active Sheet

[![https://gyazo.com/273934822839209c9b467486ca58f64f](https://i.gyazo.com/273934822839209c9b467486ca58f64f.gif)](https://gyazo.com/273934822839209c9b467486ca58f64f)

---

Next, open QGIS and click trough the following sequences:

* To create a new project:

**Project /
New /**

Note in the lower right corner that the project's default CRS (Coordinate Reference System) would be EPSG:4326, which is equivalent to [WGS 84](https://en.wikipedia.org/wiki/World_Geodetic_System), the latest revision of the World Geodesic System established in 1984.

[![Image from Gyazo](https://i.gyazo.com/c901dd020c6041215b80629538185bf4.png)](https://gyazo.com/c901dd020c6041215b80629538185bf4)

* To import the CSV file information:

**Layer /
Add layer /
Add Delimited Text Layer /**

On the pop-up window browse the CSV file. Set the **Encoding** to System and verify that the **DMS** box is checked (DMS stands for Degree Minutes Seconds). The software should recognise the CSV file information, however if not, configure the window according to the following image. **X field** is Latitude and **Y field** is Longitude:

[![Image from Gyazo](https://i.gyazo.com/cf59070c25d7a770a80c327ecda9793b.png)](https://gyazo.com/cf59070c25d7a770a80c327ecda9793b)

Then, hit **OK** and a *Coordinate Reference System Selector* window should pop-up. Again, the software by default should have selected **WGS 84 EPSG:4326**, which is the standard for online maps. If not, select the CRS from the list and then hit **OK**.

[![Image from Gyazo](https://i.gyazo.com/023de44742d333a52c4ef7c2f2a10858.png)](https://gyazo.com/023de44742d333a52c4ef7c2f2a10858)

Now, on the main window you should be able to see a set of points that represent the geographic position of the activities queried. On the left hand side, on the **Layers Panel**, you will see that your data was added as a layer:

[![Image from Gyazo](https://i.gyazo.com/14187b46f2702d61616c4c726322c5b0.png)](https://gyazo.com/14187b46f2702d61616c4c726322c5b0)

For a basic exploration of your map use the navigational tools on the toolbar. Also, the wheel on your mouse will behave in a similar way to navigating a Google Map.

[![Image from Gyazo](https://i.gyazo.com/0598ca24ee5ca2b7f6e4180dbc01ba13.png)](https://gyazo.com/0598ca24ee5ca2b7f6e4180dbc01ba13)

To query the information associated with each point click on the **Identify Features** botton [![Image from Gyazo](https://i.gyazo.com/f848640cc3ba1294e419851d186c44cc.png)](https://gyazo.com/f848640cc3ba1294e419851d186c44cc). A window will pop-up showing the 'Attributes' (columns) of each point:

[![Image from Gyazo](https://i.gyazo.com/c6a96d1d1ebfa3442fea77c71334f837.png)](https://gyazo.com/c6a96d1d1ebfa3442fea77c71334f837)

Note that one point might have more than one set of information. This means that some activities share the same 'Primary trading address Latitude and Longitude', so the points overlap and the identify tool shows the information for all the points.

To query all the records click ont the **Open Attribute Table** botton [![Image from Gyazo](https://i.gyazo.com/a084bc32fba7a902727a6ffdeead5b6b.png)](https://gyazo.com/a084bc32fba7a902727a6ffdeead5b6b). A window will pop-up showing a spreadsheet with all the records (including those which Latitude-Longitude was blank):

[![Image from Gyazo](https://i.gyazo.com/84c5e09b597252e837d41eb8e12e6a48.png)](https://gyazo.com/84c5e09b597252e837d41eb8e12e6a48)

In order to visually analyse the spatial distribution of the points we need to 'see' all of them. Therefore, we need to spatially 'separate' those points that overlap. For this, we will 'displace' the overlapping points in relation to their current location. This will create a 'distorted' representation of the point's 'real' position but this is the trade-off to be able to visualise all the points which at the end will provide a more accurate spatial analysis (without any 'hidden' points).

Before running the displacement operation it is recommended to perfomr a validity check of the geometries:

**Vector / Geometry Tools / Check validity**

In the pop-up window keep the default values, uncheck the last two boxes and click **Run**:

[![Image from Gyazo](https://i.gyazo.com/62f7b839a6662a140e68a92611974a37.png)](https://gyazo.com/62f7b839a6662a140e68a92611974a37)

After running this process you would have created a new layer 'Valid output'. This will be your new working data.

Next, to perform the point 'displacement' we need to call the QGIS toolbox:

**Processing / Toolbox**

Then, in the search box search for *displacement* and click on the **Point displacement** section:

[![Image from Gyazo](https://i.gyazo.com/e190fc28e2bd1ad0df26aa5dbd350057.png)](https://gyazo.com/e190fc28e2bd1ad0df26aa5dbd350057)

Select the input layer 'Valid output', keep the dafault values and click **Run**:



### 6. Mapping FAME data in CARTO
