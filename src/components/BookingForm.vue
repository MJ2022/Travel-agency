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
    <h5>{{ destination.dest_id }}-{{ destination.dest_type }}</h5>
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
      console.log(this.booking);

      /*  try {
        const options = {
          method: "GET",
          headers: {
            "X-RapidAPI-Key":
              "abf1ba1bcbmshecd464effca6792p1165f1jsn401b78cfaaab",
            "X-RapidAPI-Host": "apidojo-booking-v1.p.rapidapi.com",
          },
        };
        const data = await fetch(
          `https://apidojo-booking-v1.p.rapidapi.com/properties/list?offset=0&arrival_date=%3CREQUIRED%3E&departure_date=%3CREQUIRED%3E&guest_qty=1&dest_ids=-3712125&room_qty=1&search_type=city`,
          options
        );
        const json = await data.json();
        this.items = json;
        console.log(this.items);
      } catch (err) {
        console.log(err);
      } */
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
