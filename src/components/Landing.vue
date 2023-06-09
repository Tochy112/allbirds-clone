<template>
  <section class="landing_section">
    <div class="img_div">
      <div class="content_div">
        <h1>Longer Days, Lighter Shoes</h1>
        <p>
          Give your feet some fresh air in styles made with eucalyptus fiber.
        </p>

        <div class="btn_div">
          <Button content="SHOP MEN" />
          <Button content=" SHOP WOMEN" />
        </div>
      </div>
    </div>
    <div class="bottom_ad">
      <p>
        <b>Discover Your Perfect Pair</b> Try our Style Quiz to find the best
        pair for you.
        <a href="/">Take the Style Quiz</a>
      </p>
    </div>
  </section>
</template>

<script>
import Button from "../Reusables/Button.vue";
export default {
  name: "Landing",
  components: {
    Button,
  },
};
</script>

<style scoped>
.landing_section {
  overflow-x: hidden !important;
}
.img_div {
  background-image: url("../assets/landing_right.jpg");
  width: 100vw;
  height: 100vh;
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  padding-top: 47rem;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}
.content_div {
  padding: 11rem 2rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  /* background-color: red; */
}
.content_div h1 {
  font-size: 2.8rem;
  color: #fff;
}
.content_div p {
  color: #fff;
}
.content_div .btn_div {
  display: flex;
  gap: 10px;
}

/* ad side */
.bottom_ad {
  text-align: center;
  background-color: #212a2f;
  color: #fff;
  font-size: 16px;
  padding: 0.9rem;
  width: 100vw;
  overflow-x: hidden;
}
.bottom_ad a {
  color: #fff;
  text-decoration: underline;
  margin-right: 5px;
}

/* Media query */
@media screen and (max-width: 860px) {
  .content_div h1 {
    font-size: 2.4rem;
    color: #fff;
  }
}
@media screen and (max-width: 820px) {
  .img_div {
    background-image: url("../assets/Landing_page.PNG");
  }
  .content_div h1 {
    font-size: 2rem;
    color: #fff;
  }
}
@media screen and (max-width: 480px) {
  .content_div {
    padding: 11rem 0.5rem;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }
}
</style>
