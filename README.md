
# Leaflet.GridLayer.GoogleMutant

A [LeafletJS](http://www.leafletjs.com) plugin to use Google maps basemaps.

Altough this is possible already thanks to [Shramov's implementation](https://github.com/shramov/leaflet-plugins), or using an [OpenLayers implementation](http://openlayers.org/en/v3.0.0/examples/google-map.html), the current state of the art suffers from a [big drawback](https://github.com/shramov/leaflet-plugins/issues/111): the basemap and whatever overlays are on top are *off sync*.

GoogleMutant uses both [DOM mutation observers](https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver) and `L.GridLayer` from Leaflet 1.0.0 to provide a seamless experience. The basemap tiles are still requested *through* Google's javascript code, but they switch places to use Leaflet animations.

Hat tip to [Avin Mathew](https://avinmathew.com/leaflet-and-google-maps/) for inspiration.


## Demo

[http://ivansanchez.gitlab.io/Leaflet.GridLayer.GoogleMutant/demo.html](http://ivansanchez.gitlab.io/Leaflet.GridLayer.GoogleMutant/demo.html)


## Usage

Include the GMaps JS API in your HTML, plus Leaflet:

```
<script src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY" async defer></script>
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.0.0-rc.3/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.0.0-rc.3/dist/leaflet.js"></script>
```

Then, you can create an instance of `L.GridLayer.GoogleMutant` on your JS code:

```
var roads = L.gridLayer.googleMutant({
	type: 'roadmap'	// valid values are 'roadmap', 'satellite', 'terrain'
}).addTo(map);
```


## Legalese

----------------------------------------------------------------------------

"THE BEER-WARE LICENSE":
<ivan@sanchezortega.es> wrote this file. As long as you retain this notice you
can do whatever you want with this stuff. If we meet some day, and you think
this stuff is worth it, you can buy me a beer in return.

----------------------------------------------------------------------------

