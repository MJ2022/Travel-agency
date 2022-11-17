<template>
  <div class="container-fluid">
    <h2>Booking:{{ reservation.base_filters[0].title }}</h2>
    <h3>Currency code:{{ reservation.result[1].currencycode }}</h3>
    <table>
      <tr>
        <th>Hotel</th>
        <th>Price</th>
        <th>Address</th>
        <th>Peoples Reviews</th>
      </tr>
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
.container-fluid {
  margin: 20px;
  padding: 30px;
}

table,
td,
th {
  border: 2px solid black;
  border-collapse: separate;
  background-color: #e9e8e8;
  font-size: 1.25em;
  margin-left: 25%;
}

h2,
h3 {
  letter-spacing: 0.3em;
  font-weight: bold;
  color: #fffffff1;
  font-size: 35px;
}
</style>
