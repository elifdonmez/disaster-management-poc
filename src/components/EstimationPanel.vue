<!-- EstimationPanel.vue -->
<template>
  <div class="estimation-panel">
    <h2>AI Estimated Help Requests</h2>
    <ul v-if="estimatedHelpRequests.length > 0">
      <li v-for="estimation in estimatedHelpRequests" :key="estimation.id">
        <strong>ID:</strong> {{ estimation.id }} - {{ estimation.type }}
        <strong>Accuracy:</strong> {{ estimation.accuracy }}
      </li>
    </ul>
    <p v-else>No estimated help requests available.</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      estimatedHelpRequests: [], // Dummy data for demonstration
    };
  },
  mounted() {
    // Simulate AI-generated data (replace this with real AI integration)
    setTimeout(() => {
      this.estimatedHelpRequests = [
        { id: 1, type: "Medical Assistance", accuracy: "90%" },
        { id: 2, type: "Food Supply", accuracy: "90%" },
        { id: 3, type: "Shelter Support", accuracy: "90%" },
        // Add more simulated data as needed
      ];
    }, 2000); // Simulating delay as if data is fetched asynchronously
  },
};
</script>

<style scoped>
.estimation-panel {
  position: fixed;
  top: 0;
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

.estimation-panel h2 {
  font-size: 22px;
  margin-bottom: 10px;
}

.estimation-panel ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.estimation-panel li {
  margin-bottom: 8px;
}

.estimation-panel p {
  margin-top: 10px;
  font-style: italic;
}

/* Add more styles as needed */
</style>
