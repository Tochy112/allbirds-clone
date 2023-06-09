<template>
  <div class="button_div">
    <button>{{ content }}</button>
  </div>
</template>

<script>
export default {
  name: "Button",
  props: {
    content: String,
  },
};
</script>

<style scoped>
button {
  width: 10rem;
  height: 3rem;
  padding: 0 1rem;
  font-weight: 545;
  color: #212a2f;
  font-size: 0.9rem;
  border-radius: 3px;
  transition: background-color 0.1s ease-in-out;
  cursor: pointer;
  border: 5px #fff;
}
button:hover {
  background-color: #212a2f;
  color: #fff;
  border-radius: 3px;
  border: 5px #212a2f;
}
@media screen and (max-width: 320px) {
  button {
    width: 9rem;
    height: 3rem;
  }
}
</style>
