---
title: "Trupti Agarwal"
author: "Trupti Agarwal"
date: "30/07/2021"
slug: []
categories:
  - R
tags:
  - R Markdown
image: https://www.alice-in-wonderland.net/wp-content/uploads/7.jpg
caption: ''
preview: yes
output:
  blogdown::html_page:
    toc: no
    fig_width: 5
    fig_height: 5
    keep_md: yes
description: Hi! I am Trupti Agarwal. I am a first year student studying Human Centred Design at Srishti Manipal Institute.
---



## Introduction
Hi! I am Trupti Agarwal. I am a first year student studying Human Centred Design at Srishti Manipal Institute. Using R Programming language, I have plotted different kinds of graph on 3 different datasets. 

## Graph 1

This dataset shows the various types of items that are banned in different schools across the United States. 
The schoolName coloumn are the kinds of schools in different states of the United States. The type column are the kinds of things and items are the types of items under type of things. Eg backpacks is type of an accessory. Prohibited is where types of items are banned accoridng to the gender. So if it banned for both, then it is none and if it is only banned for males, then the particular row says male. 


```
## Rows: 15,144
## Columns: 5
## $ schoolName <chr> "RUSK H S", "RUSK H S", "EAST HIGH", "TOMAHAWK HIGH", "TOMA~
## $ state      <chr> "TX", "TX", "UT", "WI", "WI", "WI", "WI", "WI", "OK", "TX",~
## $ item       <chr> "pillows", "stuffed animals", "dangling belts", "wallet cha~
## $ type       <chr> "accessories", "accessories", "accessories", "accessories",~
## $ prohibited <chr> "none", "none", "none", "none", "none", "none", "none", "no~
```

The graph below shows the number of schools that have banned alcohol, drugs and tobacco in respective states across the United States. 
Alcohol, Drugs and Tobacco are the items that fall into the type of Promotion in the column. 

<img src="index_files/figure-html/plot-1-1.png" width="480" />
According to the data, Texas has the highest number of schools that have banned all the three items and Alaska has the lowest number of schools banning the items. Montana and Nevada have allowed drugs since there is no green colour for them in the graph. 
To show the data more clearly, i have colour coded the items and have placed them in an ascending order. 

## Graph 2

This dataset is on the TV show, F.R.I.E.N.D.S. The chosen dataset is based on season 1, episode 7-10. The node dataset contains the information of the characters that are present in the given episodes. It contains their names, gender, profession and their personality traits. 
the edge dataset contains the cpnversation between two people and the number of times they have spoken is given in the Weight coloumn. Type is the kind of relationship the two people share between eachother. 
Hence we are trying to plot a network between the characters and see the strength of the relationships between each other. 


```
## # A tibble: 22 x 7
##    Numbers Name             Sex   Profession     `Animal Lover` `Relationship ~`
##      <dbl> <chr>            <chr> <chr>          <chr>          <chr>           
##  1       1 "Chandler Bing " M     "statistical ~ No             Dating          
##  2       2 "Phoebe Buffay"  F     "Self - taugh~ Yes            Dating          
##  3       3 "Rachel Green"   F     "Waitress"     Yes            Dating          
##  4       4 "Ross Geller"    M     "Paleantologi~ Yes            Divorced        
##  5       5 "Monica Geller"  F     "Chef"         Yes            Dating          
##  6       6 "Joey Tribbiani" M     "Actor"        Yes            Single          
##  7       7 "Paolo"          M     "Actor"        Yes            Dating          
##  8       8 "Jill Goodacre"  F     "Model"        <NA>           Single          
##  9       9 "Mr. Heckles"    M     "Retired"      No             Widower         
## 10      10 "Jack Geller "   M     "Lawyer"       Yes            Married         
## # ... with 12 more rows, and 1 more variable: `Character Trait` <chr>
```

```
## # A tibble: 50 x 4
##    `From `    To Weight Type      
##      <dbl> <dbl>  <dbl> <chr>     
##  1       2     5     12 Friends   
##  2       1     8      1 Inftuation
##  3       5     1     10 Friends   
##  4       6     1     11 Roommates 
##  5       5     6      9 Friends   
##  6       4     2     12 Friends   
##  7       3     4     14 Inftuation
##  8       4     6     13 Friends   
##  9       3     9      1 Neighbours
## 10       2     9      1 Neighbours
## # ... with 40 more rows
```


```
## # A tbl_graph: 22 nodes and 50 edges
## #
## # An undirected simple graph with 1 component
## #
## # Node Data: 22 x 7 (active)
##   Numbers Name  Sex   Profession `Animal Lover` `Relationship ~`
##     <dbl> <chr> <chr> <chr>      <chr>          <chr>           
## 1       1 "Cha~ M     "statisti~ No             Dating          
## 2       2 "Pho~ F     "Self - t~ Yes            Dating          
## 3       3 "Rac~ F     "Waitress" Yes            Dating          
## 4       4 "Ros~ M     "Paleanto~ Yes            Divorced        
## 5       5 "Mon~ F     "Chef"     Yes            Dating          
## 6       6 "Joe~ M     "Actor"    Yes            Single          
## # ... with 16 more rows, and 1 more variable: `Character Trait` <chr>
## #
## # Edge Data: 50 x 4
##    from    to Weight Type      
##   <int> <int>  <dbl> <chr>     
## 1     2     5     12 Friends   
## 2     1     8      1 Inftuation
## 3     1     5     10 Friends   
## # ... with 47 more rows
```

In the grapg below, we have plotted the connections between all the characters in those episodes of the show. the lines are colour coded that are according to the type of relationship between each other. the thickness of the lines shows the number of times they have had a converstaion with each other. Hence, greater the thickness of lines, greater is the bond between them. 


```
## Warning in grid.Call(C_stringMetric, as.graphicsAnnot(x$label)): font family not
## found in Windows font database

## Warning in grid.Call(C_stringMetric, as.graphicsAnnot(x$label)): font family not
## found in Windows font database
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database
```

<img src="index_files/figure-html/plot-2-1.png" width="480" />

## Graph 3

This dataset shows depicts the number of restaurants that are there in Banajara Hills, Hyderabad according to the cuisine in the respective restuarants. The data of bulidings, parks, roads and restaurants is gathered by the package, osmdata that gives the data according to the location using Longitudes and Latitudes. 



First, we extract the data from osmdata package and then save in the bbox. Then we write the data and save it in a file and then we read the data again. Then we read data of the restaurants according to the cuisines. Whatever are empty/ Not applicable are removed and then we plot the graph. 


```
## Reading layer `buildings' from data source 
##   `C:\Users\Arvind\My Drive\R work\MyWebsites\dtt-2021-2022\content\portfolio\Trupti Agarwal\buildings.gpkg' 
##   using driver `GPKG'
## Simple feature collection with 17529 features and 71 fields
## Geometry type: POLYGON
## Dimension:     XY
## Bounding box:  xmin: 78.41962 ymin: 17.39732 xmax: 78.46071 ymax: 17.43843
## Geodetic CRS:  WGS 84
```

```
## Reading layer `roads' from data source 
##   `C:\Users\Arvind\My Drive\R work\MyWebsites\dtt-2021-2022\content\portfolio\Trupti Agarwal\roads.gpkg' 
##   using driver `GPKG'
## Simple feature collection with 2499 features and 34 fields
## Geometry type: LINESTRING
## Dimension:     XY
## Bounding box:  xmin: 78.41649 ymin: 17.39516 xmax: 78.46421 ymax: 17.44087
## Geodetic CRS:  WGS 84
```

```
## Reading layer `parks' from data source 
##   `C:\Users\Arvind\My Drive\R work\MyWebsites\dtt-2021-2022\content\portfolio\Trupti Agarwal\parks.gpkg' 
##   using driver `GPKG'
## Simple feature collection with 55 features and 7 fields
## Geometry type: POLYGON
## Dimension:     XY
## Bounding box:  xmin: 78.41975 ymin: 17.3974 xmax: 78.45959 ymax: 17.43847
## Geodetic CRS:  WGS 84
```

```
## Reading layer `restaurants' from data source 
##   `C:\Users\Arvind\My Drive\R work\MyWebsites\dtt-2021-2022\content\portfolio\Trupti Agarwal\restaurants.gpkg' 
##   using driver `GPKG'
## Simple feature collection with 793 features and 82 fields
## Geometry type: POINT
## Dimension:     XY
## Bounding box:  xmin: 78.41994 ymin: 17.39783 xmax: 78.4598 ymax: 17.43832
## Geodetic CRS:  WGS 84
```

```
## [1] 793
```

```
##  [1] "osm_id"                "name"                  "addr.city"            
##  [4] "addr.district"         "addr.full"             "addr.housename"       
##  [7] "addr.housenumber"      "addr.postcode"         "addr.state"           
## [10] "addr.street"           "addr.subdistrict"      "amenity"              
## [13] "atm"                   "barrier"               "branch"               
## [16] "brand"                 "brand.ks"              "brand.pa"             
## [19] "brand.ur"              "brand.wikidata"        "brand.wikipedia"      
## [22] "brand.wikipedia.pa"    "brand.wikipedia.ur"    "building"             
## [25] "capacity"              "contact.email"         "contact.mobile"       
## [28] "contact.phone"         "contact.website"       "created_by"           
## [31] "cuisine"               "delivery"              "denomination"         
## [34] "description"           "designation"           "diet.vegetarian"      
## [37] "dispensing"            "email"                 "emergency"            
## [40] "fax"                   "fee"                   "fixme"                
## [43] "fuel.diesel"           "fuel.octane_91"        "fuel.petrol"          
## [46] "health_facility.type"  "healthcare"            "healthcare.speciality"
## [49] "internet_access"       "is_in"                 "level"                
## [52] "medical_system"        "name.ar"               "name.en"              
## [55] "name.hi"               "name.ks"               "name.pa"              
## [58] "name.ru"               "name.te"               "name.ur"              
## [61] "note"                  "official_name"         "official_name.pa"     
## [64] "official_name.ur"      "old_name"              "opening_hours"        
## [67] "opening_hours.covid19" "operator"              "operator.type"        
## [70] "outdoor_seating"       "phone"                 "religion"             
## [73] "service_times"         "shop"                  "short_name"           
## [76] "smoking"               "source"                "takeaway"             
## [79] "tourism"               "website"               "wheelchair"           
## [82] "wikidata"              "geom"
```

```
##   [1] NA                                   
##   [2] NA                                   
##   [3] NA                                   
##   [4] NA                                   
##   [5] NA                                   
##   [6] NA                                   
##   [7] NA                                   
##   [8] NA                                   
##   [9] NA                                   
##  [10] NA                                   
##  [11] NA                                   
##  [12] NA                                   
##  [13] NA                                   
##  [14] NA                                   
##  [15] NA                                   
##  [16] NA                                   
##  [17] NA                                   
##  [18] "coffee_shop"                        
##  [19] NA                                   
##  [20] "south_indian"                       
##  [21] NA                                   
##  [22] NA                                   
##  [23] NA                                   
##  [24] "regional"                           
##  [25] NA                                   
##  [26] NA                                   
##  [27] NA                                   
##  [28] NA                                   
##  [29] NA                                   
##  [30] NA                                   
##  [31] "sandwich"                           
##  [32] NA                                   
##  [33] NA                                   
##  [34] NA                                   
##  [35] "indian"                             
##  [36] NA                                   
##  [37] NA                                   
##  [38] NA                                   
##  [39] "pizza"                              
##  [40] "coffee_shop"                        
##  [41] NA                                   
##  [42] NA                                   
##  [43] NA                                   
##  [44] "regional;indian;kebab"              
##  [45] "coffee_shop"                        
##  [46] NA                                   
##  [47] NA                                   
##  [48] NA                                   
##  [49] NA                                   
##  [50] NA                                   
##  [51] "indian"                             
##  [52] NA                                   
##  [53] NA                                   
##  [54] "american"                           
##  [55] "chinese"                            
##  [56] NA                                   
##  [57] "indian"                             
##  [58] NA                                   
##  [59] "indian"                             
##  [60] NA                                   
##  [61] NA                                   
##  [62] NA                                   
##  [63] NA                                   
##  [64] NA                                   
##  [65] NA                                   
##  [66] NA                                   
##  [67] NA                                   
##  [68] NA                                   
##  [69] NA                                   
##  [70] NA                                   
##  [71] NA                                   
##  [72] NA                                   
##  [73] NA                                   
##  [74] NA                                   
##  [75] NA                                   
##  [76] NA                                   
##  [77] NA                                   
##  [78] NA                                   
##  [79] NA                                   
##  [80] NA                                   
##  [81] NA                                   
##  [82] NA                                   
##  [83] NA                                   
##  [84] NA                                   
##  [85] NA                                   
##  [86] NA                                   
##  [87] NA                                   
##  [88] "indian"                             
##  [89] NA                                   
##  [90] NA                                   
##  [91] NA                                   
##  [92] NA                                   
##  [93] NA                                   
##  [94] NA                                   
##  [95] NA                                   
##  [96] NA                                   
##  [97] "chinese"                            
##  [98] NA                                   
##  [99] NA                                   
## [100] NA                                   
## [101] NA                                   
## [102] "chicken"                            
## [103] "indian"                             
## [104] NA                                   
## [105] NA                                   
## [106] NA                                   
## [107] "ice_cream"                          
## [108] "ice_cream"                          
## [109] NA                                   
## [110] "coffee_shop"                        
## [111] NA                                   
## [112] NA                                   
## [113] NA                                   
## [114] "indian"                             
## [115] NA                                   
## [116] "indian"                             
## [117] "indian"                             
## [118] NA                                   
## [119] NA                                   
## [120] NA                                   
## [121] NA                                   
## [122] NA                                   
## [123] NA                                   
## [124] NA                                   
## [125] NA                                   
## [126] NA                                   
## [127] NA                                   
## [128] NA                                   
## [129] NA                                   
## [130] NA                                   
## [131] NA                                   
## [132] NA                                   
## [133] NA                                   
## [134] NA                                   
## [135] NA                                   
## [136] NA                                   
## [137] NA                                   
## [138] "international"                      
## [139] "tea"                                
## [140] NA                                   
## [141] NA                                   
## [142] NA                                   
## [143] "indian"                             
## [144] NA                                   
## [145] NA                                   
## [146] NA                                   
## [147] "coffee_shop"                        
## [148] "pizza"                              
## [149] NA                                   
## [150] NA                                   
## [151] NA                                   
## [152] NA                                   
## [153] NA                                   
## [154] NA                                   
## [155] NA                                   
## [156] NA                                   
## [157] NA                                   
## [158] NA                                   
## [159] NA                                   
## [160] NA                                   
## [161] NA                                   
## [162] NA                                   
## [163] NA                                   
## [164] NA                                   
## [165] NA                                   
## [166] NA                                   
## [167] NA                                   
## [168] NA                                   
## [169] NA                                   
## [170] NA                                   
## [171] NA                                   
## [172] NA                                   
## [173] NA                                   
## [174] NA                                   
## [175] NA                                   
## [176] NA                                   
## [177] NA                                   
## [178] NA                                   
## [179] NA                                   
## [180] NA                                   
## [181] NA                                   
## [182] NA                                   
## [183] NA                                   
## [184] NA                                   
## [185] "regional"                           
## [186] NA                                   
## [187] NA                                   
## [188] NA                                   
## [189] NA                                   
## [190] NA                                   
## [191] NA                                   
## [192] NA                                   
## [193] NA                                   
## [194] "indian"                             
## [195] NA                                   
## [196] "regional"                           
## [197] NA                                   
## [198] NA                                   
## [199] NA                                   
## [200] NA                                   
## [201] NA                                   
## [202] NA                                   
## [203] NA                                   
## [204] NA                                   
## [205] NA                                   
## [206] NA                                   
## [207] NA                                   
## [208] NA                                   
## [209] "fine_dining;arab;kebab;curry;indian"
## [210] NA                                   
## [211] NA                                   
## [212] NA                                   
## [213] NA                                   
## [214] NA                                   
## [215] NA                                   
## [216] NA                                   
## [217] NA                                   
## [218] NA                                   
## [219] NA                                   
## [220] NA                                   
## [221] NA                                   
## [222] NA                                   
## [223] NA                                   
## [224] NA                                   
## [225] NA                                   
## [226] NA                                   
## [227] NA                                   
## [228] NA                                   
## [229] NA                                   
## [230] NA                                   
## [231] NA                                   
## [232] NA                                   
## [233] NA                                   
## [234] NA                                   
## [235] NA                                   
## [236] "coffee_shop"                        
## [237] "buger,pizza,cakes,pastry"           
## [238] NA                                   
## [239] NA                                   
## [240] NA                                   
## [241] NA                                   
## [242] NA                                   
## [243] NA                                   
## [244] NA                                   
## [245] NA                                   
## [246] NA                                   
## [247] NA                                   
## [248] NA                                   
## [249] NA                                   
## [250] NA                                   
## [251] NA                                   
## [252] NA                                   
## [253] NA                                   
## [254] NA                                   
## [255] NA                                   
## [256] NA                                   
## [257] NA                                   
## [258] NA                                   
## [259] NA                                   
## [260] NA                                   
## [261] NA                                   
## [262] NA                                   
## [263] NA                                   
## [264] NA                                   
## [265] NA                                   
## [266] NA                                   
## [267] NA                                   
## [268] NA                                   
## [269] NA                                   
## [270] NA                                   
## [271] NA                                   
## [272] NA                                   
## [273] NA                                   
## [274] NA                                   
## [275] NA                                   
## [276] NA                                   
## [277] NA                                   
## [278] NA                                   
## [279] NA                                   
## [280] NA                                   
## [281] NA                                   
## [282] NA                                   
## [283] NA                                   
## [284] NA                                   
## [285] NA                                   
## [286] NA                                   
## [287] NA                                   
## [288] NA                                   
## [289] NA                                   
## [290] NA                                   
## [291] NA                                   
## [292] NA                                   
## [293] NA                                   
## [294] NA                                   
## [295] NA                                   
## [296] NA                                   
## [297] NA                                   
## [298] NA                                   
## [299] NA                                   
## [300] NA                                   
## [301] NA                                   
## [302] NA                                   
## [303] NA                                   
## [304] NA                                   
## [305] NA                                   
## [306] NA                                   
## [307] NA                                   
## [308] NA                                   
## [309] NA                                   
## [310] NA                                   
## [311] NA                                   
## [312] NA                                   
## [313] NA                                   
## [314] NA                                   
## [315] NA                                   
## [316] NA                                   
## [317] NA                                   
## [318] NA                                   
## [319] NA                                   
## [320] NA                                   
## [321] NA                                   
## [322] NA                                   
## [323] NA                                   
## [324] NA                                   
## [325] NA                                   
## [326] NA                                   
## [327] NA                                   
## [328] NA                                   
## [329] NA                                   
## [330] NA                                   
## [331] NA                                   
## [332] NA                                   
## [333] NA                                   
## [334] NA                                   
## [335] NA                                   
## [336] NA                                   
## [337] NA                                   
## [338] NA                                   
## [339] NA                                   
## [340] NA                                   
## [341] NA                                   
## [342] NA                                   
## [343] NA                                   
## [344] NA                                   
## [345] NA                                   
## [346] NA                                   
## [347] NA                                   
## [348] NA                                   
## [349] NA                                   
## [350] NA                                   
## [351] NA                                   
## [352] NA                                   
## [353] NA                                   
## [354] NA                                   
## [355] NA                                   
## [356] NA                                   
## [357] NA                                   
## [358] NA                                   
## [359] NA                                   
## [360] NA                                   
## [361] NA                                   
## [362] NA                                   
## [363] NA                                   
## [364] NA                                   
## [365] NA                                   
## [366] NA                                   
## [367] NA                                   
## [368] NA                                   
## [369] NA                                   
## [370] NA                                   
## [371] NA                                   
## [372] NA                                   
## [373] NA                                   
## [374] NA                                   
## [375] NA                                   
## [376] NA                                   
## [377] NA                                   
## [378] NA                                   
## [379] NA                                   
## [380] NA                                   
## [381] NA                                   
## [382] NA                                   
## [383] NA                                   
## [384] NA                                   
## [385] NA                                   
## [386] NA                                   
## [387] NA                                   
## [388] "Fast_Food"                          
## [389] NA                                   
## [390] NA                                   
## [391] NA                                   
## [392] NA                                   
## [393] NA                                   
## [394] NA                                   
## [395] NA                                   
## [396] NA                                   
## [397] NA                                   
## [398] NA                                   
## [399] NA                                   
## [400] NA                                   
## [401] NA                                   
## [402] NA                                   
## [403] NA                                   
## [404] NA                                   
## [405] NA                                   
## [406] NA                                   
## [407] NA                                   
## [408] NA                                   
## [409] NA                                   
## [410] NA                                   
## [411] NA                                   
## [412] NA                                   
## [413] NA                                   
## [414] NA                                   
## [415] NA                                   
## [416] NA                                   
## [417] NA                                   
## [418] "indian"                             
## [419] NA                                   
## [420] NA                                   
## [421] NA                                   
## [422] "indian"                             
## [423] NA                                   
## [424] NA                                   
## [425] NA                                   
## [426] NA                                   
## [427] NA                                   
## [428] NA                                   
## [429] NA                                   
## [430] NA                                   
## [431] NA                                   
## [432] NA                                   
## [433] "regional"                           
## [434] NA                                   
## [435] NA                                   
## [436] NA                                   
## [437] NA                                   
## [438] NA                                   
## [439] NA                                   
## [440] NA                                   
## [441] NA                                   
## [442] "indian"                             
## [443] NA                                   
## [444] NA                                   
## [445] NA                                   
## [446] NA                                   
## [447] NA                                   
## [448] NA                                   
## [449] NA                                   
## [450] NA                                   
## [451] NA                                   
## [452] NA                                   
## [453] NA                                   
## [454] NA                                   
## [455] NA                                   
## [456] NA                                   
## [457] NA                                   
## [458] NA                                   
## [459] NA                                   
## [460] NA                                   
## [461] NA                                   
## [462] NA                                   
## [463] NA                                   
## [464] NA                                   
## [465] NA                                   
## [466] NA                                   
## [467] NA                                   
## [468] NA                                   
## [469] NA                                   
## [470] NA                                   
## [471] "coffee;cookies"                     
## [472] NA                                   
## [473] "chicken"                            
## [474] NA                                   
## [475] "burger"                             
## [476] NA                                   
## [477] NA                                   
## [478] NA                                   
## [479] NA                                   
## [480] "pizza;burger;sandwich"              
## [481] NA                                   
## [482] NA                                   
## [483] NA                                   
## [484] NA                                   
## [485] NA                                   
## [486] NA                                   
## [487] NA                                   
## [488] NA                                   
## [489] NA                                   
## [490] NA                                   
## [491] NA                                   
## [492] NA                                   
## [493] NA                                   
## [494] NA                                   
## [495] NA                                   
## [496] NA                                   
## [497] NA                                   
## [498] NA                                   
## [499] NA                                   
## [500] NA                                   
## [501] NA                                   
## [502] NA                                   
## [503] NA                                   
## [504] NA                                   
## [505] NA                                   
## [506] NA                                   
## [507] NA                                   
## [508] NA                                   
## [509] NA                                   
## [510] NA                                   
## [511] NA                                   
## [512] NA                                   
## [513] NA                                   
## [514] NA                                   
## [515] NA                                   
## [516] NA                                   
## [517] NA                                   
## [518] NA                                   
## [519] NA                                   
## [520] NA                                   
## [521] NA                                   
## [522] NA                                   
## [523] NA                                   
## [524] NA                                   
## [525] NA                                   
## [526] NA                                   
## [527] NA                                   
## [528] NA                                   
## [529] NA                                   
## [530] NA                                   
## [531] NA                                   
## [532] NA                                   
## [533] NA                                   
## [534] NA                                   
## [535] NA                                   
## [536] NA                                   
## [537] "donut;coffee"                       
## [538] "chinese"                            
## [539] NA                                   
## [540] NA                                   
## [541] NA                                   
## [542] NA                                   
## [543] NA                                   
## [544] NA                                   
## [545] NA                                   
## [546] NA                                   
## [547] NA                                   
## [548] NA                                   
## [549] NA                                   
## [550] NA                                   
## [551] NA                                   
## [552] NA                                   
## [553] NA                                   
## [554] NA                                   
## [555] NA                                   
## [556] NA                                   
## [557] NA                                   
## [558] NA                                   
## [559] NA                                   
## [560] NA                                   
## [561] NA                                   
## [562] NA                                   
## [563] NA                                   
## [564] NA                                   
## [565] NA                                   
## [566] NA                                   
## [567] NA                                   
## [568] NA                                   
## [569] NA                                   
## [570] NA                                   
## [571] NA                                   
## [572] NA                                   
## [573] NA                                   
## [574] NA                                   
## [575] NA                                   
## [576] NA                                   
## [577] NA                                   
## [578] NA                                   
## [579] NA                                   
## [580] NA                                   
## [581] NA                                   
## [582] NA                                   
## [583] NA                                   
## [584] NA                                   
## [585] NA                                   
## [586] NA                                   
## [587] NA                                   
## [588] NA                                   
## [589] NA                                   
## [590] NA                                   
## [591] NA                                   
## [592] NA                                   
## [593] NA                                   
## [594] NA                                   
## [595] NA                                   
## [596] NA                                   
## [597] NA                                   
## [598] NA                                   
## [599] NA                                   
## [600] NA                                   
## [601] NA                                   
## [602] NA                                   
## [603] NA                                   
## [604] NA                                   
## [605] NA                                   
## [606] NA                                   
## [607] "kebab"                              
## [608] "pizza;american"                     
## [609] NA                                   
## [610] "regional"                           
## [611] NA                                   
## [612] NA                                   
## [613] NA                                   
## [614] NA                                   
## [615] NA                                   
## [616] NA                                   
## [617] NA                                   
## [618] NA                                   
## [619] NA                                   
## [620] NA                                   
## [621] NA                                   
## [622] NA                                   
## [623] NA                                   
## [624] NA                                   
## [625] NA                                   
## [626] NA                                   
## [627] NA                                   
## [628] NA                                   
## [629] NA                                   
## [630] NA                                   
## [631] NA                                   
## [632] NA                                   
## [633] NA                                   
## [634] NA                                   
## [635] NA                                   
## [636] NA                                   
## [637] NA                                   
## [638] NA                                   
## [639] NA                                   
## [640] NA                                   
## [641] NA                                   
## [642] NA                                   
## [643] NA                                   
## [644] NA                                   
## [645] NA                                   
## [646] NA                                   
## [647] NA                                   
## [648] NA                                   
## [649] NA                                   
## [650] NA                                   
## [651] NA                                   
## [652] NA                                   
## [653] "indian;kebab;chicken"               
## [654] NA                                   
## [655] NA                                   
## [656] NA                                   
## [657] NA                                   
## [658] NA                                   
## [659] NA                                   
## [660] NA                                   
## [661] NA                                   
## [662] NA                                   
## [663] NA                                   
## [664] NA                                   
## [665] NA                                   
## [666] NA                                   
## [667] NA                                   
## [668] NA                                   
## [669] NA                                   
## [670] NA                                   
## [671] NA                                   
## [672] NA                                   
## [673] NA                                   
## [674] NA                                   
## [675] NA                                   
## [676] NA                                   
## [677] NA                                   
## [678] NA                                   
## [679] NA                                   
## [680] NA                                   
## [681] NA                                   
## [682] NA                                   
## [683] NA                                   
## [684] NA                                   
## [685] NA                                   
## [686] NA                                   
## [687] NA                                   
## [688] NA                                   
## [689] NA                                   
## [690] NA                                   
## [691] NA                                   
## [692] NA                                   
## [693] NA                                   
## [694] NA                                   
## [695] NA                                   
## [696] NA                                   
## [697] NA                                   
## [698] NA                                   
## [699] NA                                   
## [700] NA                                   
## [701] NA                                   
## [702] NA                                   
## [703] NA                                   
## [704] NA                                   
## [705] NA                                   
## [706] NA                                   
## [707] NA                                   
## [708] NA                                   
## [709] NA                                   
## [710] NA                                   
## [711] NA                                   
## [712] NA                                   
## [713] NA                                   
## [714] NA                                   
## [715] NA                                   
## [716] NA                                   
## [717] NA                                   
## [718] NA                                   
## [719] NA                                   
## [720] NA                                   
## [721] NA                                   
## [722] NA                                   
## [723] "chinese;thai"                       
## [724] NA                                   
## [725] NA                                   
## [726] NA                                   
## [727] NA                                   
## [728] NA                                   
## [729] NA                                   
## [730] NA                                   
## [731] NA                                   
## [732] NA                                   
## [733] NA                                   
## [734] NA                                   
## [735] NA                                   
## [736] NA                                   
## [737] NA                                   
## [738] NA                                   
## [739] NA                                   
## [740] NA                                   
## [741] NA                                   
## [742] NA                                   
## [743] NA                                   
## [744] NA                                   
## [745] NA                                   
## [746] NA                                   
## [747] NA                                   
## [748] NA                                   
## [749] NA                                   
## [750] NA                                   
## [751] NA                                   
## [752] NA                                   
## [753] NA                                   
## [754] NA                                   
## [755] NA                                   
## [756] NA                                   
## [757] NA                                   
## [758] NA                                   
## [759] NA                                   
## [760] NA                                   
## [761] NA                                   
## [762] NA                                   
## [763] NA                                   
## [764] NA                                   
## [765] NA                                   
## [766] NA                                   
## [767] NA                                   
## [768] NA                                   
## [769] NA                                   
## [770] NA                                   
## [771] NA                                   
## [772] NA                                   
## [773] NA                                   
## [774] NA                                   
## [775] NA                                   
## [776] NA                                   
## [777] NA                                   
## [778] NA                                   
## [779] NA                                   
## [780] NA                                   
## [781] NA                                   
## [782] NA                                   
## [783] NA                                   
## [784] NA                                   
## [785] NA                                   
## [786] NA                                   
## [787] NA                                   
## [788] NA                                   
## [789] NA                                   
## [790] NA                                   
## [791] "indian"                             
## [792] NA                                   
## [793] NA
```

```
## Warning: Expected 3 pieces. Additional pieces discarded in 1 rows [33].
```

```
## Warning: Expected 3 pieces. Missing pieces filled with `NA` in 48 rows [1, 2, 3,
## 4, 5, 6, 7, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, ...].
```

```
## Warning: Expected 3 pieces. Additional pieces discarded in 1 rows [35].
```

```
## Warning: Expected 3 pieces. Missing pieces filled with `NA` in 51 rows [1, 2, 3,
## 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, ...].
```

```
##  [1] "coffee_shop"   "south_indian"  "regional"      "sandwich"     
##  [5] "indian"        "pizza"         "coffee_shop"   "regional"     
##  [9] "coffee_shop"   "indian"        "american"      "chinese"      
## [13] "indian"        "indian"        "indian"        "chinese"      
## [17] "chicken"       "indian"        "ice_cream"     "ice_cream"    
## [21] "coffee_shop"   "indian"        "indian"        "indian"       
## [25] "international" "tea"           "indian"        "coffee_shop"  
## [29] "pizza"         "regional"      "indian"        "regional"     
## [33] "fine_dining"   "coffee_shop"   "buger"         "Fast_Food"    
## [37] "indian"        "indian"        "regional"      "indian"       
## [41] "coffee"        "chicken"       "burger"        "pizza"        
## [45] "donut"         "chinese"       "kebab"         "pizza"        
## [49] "regional"      "indian"        "chinese"       "indian"
```
<img src="index_files/figure-html/unnamed-chunk-4-1.png" width="480" />

## My Course Reflection

Learning R programming language was a lot of fun and I have grown a lot in these 2 weeks of the workshop. My earlier experience with learning a programming language has not been pleasant and never thought I will be able to learn another language again. It had become intimidating for me to do coding again. But this workshop went so smoothly that I didn't feel stuck anywhere. I understood most of the things Arvind taught us and how one should approach a dataset and code using your intuition instead of memorizing the syntax. I have progressed a lot of and felt that the course was at the right pace. In my HCD journey, I look forward to continuing using R in my research methods, data collection and creating good user friendly products like apps and websites. 
I learnt that data collection and analysis of the research is one of the most important things to do to improve human experience. 
