<!-- EstimationPanel.vue -->
<template>
  <div class="help-panel">
    <h2>Call for Help</h2>
    <ul v-if="helpRequests.length > 0">
      <li v-for="help in helpRequests" :key="help.id">
        <strong>ID:</strong> {{ help.id }} - {{ help.type }}
        <strong>Accuracy:</strong> {{ help.accuracy }}
      </li>
    </ul>
    <p v-else>No help requests available.</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      helpRequests: [], // Dummy data for demonstration
    };
  },
  mounted() {
    // Simulate AI-generated data (replace this with real AI integration)
    setTimeout(() => {
      this.helpRequests = [
        { id: 1, type: "Medical Assistance", accuracy: "95%" },
        { id: 2, type: "Food Supply", accuracy: "80%" },
        { id: 3, type: "Shelter Support", accuracy: "72%" },
        // Add more simulated data as needed
      ];
    }, 2000); // Simulating delay as if data is fetched asynchronously
  },
};
</script>

<style scoped>
.help-panel {
  position: fixed;
  top: 0;
  right: 0;
  background-color: #c0392b; /* Dark red background */
  padding: 20px;
  border: 1px solid #922b21; /* Darker red border */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  max-width: 300px;
  color: #ecf0f1; /* Light text color */
  border-radius: 8px;
}

.help-panel h2 {
  font-size: 22px;
  margin-bottom: 10px;
}

.help-panel ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.help-panel li {
  margin-bottom: 8px;
}

.help-panel p {
  margin-top: 10px;
  font-style: italic;
}

/* Add more styles as needed */
</style>
