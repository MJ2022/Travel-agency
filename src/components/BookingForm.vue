<template>
  <div>
    <form
      class="container"
      @submit="onSubmit"
      :class="this.errors ? 'errors' : false"
    >
      <label for="room">Rooms</label>
      <input
        v-model="booking.room"
        type="number"
        id="room"
        required
        @invalid="invalidateForm"
      />
      <label for="guest">Guest</label>
      <input
        v-model="booking.guest"
        type="number"
        id="guest"
        required
        @invalid="invalidateForm"
      />
      <label for="in">Check in</label>
      <input
        v-model="booking.in"
        type="date"
        id="in"
        required
        @invalid="invalidateForm"
      />
      <label for="out">Check out</label>
      <input
        v-model="booking.out"
        type="date"
        id="out"
        required
        @invalid="invalidateForm"
      />
      <button type="submit">GO</button>
    </form>
  </div>
</template>
<script>
export default {
  name: "BookingForm",
  data() {
    return {
      errors: false,
      booking: {
        room: "",
        guest: "",
        in: "",
        out: "",
      },
    };
  },
  props: {
    destination: {
      type: Object,
      default: function () {
        return {};
      },
    },
  },
  methods: {
    invalidateForm: function () {
      this.errors = true;
    },
    onSubmit: async function (event) {
      event.preventDefault();
      try {
        const options = {
          method: "GET",
          headers: {
            "X-RapidAPI-Key":
              "abf1ba1bcbmshecd464effca6792p1165f1jsn401b78cfaaab",
            "X-RapidAPI-Host": "apidojo-booking-v1.p.rapidapi.com",
          },
        };
        const data = await fetch(
          `https://apidojo-booking-v1.p.rapidapi.com/properties/list?offset=0&arrival_date=${this.booking.in}&departure_date=${this.booking.out}&guest_qty=${this.booking.guest}&dest_ids=${this.destination.destID}&room_qty=${this.booking.room}&search_type=${this.destination.destType}`,
          options
        );
        const json = await data.json();
        const reservations = json;
        this.$emit("selectedReservation", {
          baseFilters: reservations.base_filters,
          results: reservations.result,
        });
      } catch (err) {
        console.log(err);
      }
    },
  },
};
</script>

<style scoped>
input {
  margin-left: 15px;
  margin-right: 10px;
  background: #d8d8d8;
}

form {
  color: rgb(0, 0, 0);
  font-size: 2.3em;
  font-weight: bold;
}

button {
  background-color: #000000;
  color: #f0ffff;
}
</style>
