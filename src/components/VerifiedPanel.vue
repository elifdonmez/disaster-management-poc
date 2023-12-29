<!-- EstimationPanel.vue -->
<template>
  <div class="verified-panel">
    <h2>Verified Help Requests</h2>
    <ul v-if="verifiedHelpRequests.length > 0">
      <li v-for="verified in verifiedHelpRequests" :key="verified.id">
        <strong>ID:</strong> {{ verified.id }} - {{ verified.type }}
      </li>
    </ul>
    <p v-else>No verified help requests available.</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      verifiedHelpRequests: [], // Dummy data for demonstration
    };
  },
  mounted() {
    // Simulate data (replace this with real integration)
    setTimeout(() => {
      this.verifiedHelpRequests = [
        { id: 1, type: "Medical Assistance" },
        { id: 2, type: "Food Supply" },
        { id: 3, type: "Shelter Support" },
        // Add more simulated data as needed
      ];
    }, 2000); // Simulating delay as if data is fetched asynchronously
  },
};
</script>

<style scoped>
.verified-panel {
  position: fixed;
  bottom: 0;
  left: 0;
  background-color: #c0392b; /* Dark red background */
  padding: 20px;
  border: 1px solid #922b21; /* Darker red border */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  max-width: 300px;
  color: #ecf0f1; /* Light text color */
  border-radius: 8px;
}

.verified-panel h2 {
  font-size: 22px;
  margin-bottom: 10px;
}

.verified-panel ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.verified-panel li {
  margin-bottom: 8px;
}

.verified-panel p {
  margin-top: 10px;
  font-style: italic;
}

/* Add more styles as needed */
</style>
