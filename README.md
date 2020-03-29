# latlong-distance
Calculates distance between two coordinates.
This program was written by Alexander Dua to calculate the distance between two pairs of coordinates. It does so by executing the haversine formula. More information is on the repository's GitHub website

### https://alexdua.github.io/latlong-distance/

Below is the JavaScript code used to execute the haversine formula and calculate the distance between two pairs of coordinates. Note: this is only the JavaScript code. The HTML code can be found by downloading and opening the file called index.html, however, the JavaScript is the important part as the math is being done within it.

```
// Creates a function called Deg2Rad that will take coordinates in decimal degrees and convert them to radians. 
deg is the input. Takes the input deg, multiplies it by pi, then divides it by 180.

function Deg2Rad( deg ) { 
  return deg * Math.PI / 180;
 }
 
// Creates a function called getDistance that will measure the distance between the two pairs of coordinates.

function getDistance() {
  var la1 = document.getElementById("lati1").value;
  var la2 = document.getElementById("lati2").value;
  var lo1 = document.getElementById("long1").value;
  var lo2 = document.getElementById("long2").value;
  lat1 = Deg2Rad(la1);
  lat2 = Deg2Rad(la2);
  lon1 = Deg2Rad(lo1);
  lon2 = Deg2Rad(lo2);
  latDiff = lat2-lat1;
  lonDiff = lon2-lon1;
  var R = 6371000;
  var φ1 = lat1;
  var φ2 = lat2;
  var Δφ = latDiff;
  var Δλ = lonDiff;
  
  // Executes the haversine formula. More information on it is available at the site linked above.
  
  var a = Math.sin(Δφ/2) * Math.sin(Δφ/2) + Math.cos(φ1) * Math.cos(φ2) * Math.sin(Δλ/2) * Math.sin(Δλ/2);
  
  var c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1-a));
  
  var d = R * c;
  
  // Creates text on the website that reads Distance: xx.xxx meters
  
  document.getElementById("demo").innerHTML = 'Distance: ' + d + " meters";
  
 }
 ```
