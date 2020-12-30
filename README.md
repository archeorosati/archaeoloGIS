# ArchaeoloGIS
## A QGIS processing toolbox for archaeologists spatial analysis

ArchaeoloGIS is a QGIS plugin, it is in a testing mode, feel free to clone the folder and install by the zip installation of QGIS plugins. 
Will be compose by some scripts today 30/12/2020 we have one only tool, but I'm programming some other.

First script: Tabula Peutingeriana (now available)
Second script: (will release soon)


## 1. Tabula Peutingeriana user manual

What is the Tabula Peutingeriana? Click here for furter informations: [*Tabula Peutingeriana*](https://en.wikipedia.org/wiki/Tabula_Peutingeriana).
The *Tabula Peutingeriana* script simulates the COUNTING of roman miles in the "*Tabula Peutingeriana*" way.
Before using the script, you must draw the network road layer paying attention to the sequent indications.

The **Road Network** must be a multi-lines, draw in QGIS in any QGIS vector format and projected in any SRID. 
The most important rule is to draw in a "Tabula Peutingeriana Way" as I expose in a sequent paragraphs. 
The *Tabula* has a sense of drawing, each road is formed by some segments, each segment has the count of its length in roman miles as in the image.

![Tabula Peutingeriana](https://github.com/archeorosati/archaeoloGIS/blob/main/Images/tabula-peutingeriana.jpg)

Image 1: a piece of the Tabula Peutingeriana focusing on Palestina (red lines the roads segments)

Each segment has its own count and starts from a city (*municipium*), a village (*vicus*), a station (*statio*), or a generic pivotal geographic place, and finish to the next one.

To working with the script the hub will made in the same way, remember to draw each road ever from a central geographical point: the *urbs* of Rome, a *municipium*, a *statio* etc. and must end to the sequent pivotal place. You can decide to refer your hub and replicate the Tabula or not; the *Tabula* was the map of the late-antique Roman world, the known inhabited world (*ecumene*) and you can free use it to draw your hub to understand the administration of the late-antique romans provinces.

![Tabula Peutingeriana2](https://github.com/archeorosati/archaeoloGIS/blob/main/Images/tp_roma_vs.jpg)

Image 2: focus on Rome in the Tabula Peutingeriana (red lines the roads segments with name and miles until the next start of a new segment)

### Resume:
- Draw vector QGIS lines
- Ever from a starting area or point, every each road **must start** from the center of your research (ex. Rome, Anthiochia, Londinium etc.)
- Draw segments as in the *Tabula Peutingeriana* (ex. from a roman city to a village, then to a station, then to antother city)
- The Roman Road Network **must be made** by a moltitude of lines (do not unite the segment of the network)  

### Before launching the script:
After the installation, the script will be in the "Processing Toolbar" at the right of the QGIS software.
Drawing the lines it doesn't metter the database core, or the name of the columns you insert inside your Roman Road Network layer, you have to know just that the result of the script, the two point layers, will hereditate all the informations. 

### Some suggesting columns: 
It can be useful to insert an ID column and the name of the road (ex. *Via Egnatia* or *Bononia-Ariminium*), can easly refer the miliaria points.

### Input Layer:
Input Vector Layer --> Load the Road Network line hub.

### Script results:
The script will return two results:

**1. Roman Miliaria (interpolated points):** 
it is a point layer, one point each roman mile (1480 meters). The database of this layer will contain as I say all the information referring to their own segments and two new columns: Distance and Angle.
 - **Distance**: the distance of the miliarium (point) from the previous start of the segment.
 - **Angle**: the angle of the road direction, 0 = North, 90 = Est, 180 = South, 270 = West.
 
**2. Roman Milia (incremented):**
it is also a point layer, the second result contains all the information of the "Roman Miliaria" and in addiction one only column: "Miliarium" wich indicate the number of miles from the starting point of the segment. You can use this layer and this column for labelling the layer and make useful map for prooving your late-antique researches and theories on the Roman Road Network.

![Tabula Peutingeriana2](https://github.com/archeorosati/archaeoloGIS/blob/main/Images/18983388_1549968645076978_902180483_n.jpg)

Image 3: focus on Padania Plan (Northen Italy) in the Tabula Peutingeriana (red lines the roads segments with name and miles until the next start of a new segment)
