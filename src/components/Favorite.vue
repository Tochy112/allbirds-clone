<template>
  <section class="favorite_section">
    <h1>Our Favorites</h1>

    <div class="clickable_slide">
      <h3 @click="activePort = 'firstSet'">FOR EVERYDAY</h3>
      <h3 @click="activePort = 'secondSet'">FOR ACTIVITY</h3>
      <h3 @click="activePort = 'thirdSet'">FOR TRAVEL</h3>
    </div>
    <div class="scroll_div">
      <div v-show="activePort === 'firstSet'"></div>
      <div v-show="activePort === 'secondSet'"></div>
      <div v-show="activePort === 'thirdSet'"></div>
    </div>
    <!-- Desktop view -->
    <div class="boxes">
      <div class="box_group" v-if="activePort === 'firstSet'">
        <FavoriteBox
          :image="require('@/assets/favourite1.avif')"
          header="Tree Runner"
          :icon="require('@/assets/Tree.jpg')"
          text="Light and Breezy Sneaker"
        />
        <FavoriteBox
          :image="require('@/assets/favourite2.avif')"
          header="Tree Breezer"
          :icon="require('@/assets/Tree.jpg')"
          text="Breezy Flat"
        />
        <FavoriteBox
          :image="require('@/assets/favourite3.avif')"
          header="Wool Runner"
          :icon="require('@/assets/Wool.jpg')"
          text="Cozy Sneaker"
        />
      </div>

      <div class="box_group" v-if="activePort === 'secondSet'">
        <FavoriteBox
          :image="require('@/assets/favourite4.avif')"
          header="Tree Dasher 2"
          :icon="require('@/assets/Tree.jpg')"
          text="Comfy, Breezy, Everyday Runs"
        />
        <FavoriteBox
          :image="require('@/assets/favourite5.avif')"
          header="Golf Dasher"
          :icon="require('@/assets/Tree.jpg')"
          text="stabilizing And Comfy For The Green"
        />
        <FavoriteBox
          :image="require('@/assets/favourite6.avif')"
          header="Tree Flyer"
          :icon="require('@/assets/Tree.jpg')"
          text="Light, Bouncy, Long Distance Runs"
        />
      </div>

      <div class="box_group" v-if="activePort === 'thirdSet'">
        <FavoriteBox
          :image="require('@/assets/favourite7.avif')"
          header="Tree Lounger"
          :icon="require('@/assets/Tree.jpg')"
          text="Breezy Slip-On"
        />
        <FavoriteBox
          :image="require('@/assets/favoutite8.avif')"
          header="Allgood Cotton Tee"
          :icon="require('@/assets/Tree.jpg')"
          text="Everyday organic Cotton T-Shirt"
        />
        <FavoriteBox
          :image="require('@/assets/favourite9.avif')"
          header="Plant pacer"
          :icon="require('@/assets/Wool.jpg')"
          text="Classic Pacer"
        />
      </div>
    </div>

    <!-- <div v-if="activePort === 'web1'">
      <div class="box_div" v-for="web in web1" :key="web.id">
        <div>
          <img style="width: 300px" :src="web.image" alt="" />
          <h2>{{ web.text }}</h2>
        </div>
      </div>
    </div> -->
  </section>
</template>

<script>
import FavoriteBox from "@/Reusables/FavoriteBox.vue";
export default {
  name: "Favorite",
  components: {
    FavoriteBox,
  },
  data() {
    return {
      activePort: "firstSet",
    };
  },
};
</script>

<style scoped>
.favorite_section {
  padding: 3rem;
  background-color: #fefefe;
}
.favorite_section h1 {
  text-align: center;
  color: #212a2f;
  font-size: 2rem;
}
.clickable_slide {
  display: flex;
  justify-content: center;
  gap: 10rem;
  margin: 2rem 0;
  border-bottom: 2px solid #d3d4d5;
  padding: 0.5rem 0;
}
.clickable_slide h3 {
  color: #4a4d50;
  cursor: pointer;
  position: relative;
}
.scroll_div {
  /* background-color: red; */
  /* padding: 1rem; */
  display: flex;
  gap: 7rem;
  margin: 0 2rem;
  justify-content: center;
  align-items: center;
  overflow-x: visible;
}
.scroll_div div {
  width: 10rem;
  height: 2px;
  background-color: #000;
  position: relative;
  bottom: 2.1rem;
}
.box_group {
  display: flex;
  justify-content: space-evenly;
}

/* @media screen and (max-width: 850px) {
  .clickable_slide h3 {
    font-size: small;
  }
  .scroll_div div {
    width: 8rem;
    height: 2px;
  }
  .clickable_slide {
    display: flex;
    justify-content: center;
    gap: 8rem;
    margin: 2rem;
    border-bottom: 2px solid #d3d4d5;
    padding: 0.5rem 0;
  }
} */
</style>
