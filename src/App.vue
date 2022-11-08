<template>
  <div>
    <TheHeader />
    <TravelAgency />
  </div>
</template>

<script>
import TravelAgency from "./components/TravelAgency.vue";
import TheHeader from "./components/TheHeader.vue";

export default {
  name: "App",
  components: {
    TravelAgency,
    TheHeader,
  },
};
</script>
