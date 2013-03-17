Leaflet Control Inbaz Legende
=============================

# What is it ?
A simple info box that shows the feature name and description dynamicly (requested via jsonp). It was created for the website www.inbaz.org

# How to use it ?
```javascript
var cloudmadeAttribution = 'Map data &copy; 2011 OpenStreetMap contributors, Imagery &copy; 2011 CloudMade',
    cloudmade = new L.TileLayer('http://{s}.tile.cloudmade.com/BC9A493B41014CAABB98F0471D759707/997/256/{z}/{x}/{y}.png', {attribution: cloudmadeAttribution});

var map = new L.Map('map').addLayer(cloudmade).setView(new L.LatLng(48.5, 2.5), 15);

var info = new L.Control.InbazLegende();

map.addControl(info);
```

# What are the options ?
You can specify an options object as a second argument of L.Control.OSMGeocoder.
```javascript
	options: {
		collapsed: true,
		position: 'bottomleft',
		tooltip: 'Show info',
		callback: function (results) {
      text = "";
      for (i=0; i<results.length;i++) {
        text += '<div><img src="images/conTag_'+results[i].id+'.png"/>'+
                '<b>'+results[i].name+'</b><br>'+results[i].desc+'</div>';
      }
      this._element.innerHTML = text;
		}
};
```
