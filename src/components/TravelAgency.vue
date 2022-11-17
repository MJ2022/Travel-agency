<template>
  <div>
    <TheSearchBar @selectedCity="onSelectedCity" />
    <BookingForm
      :destination="destination"
      @selectedReservation="onSelectedReservation"
    />
    <Bookings :reservation="reservation" />
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
    onSelectedReservation({ base_filters, result }) {
      this.reservation = { base_filters, result };
    },
  },
  data() {
    return {
      destination: {
        destID: "",
        destType: "",
      },
      reservation: {
        base_filters: [],
        result: [],
      },
    };
  },
};
</script>

<style scoped></style>
