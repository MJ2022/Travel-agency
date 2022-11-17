<template>
  <div>
    <form class="container">
      <label for="room">Rooms</label>
      <input v-model="booking.room" type="number" id="room" />
      <label for="guest">Guest</label>
      <input v-model="booking.guest" type="number" id="guest" />
      <label for="in">Check in</label>
      <input v-model="booking.in" type="date" id="in" />
      <label for="out">Check out</label>
      <input v-model="booking.out" type="date" id="out" />
      <button type="submit" @click="clickedButton">GO</button>
    </form>
  </div>
</template>
<script>
export default {
  name: "BookingForm",
  data() {
    return {
      booking: {
        room: "",
        guest: "",
        in: "",
        out: "",
      },
      reservations: {},
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
    clickedButton: async function (event) {
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
        this.reservations = json;
        this.$emit("selectedReservation", {
          base_filters: this.reservations.base_filters,
          result: this.reservations.result,
        });
      } catch (err) {
        console.log(err);
      }
    },
  },
};
</script>

<style scoped>
.container > input {
  margin-left: 10px;
  margin-right: 10px;
  background: #d8d8d8;
}

.container {
  color: rgb(0, 0, 0);
  font-size: 1.25em;
  font-weight: bold;
}

button {
  background-color: #000000;
  color: #f0ffff;
}
</style>
