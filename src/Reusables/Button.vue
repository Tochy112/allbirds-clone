<template>
  <div class="button_div">
    <button
      :style="{
        width: width,
        backgroundColor: bgcolor,
        color: color,
        hover: hover,
      }"
    >
      {{ content }}
    </button>
  </div>
</template>

<script>
export default {
  name: "Button",
  props: {
    content: String,
    width: String,
    bgcolor: String,
    color: String,
    hover: String,
  },
};
</script>

<style scoped>
button {
  height: 3rem;
  padding: 0 1rem;
  font-weight: 545;
  color: #212a2f;
  font-size: 0.9rem;
  border-radius: 3px;
  transition: background-color 0.1s ease-in-out;
  cursor: pointer;
  border: 5px #fff;
  margin: 0 auto;
}
button:hover {
  background-color: #212a2f;
  color: #fff;
  border-radius: 3px;
  border: 5px #212a2f;
}
@media screen and (max-width: 320px) {
  button {
    width: 8.5rem;
    height: 3rem;
  }
}
</style>
