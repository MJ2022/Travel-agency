<template>
  <div>
    <div class="container mt-5">
      <h1 class="mt-5 text-center text-white bg-dark fst-italic rounded">
        TOP SELL
      </h1>
      <div class="row mt-3 g-5" id="card">
        <div
          class="col col-lg-4 col-md-6 col-sm-12 text-center"
          :key="index"
          v-for="(card, index) of cards"
        >
          <ProductCard @productCardClicked="handleButton" :card="card" />
        </div>
      </div>
    </div>
    <div>
      <b-modal v-model="modalShow">
        <div>
          <img
            :src="activeCard.image"
            class="img-fluid"
            :alt="activeCard.mainTitle"
          />
        </div>
        <br />
        <p>Price:{{ activeCard.price }}$</p>
        <p>Reviews:{{ activeCard.reviews }}</p>
      </b-modal>
    </div>
  </div>
</template>

<script>
import ProductCard from "./ProductCard.vue";
export default {
  name: "ProductList",
  components: {
    ProductCard,
  },
  data() {
    return {
      modalShow: false,
      activeCard: {},
      cards: [
        {
          id: 0,
          image: require("@/assets/dubai.jpg"),
          mainTitle: "Dubai",
          price: 800,
          reviews: "Really good",
        },
        {
          id: 1,
          image: require("@/assets/madrid.jpg"),
          mainTitle: "Madrid",
          price: 600,
          reviews: "Good",
        },
        {
          id: 2,
          image: require("@/assets/peru.jpg"),
          mainTitle: "Peru",
          price: 250,
          reviews: "Bad",
        },
        {
          id: 3,
          image: require("@/assets/brasil.jpg"),
          mainTitle: "Brasil",
          price: 300,
          reviews: "good",
        },
        {
          id: 4,
          image: require("@/assets/london.jpg"),
          mainTitle: "London",
          price: 400,
          reviews: "Really good",
        },
        {
          id: 5,
          image: require("@/assets/zambia.jpg"),
          mainTitle: "Zambia",
          price: 100,
          reviews: "Medium",
        },
      ],
    };
  },
  methods: {
    handleButton(id) {
      this.activeCard = this.cards[id];
      this.modalShow = true;
    },
  },
};
</script>

<style scoped>
p {
  text-align: center;
  font-style: italic;
  font-size: medium;
  color: #000000;
  letter-spacing: 0.3em;
}
</style>
