<template>
  <div class="container">
    <h2 class="mt-5 text-center text-black">
      Booking:{{ reservation.base_filters[0].title }}
    </h2>
    <h3 class="mt-2 mb-5 text-center text-black">
      Currency:{{ reservation.result[1].currencycode }}
    </h3>
    <table class="container">
      <thead>
        <th>Hotel</th>
        <th>Price</th>
        <th>Address</th>
        <th>Peoples Reviews</th>
      </thead>
      <tr>
        <td>{{ reservation.result[1].hotel_name }}</td>
        <td>{{ reservation.result[1].price_breakdown.gross_price }}</td>
        <td>{{ reservation.result[1].address }}</td>
        <td>{{ reservation.result[1].review_score_word }}</td>
      </tr>
      <tr>
        <td>{{ reservation.result[2].hotel_name }}</td>
        <td>{{ reservation.result[2].price_breakdown.gross_price }}</td>
        <td>{{ reservation.result[2].address }}</td>
        <td>{{ reservation.result[2].review_score_word }}</td>
      </tr>
      <tr>
        <td>{{ reservation.result[3].hotel_name }}</td>
        <td>{{ reservation.result[3].price_breakdown.gross_price }}</td>
        <td>{{ reservation.result[3].address }}</td>
        <td>{{ reservation.result[3].review_score_word }}</td>
      </tr>
      <tr>
        <td>{{ reservation.result[4].hotel_name }}</td>
        <td>{{ reservation.result[4].price_breakdown.gross_price }}</td>
        <td>{{ reservation.result[4].address }}</td>
        <td>{{ reservation.result[4].review_score_word }}</td>
      </tr>
      <tr>
        <td>{{ reservation.result[5].hotel_name }}</td>
        <td>{{ reservation.result[5].price_breakdown.gross_price }}</td>
        <td>{{ reservation.result[5].address }}</td>
        <td>{{ reservation.result[5].review_score_word }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "Bookings",
  data() {
    return {};
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
