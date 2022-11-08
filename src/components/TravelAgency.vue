<template>
  <div>
    <TheSearchBar @dest="onSelectedCity" />
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
    onSelectedCity(value) {
      this.destination = value;
    },
  },
  data() {
    return {
      destination: {
        dest_id: "",
        dest_type: "",
      },
    };
  },
};
</script>

<style scoped></style>
