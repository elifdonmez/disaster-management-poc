<!-- PinPanel.vue -->
<template>
  <div v-if="selectedHelpRequest" class="pin-panel">
    <h2>Help Request Details</h2>
    <ul>
      <li><strong>ID:</strong> {{ selectedHelpRequest.id }}</li>
      <li><strong>Location:</strong> {{ selectedHelpRequest.location }}</li>
      <!-- Add more details as needed -->
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    selectedHelpRequest: Object,
  },
};
</script>

<style scoped>
.pin-panel {
  position: fixed;
  top: 0;
  right: 0;
  background-color: #e74c3c; /* Red background */
  padding: 20px;
  border: 1px solid #c0392b; /* Darker red border */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  max-width: 300px;
  color: #ecf0f1; /* Light text color */
  border-radius: 8px;
}

.pin-panel h2 {
  font-size: 22px;
  margin-bottom: 10px;
}

.pin-panel ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.pin-panel li {
  margin-bottom: 8px;
}

/* Add more styles as needed */
</style>
