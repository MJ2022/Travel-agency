<template>
  <div>
    <h5>{{ reservation }}</h5>
    <!-- <h1>Booking:{{ base.filters[0].layout.title }}</h1>
    <h2>Currency code:{{ result[1].currencycode }}</h2>
    <table>
      <tr>
        <th>Hotel</th>
        <th>Price</th>
        <th>Photo</th>
      </tr>
      <tr>
        <td>{{ result[1].pricebreakdown.gross_price }}</td>
        <td>{{ result[1].main_photo_url }}</td>
        <td>{{ result[1].hotel_name }}</td>
      </tr>
      <tr>
        <td>{{ result[2].hotel_name }}</td>
        <td>{{ result[2].pricebreakdown.gross_price }}</td>
        <td>{{ result[2].main_photo_url }}</td>
      </tr>
      <tr>
        <td>{{ result[3].hotel_name }}</td>
        <td>{{ result[3].pricebreakdown.gross_price }}</td>
        <td>{{ result[3].main_photo_url }}</td>
      </tr>
    </table> -->
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
}
</style>
