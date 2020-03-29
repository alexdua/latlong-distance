# latlong-distance
This program was written by Alexander Dua to calculate the distance between two pairs of coordinates. It does so by executing the haversine formula. More information is on the repository's GitHub website

### https://alexdua.github.io/latlong-distance/

function Deg2Rad( deg ) {  <-- Creates a function called Deg2Rad that will take coordinates in decimaal degrees and convert them to radians. deg is the input.
      return deg * Math.PI / 180;  <-- Takes the input deg, multiplies it by pi, then divides it by 180.
   }

   function getDistance()  <-- Creates a function called getDistance that will measure the distance between the two pairs of coordinates.
   {
       var la1 = document.getElementById("lati1").value;  <-- Assigns the value of the first latitude coordinate to a variable called la1.
       var la2 = document.getElementById("lati2").value;  <-- Assigns the value of the second latitude coordinate to a variable called la2.
       var lo1 = document.getElementById("long1").value;  <-- Assigns the value of the first longitude coordinate to a variable called lo1.
       var lo2 = document.getElementById("long2").value;  <-- Assigns the value of the second longitude coordinate to a variable called lo2.
       lat1 = Deg2Rad(la1);  <-- Performs the degrees to radians operation as defined by the function Deg2Rad.
       lat2 = Deg2Rad(la2);  <-- Performs the degrees to radians operation as defined by the function Deg2Rad.
       lon1 = Deg2Rad(lo1);  <-- Performs the degrees to radians operation as defined by the function Deg2Rad.
       lon2 = Deg2Rad(lo2);  <-- Performs the degrees to radians operation as defined by the function Deg2Rad.
       latDiff = lat2-lat1;  <-- Assigns the value of the second latitude subtracted by the first latitude to the variable called latDiff.
       lonDiff = lon2-lon1;  <-- Assigns the value of the second longitude subtracted by the first longitude to the variable called lonDiff.
       var R = 6371000; // meters  <-- Assigns the value of 6371000, approximately the radius of the Earth in meters, to the variable R;
       var φ1 = lat1;  <-- Assigns the value of the first latitude coordinate to the the variable φ1.
       var φ2 = lat2;  <-- Assigns the value of the second latitude coordinate to the the variable φ2.
       var Δφ = latDiff;  <-- Assigns the value of the latDiff variable (defined above) to the the variable Δφ.
       var Δλ = lonDiff;  <-- Assigns the value of the lonDiff variable (defined above) to the variable Δλ. 

       var a = Math.sin(Δφ/2) * Math.sin(Δφ/2) +  <-- Assigns the resulting value from the equation to the variable a.
               Math.cos(φ1) * Math.cos(φ2) *
               Math.sin(Δλ/2) * Math.sin(Δλ/2);
       var c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1-a));  <-- Assigns the resulting value from the equation to variable b.

       var d = R * c;  <-- Perform the operation multiplying R and c, and assign the product to variable d.

       document.getElementById("demo").innerHTML = 'Distance: ' + d + " meters";  <-- Create a string of text on the webpage that reads Distance: xx.xxx meters.
   }
