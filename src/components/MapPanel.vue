<!-- MapPanel.vue -->
<template>
  <div ref="mapPanel" class="map-panel">
    <h1>Disaster Management Map</h1>
  </div>
</template>

<script>
import L from "leaflet";
import "leaflet/dist/leaflet.css";

export default {
  data() {
    return {
      map: null,
    };
  },
  mounted() {
    this.map = L.map(this.$refs.mapPanel).setView([41.0082, 28.9784], 13);

    // Add an custom pin icon
    const earthquake = L.icon({
      iconUrl: "/earthquake.png", // Assuming the image is in the public directory
      iconSize: [32, 32],
      iconAnchor: [16, 32],
      popupAnchor: [0, -32],
    });

    // Add an custom ai pin icon
    const aiPinIcon = L.icon({
      iconUrl: "/microchip.png", // Assuming the image is in the public directory
      iconSize: [32, 32],
      iconAnchor: [16, 32],
      popupAnchor: [0, -32],
    });

    // Add an custom ai pin icon
    const helpPinIcon = L.icon({
      iconUrl: "/help.png", // Assuming the image is in the public directory
      iconSize: [32, 32],
      iconAnchor: [16, 32],
      popupAnchor: [0, -32],
    });

    L.tileLayer("https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png", {
      attribution: "© OpenStreetMap contributors",
    }).addTo(this.map);

    // Add markers with custom pin icons for mock locations
    this.addMarker([41.0082, 28.9784], "AI Help ID 1", aiPinIcon);
    this.addMarker([41.015, 28.96], "AI Help ID 2", aiPinIcon);
    this.addMarker([41.005, 28.97], "AI Help ID 3", aiPinIcon);
    this.addMarker([41.002, 28.9784], "Verified Help ID 1", earthquake);
    this.addMarker([41.025, 28.96], "Verified Help ID 2", earthquake);
    this.addMarker([41.0105, 28.97], "Verified Help ID 3", earthquake);
    this.addMarker([41.029, 28.976], "Victim Help ID 1", helpPinIcon);
  },
  methods: {
    addMarker(coordinates, popupContent, icon) {
      L.marker(coordinates, { icon }).addTo(this.map).bindPopup(popupContent);
    },
  },
};
</script>

<style scoped>
.map-panel {
  height: 100vh;
  text-align: center;
  background-color: #1a1a1a; /* Dark background */
  color: #e74c3c; /* Red text color */
}

.map-panel h1 {
  font-size: 28px;
  margin-bottom: 20px;
}

/* Add more styles as needed */
</style>
