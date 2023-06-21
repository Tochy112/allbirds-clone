<template>
  <div class="summer_section">
    <div class="summer_img_div">
      <img src="@/assets/summer-trip1.jpg" alt="" />
    </div>
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
  width: max-content;
  height: max-content;
  overflow-x: hidden;
}
.summer_img_div img {
  width: 100vw;
  /* height: 38rem; */
}
</style>
