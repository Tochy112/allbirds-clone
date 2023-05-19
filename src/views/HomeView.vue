<template>
  <div class="home">
    <Landing />
    <Favorite />
  </div>
</template>

<script>
// @ is an alias to /src
import Landing from "@/components/Landing.vue";
import Favorite from "@/components/Favorite.vue";
export default {
  name: "HomeView",
  components: {
    Landing,
    Favorite,
  },
};
</script>
