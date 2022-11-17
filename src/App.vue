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

<style>
body {
  animation: animate 20s ease-in-out infinite;

  background-size: cover;
}

@keyframes animate {
  0%,
  100% {
    background-image: url("./assets/vuelo1.jpg");
  }
  25% {
    background-image: url("./assets/vuelo2.jpg");
  }
  50% {
    background-image: url("./assets/vuelo3.jpg");
  }
  75% {
    background-image: url("./assets/vuelo.jpg");
  }
}
</style>
