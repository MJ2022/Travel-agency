<template>
  <div>
    <div class="form-group">
      <h1>Search :</h1>
      <input
        v-model="selectedCountry"
        type="text"
        id="search"
        placeholder="Type a City"
        @keyup="loadCard"
      />
      <ul id="list">
        <li
          v-for="item of items"
          :key="item.dest_id"
          @click="onSelectedCity(item.city_name, item.dest_id, item.dest_type)"
        >
          {{ item.city_name }}
        </li>
      </ul>
    </div>
    <div>
      <p>Your choice: {{ selectedCountry }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "TheSearchBar",
  data() {
    return {
      items: [],
      selectedCountry: null,
    };
  },
  methods: {
    loadCard: async function (event) {
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
          `https://apidojo-booking-v1.p.rapidapi.com/locations/auto-complete?text=${event.target.value}&languagecode=en-us`,
          options
        );
        const json = await data.json();
        this.items = json;
        console.log(this.items);
      } catch (err) {
        console.log(err);
      }
    },
    onSelectedCity: function (cityName, destID, destType) {
      this.selectedCountry = cityName;

      this.$emit("selectedCity", { destID, destType });

      this.items = [];
    },
  },
};
</script>

<style scoped>
form {
  text-align: center;
  color: #000000;
  font-size: 1.25em;
  font-style: oblique;
  font-weight: 600;
  margin-top: 25px;
  padding: 10px;
}

h1 {
  font-size: 2em;
  font-style: italic;
  font-weight: bold;
}

p {
  margin: 10px;
  font-size: 2em;
  color: #000000;
  font-weight: bold;
}

#list {
  list-style: none;
  cursor: pointer;
  padding-left: unset;
  margin-left: unset;
}

#list li {
  border: 1px solid #c0c0c0;
  border-top: unset;
}

#search {
  border: unset;
  background: #dbdbdb;
  padding: 0.5em;
}

.form-group {
  display: inline-block;
  margin-left: 30%;
  padding: 20px;
}
</style>
