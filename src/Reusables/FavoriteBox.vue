<template>
  <div class="parent">
    <div class="fav_box">
      <div class="img">
        <img :src="image" alt="images" />
      </div>
      <div class="text">
        <h2>{{ header }}</h2>
      </div>

      <div class="para">
        <img :src="icon" alt="icon" />
        <p>{{ text }}</p>
      </div>

      <div class="child-box">
        <div class="btn-div">
          <Button content="SHOP MEN" />
          <Button content="SHOP WOMEN" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "@/Reusables/Button.vue";
export default {
  name: "FavoriteBox",
  components: {
    Button,
  },
  props: {
    image: String,
    header: String,
    icon: String,
    text: String,
  },
};
</script>

<style scoped>
.img {
  width: 25rem;
  height: 24rem;
}
.img img {
  width: 100%;
  height: 100%;
  transition: all 0.3s ease-in-out;
}
.fav_box {
  width: 25rem;
  height: 32rem;
  /* margin: auto; */
  background-color: #fff;
  box-shadow: rgb(51, 51, 51, 0.5) 5px 0 9px 0px;
  position: relative;
}
.text {
  margin: 0 2rem;
  border-bottom: 2px solid #d3d4d5;
  padding: 0.5rem 0;
}
.para {
  display: flex;
  align-items: center;
  gap: 1.2rem;
  font-size: 15px;
  margin: 1rem 2rem;
}
.para img {
  width: 2rem;
}
.child-box {
  background-color: rgba(51, 51, 51, 0.5);
  width: 25rem;
  height: 24rem;
  position: absolute;
  left: 0rem;
  top: 0rem;
  display: none;
}
.child-box .btn-div {
  display: flex;
  flex-direction: column;
  text-align: center;
  margin: 35% auto;
  gap: 10px;
}

.fav_box:hover .child-box,
.fav_box:hover .img img {
  display: block;
  transform: scale(100.5%);
}
/* 
@media screen and (max-width: 995) {
  .child-box {
    background-color: #fff;
    width: 25rem;
    height: 24rem;
    position: relative;
    left: 0rem;
    top: 0rem;
    display: none;
  }
} */
</style>
