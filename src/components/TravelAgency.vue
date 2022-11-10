<template>
  <div>
    <TheSearchBar @selectedCity="onSelectedCity" />
    <BookingForm :destination="destination" />
    <Bookings />
    <ProductList />
  </div>
</template>

<script>
import TheSearchBar from "./TheSearchBar.vue";
import Bookings from "./Bookings.vue";
import ProductList from "./ProductList.vue";
import BookingForm from "./BookingForm.vue";

export default {
  name: "TravelAgency",
  components: {
    Bookings,
    ProductList,
    TheSearchBar,
    BookingForm,
  },
  methods: {
    onSelectedCity({ destID, destType }) {
      this.destination = { destID, destType };
    },
  },
  data() {
    return {
      destination: {
        destID: "",
        destType: "",
      },
    };
  },
};
</script>

<style scoped></style>
