<template>
  <div>
    <div class="container mt-5">
      <h1 class="mt-5 text-center text-white bg-dark fst-italic rounded">
        TOP SELL
      </h1>
      <div class="row mt-3 g-5">
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
        <p>{{ activeCard.price }}</p>
        <p>{{ activeCard.reviews }}</p>
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
          image: require("@/assets/vuelo.jpg"),
          mainTitle: "Brasil",
          price: 300,
          reviews: "good",
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
