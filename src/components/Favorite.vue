<template>
  <section class="favorite_section">
    <h1>Our Favorites</h1>

    <button @click="activePort = 'web1'">toggle 1</button>
    <button @click="activePort = 'web2'">toggle 2</button>
    <button @click="activePort = 'web3'">toggle 3</button>

    <div v-if="activePort === 'web1'">
      <div class="box_div" v-for="web in web1" :key="web.id">
        <div>
          <img style="width: 300px" :src="web.image" alt="" />
          <h2>{{ web.text }}</h2>
        </div>
      </div>
    </div>

    <div v-if="activePort === 'web2'">
      <div class="box_div" v-for="web in web2" :key="web.id">
        <div>
          <img style="width: 200px" :src="web.image" alt="" />
          <h2>{{ web.text }}</h2>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import landing from "../assets/landing_right.jpg";
import shoe from "../assets/shoeType2.avif";
export default {
  name: "Favorite",
  data() {
    return {
      activePort: "web1",
      web1: [
        {
          id: 1,
          image: landing,
          text: "First Image",
        },
      ],
      web2: [
        {
          id: 1,
          image: shoe,
          text: "Second Image",
        },
      ],
    };
  },
};
</script>

<style scoped>
.favorite_section {
  padding: 3rem;
}
.favorite_section h1 {
  text-align: center;
  color: #212a2f;
  font-size: 2rem;
}
</style>
