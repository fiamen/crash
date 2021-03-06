# Road crash locations - Queensland 
Mario Fiamenghi  

###1.Introduction  
This dataset shows the position of vehicular crash incidents in Queensland. This includes fatalities, injuries and vehicular damage. The point of truth for this dataset is the Queensland government open data website at,https://data.qld.gov.au/dataset/crash-data-from-queensland-roads.

###2.Loading the  Dataset
- Create the variable time to report the system time to be used in the following line


```r
time<-Sys.time()
```
This code was last interpreted on *2014-11-03 15:02:38*  


-Download data from the following adress **[click to open QLD Data](https://data.qld.gov.au/dataset/crash-data-from-queensland-roads)**

- Using my own git hub repository, open directory from Git Hub repository created for this project:**[click to open github](https://github.com/fiamen/crash)**



- Reads file as a table to memory *crash location*

```r
loc=read.csv("../../data/locations (1).csv")
loc$latlon=paste0(loc$Crash_Latitude_GDA94,":",loc$Crash_Longitude_GDA94)
```
- Subset table

```r
loc1=loc[,c(2,3,19,30,31,32,33,39,44)]
```



###3.Analysis

####Did the number of fatality decrease since 2007?

#####1.Make a graph  of the total number of fatalities yearly




- The graphic can be generated by the code:

```r
suppressPackageStartupMessages(library(googleVis))
```

```
## Warning: package 'googleVis' was built under R version 3.0.3
```

```r
options(gvis.plot.tag="chart")
```


```r
loca=aggregate(loc1$Count_Casualty_Fatality,by= list(year=loc1$Crash_Year,region=loc1$Loc_Queensland_Transport_Region),sum,na=TRUE)
```

```r
M1 <- gvisMotionChart(loca, idvar="region", timevar="year")
plot(M1)
```

<!-- MotionChart generated in R 3.0.2 by googleVis 0.5.6 package -->
<!-- Mon Nov 03 15:02:39 2014 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMotionChartID1fb427153cd9 () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
 "Central",
2001,
50 
],
[
 "Central",
2002,
49 
],
[
 "Central",
2003,
41 
],
[
 "Central",
2004,
42 
],
[
 "Central",
2005,
50 
],
[
 "Central",
2006,
52 
],
[
 "Central",
2007,
62 
],
[
 "Central",
2008,
35 
],
[
 "Central",
2009,
58 
],
[
 "Central",
2010,
43 
],
[
 "Central",
2011,
57 
],
[
 "Central",
2012,
51 
],
[
 "Central",
2013,
57 
],
[
 "Central",
2014,
6 
],
[
 "Northern",
2001,
48 
],
[
 "Northern",
2002,
47 
],
[
 "Northern",
2003,
38 
],
[
 "Northern",
2004,
30 
],
[
 "Northern",
2005,
55 
],
[
 "Northern",
2006,
58 
],
[
 "Northern",
2007,
42 
],
[
 "Northern",
2008,
63 
],
[
 "Northern",
2009,
60 
],
[
 "Northern",
2010,
41 
],
[
 "Northern",
2011,
30 
],
[
 "Northern",
2012,
44 
],
[
 "Northern",
2013,
34 
],
[
 "Northern",
2014,
12 
],
[
 "SEQ North",
2001,
68 
],
[
 "SEQ North",
2002,
69 
],
[
 "SEQ North",
2003,
76 
],
[
 "SEQ North",
2004,
57 
],
[
 "SEQ North",
2005,
57 
],
[
 "SEQ North",
2006,
70 
],
[
 "SEQ North",
2007,
67 
],
[
 "SEQ North",
2008,
64 
],
[
 "SEQ North",
2009,
67 
],
[
 "SEQ North",
2010,
43 
],
[
 "SEQ North",
2011,
43 
],
[
 "SEQ North",
2012,
58 
],
[
 "SEQ North",
2013,
56 
],
[
 "SEQ North",
2014,
5 
],
[
 "SEQ South",
2001,
94 
],
[
 "SEQ South",
2002,
94 
],
[
 "SEQ South",
2003,
91 
],
[
 "SEQ South",
2004,
109 
],
[
 "SEQ South",
2005,
95 
],
[
 "SEQ South",
2006,
94 
],
[
 "SEQ South",
2007,
124 
],
[
 "SEQ South",
2008,
91 
],
[
 "SEQ South",
2009,
78 
],
[
 "SEQ South",
2010,
70 
],
[
 "SEQ South",
2011,
82 
],
[
 "SEQ South",
2012,
72 
],
[
 "SEQ South",
2013,
67 
],
[
 "SEQ South",
2014,
13 
],
[
 "Southern",
2001,
69 
],
[
 "Southern",
2002,
68 
],
[
 "Southern",
2003,
69 
],
[
 "Southern",
2004,
78 
],
[
 "Southern",
2005,
78 
],
[
 "Southern",
2006,
66 
],
[
 "Southern",
2007,
70 
],
[
 "Southern",
2008,
80 
],
[
 "Southern",
2009,
73 
],
[
 "Southern",
2010,
57 
],
[
 "Southern",
2011,
62 
],
[
 "Southern",
2012,
60 
],
[
 "Southern",
2013,
62 
],
[
 "Southern",
2014,
21 
],
[
 "Unknown",
2001,
1 
],
[
 "Unknown",
2002,
1 
],
[
 "Unknown",
2003,
1 
],
[
 "Unknown",
2004,
1 
],
[
 "Unknown",
2005,
1 
],
[
 "Unknown",
2006,
1 
],
[
 "Unknown",
2007,
1 
],
[
 "Unknown",
2008,
1 
],
[
 "Unknown",
2009,
1 
],
[
 "Unknown",
2010,
1 
],
[
 "Unknown",
2011,
1 
],
[
 "Unknown",
2012,
1 
],
[
 "Unknown",
2013,
1 
] 
];
data.addColumn('string','region');
data.addColumn('number','year');
data.addColumn('number','x');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartMotionChartID1fb427153cd9() {
var data = gvisDataMotionChartID1fb427153cd9();
var options = {};
options["width"] =    600;
options["height"] =    500;
options["state"] = "";

    var chart = new google.visualization.MotionChart(
    document.getElementById('MotionChartID1fb427153cd9')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "motionchart";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartMotionChartID1fb427153cd9);
})();
function displayChartMotionChartID1fb427153cd9() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMotionChartID1fb427153cd9"></script>
 
<!-- divChart -->
  
<div id="MotionChartID1fb427153cd9" 
  style="width: 600; height: 500;">
</div>

```r
loca=aggregate(loc1$Count_Casualty_Fatality,by= list(year=loc1$Crash_Year,speed=loc1$Crash_Speed_Limit),sum,na=TRUE)
```

```r
M2 <- gvisMotionChart(loca, idvar="speed", timevar="year")
plot(M2)
```

<!-- MotionChart generated in R 3.0.2 by googleVis 0.5.6 package -->
<!-- Mon Nov 03 15:02:39 2014 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataMotionChartID1fb4193015ad () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
 "0 - 50 km/h",
2001,
17 
],
[
 "0 - 50 km/h",
2002,
10 
],
[
 "0 - 50 km/h",
2003,
23 
],
[
 "0 - 50 km/h",
2004,
29 
],
[
 "0 - 50 km/h",
2005,
24 
],
[
 "0 - 50 km/h",
2006,
36 
],
[
 "0 - 50 km/h",
2007,
37 
],
[
 "0 - 50 km/h",
2008,
24 
],
[
 "0 - 50 km/h",
2009,
38 
],
[
 "0 - 50 km/h",
2010,
23 
],
[
 "0 - 50 km/h",
2011,
22 
],
[
 "0 - 50 km/h",
2012,
21 
],
[
 "0 - 50 km/h",
2013,
23 
],
[
 "0 - 50 km/h",
2014,
7 
],
[
 "100 - 110 km/h",
2001,
167 
],
[
 "100 - 110 km/h",
2002,
165 
],
[
 "100 - 110 km/h",
2003,
137 
],
[
 "100 - 110 km/h",
2004,
140 
],
[
 "100 - 110 km/h",
2005,
178 
],
[
 "100 - 110 km/h",
2006,
144 
],
[
 "100 - 110 km/h",
2007,
163 
],
[
 "100 - 110 km/h",
2008,
149 
],
[
 "100 - 110 km/h",
2009,
142 
],
[
 "100 - 110 km/h",
2010,
122 
],
[
 "100 - 110 km/h",
2011,
143 
],
[
 "100 - 110 km/h",
2012,
123 
],
[
 "100 - 110 km/h",
2013,
137 
],
[
 "100 - 110 km/h",
2014,
27 
],
[
 "60 km/h",
2001,
91 
],
[
 "60 km/h",
2002,
84 
],
[
 "60 km/h",
2003,
79 
],
[
 "60 km/h",
2004,
93 
],
[
 "60 km/h",
2005,
75 
],
[
 "60 km/h",
2006,
99 
],
[
 "60 km/h",
2007,
83 
],
[
 "60 km/h",
2008,
95 
],
[
 "60 km/h",
2009,
75 
],
[
 "60 km/h",
2010,
55 
],
[
 "60 km/h",
2011,
60 
],
[
 "60 km/h",
2012,
78 
],
[
 "60 km/h",
2013,
53 
],
[
 "60 km/h",
2014,
14 
],
[
 "70 km/h",
2001,
15 
],
[
 "70 km/h",
2002,
19 
],
[
 "70 km/h",
2003,
13 
],
[
 "70 km/h",
2004,
14 
],
[
 "70 km/h",
2005,
18 
],
[
 "70 km/h",
2006,
16 
],
[
 "70 km/h",
2007,
19 
],
[
 "70 km/h",
2008,
14 
],
[
 "70 km/h",
2009,
15 
],
[
 "70 km/h",
2010,
13 
],
[
 "70 km/h",
2011,
6 
],
[
 "70 km/h",
2012,
13 
],
[
 "70 km/h",
2013,
12 
],
[
 "80 - 90 km/h",
2001,
39 
],
[
 "80 - 90 km/h",
2002,
49 
],
[
 "80 - 90 km/h",
2003,
63 
],
[
 "80 - 90 km/h",
2004,
40 
],
[
 "80 - 90 km/h",
2005,
40 
],
[
 "80 - 90 km/h",
2006,
45 
],
[
 "80 - 90 km/h",
2007,
63 
],
[
 "80 - 90 km/h",
2008,
51 
],
[
 "80 - 90 km/h",
2009,
66 
],
[
 "80 - 90 km/h",
2010,
41 
],
[
 "80 - 90 km/h",
2011,
43 
],
[
 "80 - 90 km/h",
2012,
50 
],
[
 "80 - 90 km/h",
2013,
51 
],
[
 "80 - 90 km/h",
2014,
8 
] 
];
data.addColumn('string','speed');
data.addColumn('number','year');
data.addColumn('number','x');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartMotionChartID1fb4193015ad() {
var data = gvisDataMotionChartID1fb4193015ad();
var options = {};
options["width"] =    600;
options["height"] =    500;
options["state"] = "";

    var chart = new google.visualization.MotionChart(
    document.getElementById('MotionChartID1fb4193015ad')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "motionchart";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartMotionChartID1fb4193015ad);
})();
function displayChartMotionChartID1fb4193015ad() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartMotionChartID1fb4193015ad"></script>
 
<!-- divChart -->
  
<div id="MotionChartID1fb4193015ad" 
  style="width: 600; height: 500;">
</div>

-Subset table for fatalities and vreates variable with latitude and Longitude

```r
loc2=loc[,c(3,4,39,9,10)]
```
-Aggregate fatalities by coordinates

```r
loc2$Crash_Longitude_GDA94_1=round(loc2$Crash_Longitude_GDA94,2)
loc2$Crash_Latitude_GDA94_1=round(loc2$Crash_Latitude_GDA94,2)
loc2$latlong<-paste0(loc2$Crash_Latitude_GDA94_1, loc2$Crash_Longitude_GDA94_1, sep=":")
loc3=aggregate(loc2$Count_Casualty_Fatality,by=list(coordinate=loc2$latlong),sum,na=TRUE)
```


-Create a Geo graphic with fatality crashs

```r
G4 <- gvisGeoMap(loc[1:10,], locationvar="latlon", numvar="Count_Casualty_Total",
                 
                 options=list(height=350, region="AU",dataMode="markers",regionClick=TRUE))

plot(G4)
```

<!-- GeoMap generated in R 3.0.2 by googleVis 0.5.6 package -->
<!-- Mon Nov 03 15:02:40 2014 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisDataGeoMapID1fb440345b33 () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
 -16.63736445,
139.2438277,
4 
],
[
 -16.92495839,
145.7645919,
0 
],
[
 -27.81885814,
153.2849816,
2 
],
[
 -26.79602439,
153.109064,
1 
],
[
 -27.47618292,
153.0357624,
1 
],
[
 -25.28620516,
152.8725434,
0 
],
[
 -27.52203568,
153.0257546,
4 
],
[
 -19.34190784,
146.7136426,
3 
],
[
 -27.55597216,
153.0080452,
1 
],
[
 -28.03467236,
153.42723,
1 
] 
];
data.addColumn('number','Latitude');
data.addColumn('number','Longitude');
data.addColumn('number','Count_Casualty_Total');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChartGeoMapID1fb440345b33() {
var data = gvisDataGeoMapID1fb440345b33();
var options = {};
options["dataMode"] = "markers";
options["width"] =    556;
options["height"] =    350;
options["region"] = "AU";
options["regionClick"] = true;

    var chart = new google.visualization.GeoMap(
    document.getElementById('GeoMapID1fb440345b33')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "geomap";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChartGeoMapID1fb440345b33);
})();
function displayChartGeoMapID1fb440345b33() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChartGeoMapID1fb440345b33"></script>
 
<!-- divChart -->
  
<div id="GeoMapID1fb440345b33" 
  style="width: 556; height: 350;">
</div>

```r
G4 <- gvisMap(loc[1:100,], locationvar="latlon",options=list(mapType='normal')               
,chartid="2036")
 plot(G4)
```

<!-- Map generated in R 3.0.2 by googleVis 0.5.6 package -->
<!-- Mon Nov 03 15:02:40 2014 -->


<!-- jsHeader -->
<script type="text/javascript">
 
// jsData 
function gvisData2036 () {
var data = new google.visualization.DataTable();
var datajson =
[
 [
 -16.63736445,
139.2438277,
"Fatal" 
],
[
 -16.92495839,
145.7645919,
"Property damage only" 
],
[
 -27.81885814,
153.2849816,
"Hospitalisation" 
],
[
 -26.79602439,
153.109064,
"Medical treatment" 
],
[
 -27.47618292,
153.0357624,
"Hospitalisation" 
],
[
 -25.28620516,
152.8725434,
"Property damage only" 
],
[
 -27.52203568,
153.0257546,
"Fatal" 
],
[
 -19.34190784,
146.7136426,
"Fatal" 
],
[
 -27.55597216,
153.0080452,
"Hospitalisation" 
],
[
 -28.03467236,
153.42723,
"Hospitalisation" 
],
[
 -25.28865002,
152.8967132,
"Hospitalisation" 
],
[
 -25.61394107,
151.379398,
"Property damage only" 
],
[
 -27.53098407,
152.9832075,
"Medical treatment" 
],
[
 -27.6120346,
152.8082602,
"Medical treatment" 
],
[
 -27.37253287,
153.0622155,
"Medical treatment" 
],
[
 -19.28935435,
146.7495139,
"Medical treatment" 
],
[
 -28.00862339,
153.429376,
"Hospitalisation" 
],
[
 -26.72120262,
153.0446241,
"Fatal" 
],
[
 -27.47606118,
152.9885913,
"Property damage only" 
],
[
 -27.3121871,
153.0211159,
"Minor injury" 
],
[
 -27.03088477,
152.9644158,
"Fatal" 
],
[
 -27.47250714,
151.9388762,
"Property damage only" 
],
[
 -27.60558301,
152.916235,
"Property damage only" 
],
[
 -27.90711913,
153.318607,
"Medical treatment" 
],
[
 -26.53272468,
153.0927234,
"Medical treatment" 
],
[
 -27.28309028,
152.9832382,
"Hospitalisation" 
],
[
 -27.36653095,
153.0619302,
"Hospitalisation" 
],
[
 -27.44540687,
153.0269778,
"Minor injury" 
],
[
 -26.85004417,
152.9927722,
"Fatal" 
],
[
 -27.56159832,
151.9277049,
"Property damage only" 
],
[
 -27.79978342,
151.7719237,
"Hospitalisation" 
],
[
 -27.57660065,
153.1070217,
"Medical treatment" 
],
[
 -27.59409775,
153.1127516,
"Medical treatment" 
],
[
 -27.51242468,
153.0403601,
"Minor injury" 
],
[
 -28.22762315,
152.0184831,
"Hospitalisation" 
],
[
 -16.91957276,
145.7753785,
"Hospitalisation" 
],
[
 -27.5572902,
153.0406636,
"Medical treatment" 
],
[
 -27.41149756,
152.9626128,
"Hospitalisation" 
],
[
 -20.20123951,
148.3719199,
"Hospitalisation" 
],
[
 -20.78263312,
148.6130919,
"Property damage only" 
],
[
 -20.23807941,
145.8687123,
"Fatal" 
],
[
 -24.95158902,
152.3779466,
"Hospitalisation" 
],
[
 -27.4035079,
153.0280947,
"Hospitalisation" 
],
[
 -27.63846264,
153.118702,
"Property damage only" 
],
[
 -27.66373859,
153.1400202,
"Minor injury" 
],
[
 -27.67834632,
153.0823518,
"Fatal" 
],
[
 -24.070764,
145.337907,
"Fatal" 
],
[
 -27.64750132,
153.1491267,
"Fatal" 
],
[
 -23.38244091,
150.5067601,
"Property damage only" 
],
[
 -27.17868033,
152.3665834,
"Fatal" 
],
[
 -27.95714769,
153.4007385,
"Minor injury" 
],
[
 -23.44466564,
144.2472927,
"Fatal" 
],
[
 -27.5241821,
153.2568239,
"Medical treatment" 
],
[
 -25.5340442,
152.7043231,
"Medical treatment" 
],
[
 -27.71151584,
151.8593998,
"Hospitalisation" 
],
[
 -27.45786511,
153.0355283,
"Hospitalisation" 
],
[
 -27.58989342,
151.9393334,
"Property damage only" 
],
[
 -21.59223595,
149.0704636,
"Property damage only" 
],
[
 -27.55336568,
151.9726171,
"Property damage only" 
],
[
 -27.55976556,
153.0812527,
"Fatal" 
],
[
 -27.45168228,
153.183832,
"Medical treatment" 
],
[
 -27.07241391,
153.0292875,
"Minor injury" 
],
[
 -17.02427451,
145.7348819,
"Fatal" 
],
[
 -27.52028608,
153.0516966,
"Property damage only" 
],
[
 -27.42376548,
152.9964134,
"Medical treatment" 
],
[
 -27.99326586,
153.3221571,
"Fatal" 
],
[
 -27.39975727,
153.048392,
"Property damage only" 
],
[
 -23.44377883,
144.2471312,
"Fatal" 
],
[
 -27.54123413,
152.3616012,
"Fatal" 
],
[
 -24.87371037,
152.3536691,
"Fatal" 
],
[
 -23.23460155,
150.8083648,
"Hospitalisation" 
],
[
 -17.19752693,
145.8980894,
"Medical treatment" 
],
[
 -27.72159023,
153.2126159,
"Property damage only" 
],
[
 -27.3424567,
153.0113262,
"Medical treatment" 
],
[
 -27.44629753,
153.0406636,
"Property damage only" 
],
[
 -27.62706124,
152.7599097,
"Property damage only" 
],
[
 -27.40770476,
153.0751573,
"Medical treatment" 
],
[
 -28.05833229,
152.4207449,
"Fatal" 
],
[
 -27.51878936,
153.0159146,
"Minor injury" 
],
[
 -27.95192911,
153.3847123,
"Minor injury" 
],
[
 -26.63374416,
152.9607198,
"Fatal" 
],
[
 -24.66794842,
151.6897575,
"Fatal" 
],
[
 -27.95466638,
153.4084246,
"Minor injury" 
],
[
 -26.38642417,
152.8526729,
"Fatal" 
],
[
 -27.43269098,
153.1401328,
"Fatal" 
],
[
 -27.76882401,
153.1045367,
"Fatal" 
],
[
 -27.59339075,
151.9195828,
"Fatal" 
],
[
 -23.0321216,
150.263071,
"Fatal" 
],
[
 -19.29262282,
146.7942017,
"Fatal" 
],
[
 -19.96627191,
148.0362102,
"Fatal" 
],
[
 -27.48752132,
153.0009534,
"Property damage only" 
],
[
 -26.68251252,
153.0658442,
"Medical treatment" 
],
[
 -25.4136732,
152.7600784,
"Fatal" 
],
[
 -26.01741479,
152.7756714,
"Fatal" 
],
[
 -27.41136298,
152.9773389,
"Medical treatment" 
],
[
 -27.48075407,
153.1281505,
"Property damage only" 
],
[
 -26.32306653,
152.7211251,
"Fatal" 
],
[
 -18.68857225,
144.7111649,
"Fatal" 
],
[
 -27.57201213,
152.6424154,
"Medical treatment" 
],
[
 -27.95678043,
153.069846,
"Fatal" 
] 
];
data.addColumn('number','Latitude');
data.addColumn('number','Longitude');
data.addColumn('string','Crash_Severity');
data.addRows(datajson);
return(data);
}
 
// jsDrawChart
function drawChart2036() {
var data = gvisData2036();
var options = {};
options["showTip"] = true;
options["mapType"] = "normal";

    var chart = new google.visualization.Map(
    document.getElementById('2036')
    );
    chart.draw(data,options);
    

}
  
 
// jsDisplayChart
(function() {
var pkgs = window.__gvisPackages = window.__gvisPackages || [];
var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
var chartid = "map";
  
// Manually see if chartid is in pkgs (not all browsers support Array.indexOf)
var i, newPackage = true;
for (i = 0; newPackage && i < pkgs.length; i++) {
if (pkgs[i] === chartid)
newPackage = false;
}
if (newPackage)
  pkgs.push(chartid);
  
// Add the drawChart function to the global list of callbacks
callbacks.push(drawChart2036);
})();
function displayChart2036() {
  var pkgs = window.__gvisPackages = window.__gvisPackages || [];
  var callbacks = window.__gvisCallbacks = window.__gvisCallbacks || [];
  window.clearTimeout(window.__gvisLoad);
  // The timeout is set to 100 because otherwise the container div we are
  // targeting might not be part of the document yet
  window.__gvisLoad = setTimeout(function() {
  var pkgCount = pkgs.length;
  google.load("visualization", "1", { packages:pkgs, callback: function() {
  if (pkgCount != pkgs.length) {
  // Race condition where another setTimeout call snuck in after us; if
  // that call added a package, we must not shift its callback
  return;
}
while (callbacks.length > 0)
callbacks.shift()();
} });
}, 100);
}
 
// jsFooter
</script>
 
<!-- jsChart -->  
<script type="text/javascript" src="https://www.google.com/jsapi?callback=displayChart2036"></script>
 
<!-- divChart -->
  
<div id="2036" 
  style="width: 500; height: automatic;">
</div>


