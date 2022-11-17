<template>
  <div>
    <b-navbar
      variant="light"
      type="dark"
      class="justify-content-left flex-column fs-1 shadow-lg p-3 mb-5 bg-body rounded"
    >
      <img src="../assets/logo.png" class="d-block" alt="logo" />
      ¡The World Awaits You!
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "TheHeader",
};
</script>

<style scoped>
img {
  width: 200px;
  height: 200px;
  border-radius: 30%;
}
</style>
