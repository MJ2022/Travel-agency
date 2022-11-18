<template>
  <div class="container">
    <h2 class="mt-5 text-center text-black">
      Booking:{{ reservation.baseFilters[0].title }}
    </h2>
    <h3 class="mt-2 mb-5 text-center text-black">
      Currency:{{ reservation.results[1].currencycode }}
    </h3>
    <table class="container">
      <thead>
        <th>Hotel</th>
        <th>Price</th>
        <th>Address</th>
        <th>Peoples Reviews</th>
      </thead>
      <tbody>
        <tr v-for="value in reservation" :key="index">
          <td>{{ value }}</td>
          <!--   <td>{{ value.results[index].price_breakdown.gross_price }}</td>
          <td>{{ value.results[index].address }}</td>
          <td>{{ value.results[index].review_score_word }}</td> -->
        </tr>
      </tbody>
      <!-- <tr>
        <td>{{ reservation.results[2].hotel_name }}</td>
        <td>{{ reservation.results[2].price_breakdown.gross_price }}</td>
        <td>{{ reservation.results[2].address }}</td>
        <td>{{ reservation.results[2].review_score_word }}</td>
      </tr>
      <tr>
        <td>{{ reservation.results[3].hotel_name }}</td>
        <td>{{ reservation.results[3].price_breakdown.gross_price }}</td>
        <td>{{ reservation.results[3].address }}</td>
        <td>{{ reservation.results[3].review_score_word }}</td>
      </tr>
      <tr>
        <td>{{ reservation.results[4].hotel_name }}</td>
        <td>{{ reservation.results[4].price_breakdown.gross_price }}</td>
        <td>{{ reservation.results[4].address }}</td>
        <td>{{ reservation.results[4].review_score_word }}</td>
      </tr>
      <tr>
        <td>{{ reservation.results[5].hotel_name }}</td>
        <td>{{ reservation.results[5].price_breakdown.gross_price }}</td>
        <td>{{ reservation.results[5].address }}</td>
        <td>{{ reservation.results[5].review_score_word }}</td>
      </tr>  -->
    </table>
  </div>
</template>

<script>
export default {
  name: "Bookings",
  data() {
    return {
      index: [1, 2, 3, 4, 5],
    };
  },
  props: {
    reservation: {
      type: Object,
      default: function () {
        return {};
      },
    },
  },
};
</script>

<style scoped>
table,
td,
th {
  border: 2px solid black;
  border-collapse: collapse;
  background-color: #e9e8e8;
  font-size: 1.25em;
}

h2,
h3 {
  letter-spacing: 0.3em;
  font-weight: bold;
  color: #000000f1;
  font-size: 35px;
}

th {
  font-weight: bold;
  text-align: center;
  font-family: "book antiqua";
  font-size: 2em;
  padding: 20px;
}
</style>
