<template>
  <div class="home">
    <Landing />
    <Favorite />
    <Summer />
    <SummerStyles />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Landing from "@/components/Landing.vue";
import Favorite from "@/components/Favorite.vue";
import Summer from "@/components/Summer.vue";
import SummerStyles from "@/components/SummerStyles.vue";
import Footer from "@/components/Footer.vue";
export default {
  name: "HomeView",
  components: {
    Landing,
    Favorite,
    Summer,
    SummerStyles,
    Footer,
  },
};
</script>
