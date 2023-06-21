<template>
  <div class="home">
    <Landing />
    <Favorite />
    <Summer />
  </div>
</template>

<script>
// @ is an alias to /src
import Landing from "@/components/Landing.vue";
import Favorite from "@/components/Favorite.vue";
import Summer from "@/components/Summer.vue";
export default {
  name: "HomeView",
  components: {
    Landing,
    Favorite,
    Summer,
  },
};
</script>
