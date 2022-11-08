<template>
  <div class="cards">
    <div class="card">
      <img :src="card.image" :alt="card.mainTitle" />
      <div class="card-content">
        <h5>{{ card.mainTitle }}</h5>
        <div>
          <b-button variant="dark" @click="onCardClick(card.id)"
            >See More</b-button
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: {
    card: {
      type: Object,
      default: () => ({}),
    },
  },
  methods: {
    onCardClick(id) {
      this.$emit("productCardClicked", id);
    },
  },
};
</script>
