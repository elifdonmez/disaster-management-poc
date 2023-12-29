<template>
  <div id="app">
    <header>
      <h1>After Disaster Management Map</h1>
    </header>

    <main>
      <div class="content-wrapper">
        <MapPanel />
        <PinPanel :selectedHelpRequest="selectedHelpRequest" />
        <EstimationPanel />
        <VerifiedPanel />
        <HelpPanel />
        <SocialMediaPanel />
      </div>
    </main>

    <footer>
      <p>&copy; 2023 Disaster Management App</p>
    </footer>
  </div>
</template>

<script>
import MapPanel from "@/components/MapPanel.vue";
import PinPanel from "@/components/PinPanel.vue";
import EstimationPanel from "@/components/EstimationPanel.vue";
import VerifiedPanel from "@/components/VerifiedPanel.vue";
import HelpPanel from "@/components/HelpPanel.vue";
import SocialMediaPanel from "./components/SocialMediaPanel.vue";

export default {
  components: {
    MapPanel,
    PinPanel,
    EstimationPanel,
    VerifiedPanel,
    HelpPanel,
    SocialMediaPanel,
  },
  data() {
    return {
      selectedHelpRequest: null,
    };
  },
};
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

header {
  background-color: #1a1a1a; /* Dark background for the header */
  color: #e74c3c; /* Red text color */
  padding: 10px;
  text-align: center;
}

main {
  flex-grow: 1; /* Make the main section grow to fill the remaining space */
  display: flex;
  justify-content: center;
  align-items: center;
}

.content-wrapper {
  max-width: 1200px; /* Limit the width of the content */
  width: 100%;
}

footer {
  background-color: #1a1a1a; /* Dark background for the footer */
  color: #ecf0f1; /* Light text color */
  padding: 10px;
  text-align: center;
}
</style>
