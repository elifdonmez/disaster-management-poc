<!-- EstimationPanel.vue -->
<template>
  <div class="social-media-panel">
    <h2>Social Media Help Requests</h2>
    <ul v-if="socialMediaHelpRequests.length > 0">
      <li v-for="social in socialMediaHelpRequests" :key="social.id">
        <strong>ID:</strong> {{ social.id }} - {{ social.type }}
        <strong>Accuracy:</strong> {{ social.accuracy }}
      </li>
    </ul>
    <p v-else>No help requests from social media available.</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      socialMediaHelpRequests: [], // Dummy data for demonstration
    };
  },
  mounted() {
    // Simulate data (replace this with real integration)
    setTimeout(() => {
      this.socialMediaHelpRequests = [
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
.social-media-panel {
  position: fixed;
  bottom: 0;
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

.social-media-panel h2 {
  font-size: 22px;
  margin-bottom: 10px;
}

.social-media-panel ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.social-media-panel li {
  margin-bottom: 8px;
}

.social-media-panel p {
  margin-top: 10px;
  font-style: italic;
}

/* Add more styles as needed */
</style>
