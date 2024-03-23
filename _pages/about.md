---
layout: page
title: About
description: I'm an innovative and curious person who has a lot of varied experience throughout the environmental consulting market.
permalink: /about/
image: '/images/DustyWerth2.jpeg'
image_caption: ''
---

Hello! I'm Dusty, with a varied career spanning over 17 years in GIS and environmental consulting. My professional days are filled with process mapping, developing innovative tools, and leading dedicated teams through complex projects. My journey is underpinned by deep technical knowledge across data analysis, data visualization, cloud platforms, and application development. This blend of skills has allowed me to drive significant improvements in quality, efficiency, innovation, and training.

Beyond my professional life, I'm deeply passionate about exploring the world and its myriad cultures. Traveling is more than a hobby—it's a way of life that opens my mind to new perspectives and inspires my every endeavor. Whether it's the vibrant life in a foreign city or the serene beauty of a secluded spot, each destination offers new lessons, fresh challenges, and the chance to connect with diverse people.

<strong>My Travel Map</strong>
<div id="mapid" style="height: 400px;"></div>
<script>
document.addEventListener('DOMContentLoaded', function() {
  var map = L.map('mapid').setView([39.061122083, -60.240289294], 2);
  
  var baseMaps = {
    "OpenTopoMap": L.tileLayer('https://{s}.tile.opentopomap.org/{z}/{x}/{y}.png', {
      attribution: 'Map data © <a href="https://opentopomap.org">OpenTopoMap</a>',
      maxZoom: 17,
    }),
    "OpenStreetMap": L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '© OpenStreetMap contributors'
    }),
    "ESRI World Imagery": L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}', {
      attribution: 'Tiles © Esri &mdash; Source: Esri, i-cubed, USDA, USGS, AEX, GeoEye, Getmapping, Aerogrid, IGN, IGP, UPR-EGP, and the GIS User Community'
    })
  };

  baseMaps["OpenTopoMap"].addTo(map);

  var overlayMaps = {}; // Object to hold GeoJSON layers

  // Function to add GeoJSON data to the map with customizable marker options
  function addGeoJSONLayer(url, fillColor, name) {
    var geojsonMarkerOptions = {
      radius: 8,
      fillColor: fillColor,
      color: "#000",
      weight: 3,
      opacity: 1,
      fillOpacity: 0.8
    };

    fetch(url)
      .then(function(response) { return response.json(); })
      .then(function(data) {
        var layer = L.geoJSON(data, {
          pointToLayer: function (feature, latlng) {
            return L.circleMarker(latlng, geojsonMarkerOptions);
          }
        }).addTo(map); // Add the layer to the map immediately
        overlayMaps[name] = layer; // Register the layer for the overlay control
      })
      .catch(function(error) {
        console.error('Error fetching GeoJSON: ', error);
      });
  }

  // Add GeoJSON layers
  addGeoJSONLayer('https://raw.githubusercontent.com/DustyWerth/DustyWerth.github.io/main/_geojson/Travel_Locs.geojson', '#0000FF', 'Travel Locations');
  addGeoJSONLayer('https://raw.githubusercontent.com/DustyWerth/DustyWerth.github.io/main/_geojson/National_Parks.geojson', '#00FF00', 'National Parks');
  addGeoJSONLayer('https://raw.githubusercontent.com/DustyWerth/DustyWerth.github.io/main/_geojson/Camping_Sites.geojson', '#FFFF00', 'Camping Sites');

  // Ensure the GeoJSON layers have been added before creating the control
  // This simplistic approach might need adjustments for real-world usage
  setTimeout(() => {
    L.control.layers(baseMaps, overlayMaps).addTo(map);
  }, 1000);

  // Legend with updated styling for a white background
  var legend = L.control({position: 'bottomright'});
  legend.onAdd = function (map) {
    var div = L.DomUtil.create('div', 'info legend');
    div.style.backgroundColor = 'white'; // Set background color to white
    div.style.padding = '6px'; // Add some padding
    div.style.border = '1px solid #ddd'; // Add a border
    div.style.borderRadius = '4px'; // Optional: round the corners
    div.style.boxShadow = '0 0 15px rgba(0,0,0,0.2)'; // Optional: add a subtle shadow
    div.style.opacity = '0.9'; // Optional: make the background slightly transparent

    var categories = ['Travel Locations', 'National Parks', 'Camping Sites'],
        colors = ['#0000FF', '#00FF00', '#FFFF00'];

    for (var i = 0; i < categories.length; i++) {
        div.innerHTML +=
            '<i style="background:' + colors[i] + '; width: 10px; height: 10px; border-radius: 50%; display: inline-block; margin-right: 5px;"></i> ' +
            categories[i] + '<br>';
    }
    return div;
  };
  legend.addTo(map);
});
</script>

<div class="gallery-box">
  <div class="gallery">
    <img src="/images/LadyLuck.jpeg" loading="lazy">
    <img src="/images/La_Sagrada.jpg" loading="lazy">
    <img src="/images/USSArizona.jpeg" loading="lazy">
    <img src="/images/Sevile.jpg" loading="lazy">
    <img src="/images/India_Elephant_Island.jpeg" loading="lazy">
    <img src="/images/Portugal.jpg" loading="lazy">
   </div>
  <em>Travel Gallery</em>
</div>

When not exploring, I'm often found behind the grill or the smoker, indulging in my love for cooking. As a seasoned competitor on the BBQ competition circuit, I've earned numerous awards for my culinary skills. Cooking, especially BBQ, allows me to blend art and science, creating delicious experiences for friends and family.

Gardening offers me a peaceful escape, a connection to the earth that's both creative and nurturing. My garden is a source of joy and fulfillment, a testament to the beauty that comes from care and patience. At home, life is further enriched by my husband of 9 years and our three dogs, providing a foundation of love, laughter, and the occasional bark.

<div class="gallery-box">
  <div class="gallery">
    <img src="/images/DustyRussel.jpeg" loading="lazy">
    <img src="/images/Milo.jpg" loading="lazy">
    <img src="/images/Gussie.jpeg" loading="lazy">
    <img src="/images/Trooper.jpeg" loading="lazy">
    <img src="/images/Ribs.jpeg" loading="lazy">
    <img src="/images/Chicken.jpg" loading="lazy">
  </div>
  <em>Home Life Gallery</em>
</div>

I come from a large family where gatherings with my brothers, their dogs, and my nieces and nephews are cherished. These moments remind me of the invaluable support and grounding that only family can provide.

Nature calls to me, offering both solace and adventure. Hiking, camping, and simply being in the great outdoors are essential to my well-being, reminding me of the planet's beauty and our responsibility to protect it.

<div class="gallery-box">
  <div class="gallery">
    <img src="/images/Moose.jpeg" loading="lazy">
    <img src="/images/RedRocks.jpg" loading="lazy">
    <img src="/images/RMNP_Hike.jpeg" loading="lazy">
    <img src="/images/Bear.jpeg" loading="lazy">
    <img src="/images/Aruba_Sunset.jpeg" loading="lazy">
    <img src="/images/Glacier.jpeg" loading="lazy">
  </div>
  <em>Outdoor Life Gallery</em>
</div>

At heart, I'm someone who seeks to embrace life fully, from intellectual challenges to the simple joys of a meal shared with friends and family. My life is a unique mixture of professional achievements and personal passions. I believe in continuous learning, giving back, and cherishing every moment.

Welcome to my page, and thank you for joining me on this journey.
