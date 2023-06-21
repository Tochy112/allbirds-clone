<template>
  <div class="summer_section">
    <div class="summer_img_div"></div>
  </div>
</template>

<script>
export default {
  name: "Summer",
};
</script>

<style scoped>
.summer_section {
  padding: 3rem 0;
}
.summer_img_div {
  background-image: url(@/assets/summer-trip1.jpg);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  width: 100vw;
  height: 90vh;
  overflow-x: hidden;
}

@media screen and (max-width: 520px) {
  .summer_img_div {
    height: 50vh;
  }
}
</style>
