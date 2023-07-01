<template>
  <section class="summer-style-intro">
    <div class="summer-style-bg"></div>
    <div class="intro-section">
      <h1>Summer Styles</h1>
      <p>Get a move on (or out) in bouncy shoes made with natural materials.</p>
      <div class="btn-div">
        <Button
          content="SHOP MEN"
          width="10rem"
          bgcolor="#212a2f"
          color="#fff"
          class="btn"
        />
        <Button
          content="SHOP WOMEN"
          width="10rem"
          bgcolor="#212a2f"
          color="#fff"
          class="btn"
        />
      </div>
    </div>

    <div class="slide-secton">
      <h2 class="title">Stories</h2>

      <div class="mobile_view">
        <Swiper
          :navigation="{ nextEl: '.nextArrow', prevEl: '.prevArrow' }"
          :grabCursor="true"
          :modules="modules"
          class="mySwiper"
          :slides-per-view="slidesPerView"
          :breakpoints="swiperBreakpoints"
        >
          <div class="slider-navigation">
            <div class="nav-indicator prevArrow">
              <img src="@/assets/left-arrow.png" alt="prev" />
            </div>
            <div class="nav-indicator nextArrow">
              <img src="@/assets/right-arrow.png" alt="next" />
            </div>
          </div>
          <Swiper-slide v-for="data in sum_data" :key="data.id">
            <div class="sum_box">
              <div class="img">
                <img :src="data.image" alt="images" />
              </div>
              <div class="text">
                <h2>{{ data.header }}</h2>
              </div>

              <div class="description">
                <p>{{ data.text }}</p>
              </div>
            </div>
          </Swiper-slide>
        </Swiper>
      </div>
    </div>
  </section>
</template>
<script>
import Button from "@/Reusables/Button";

import { Swiper, SwiperSlide } from "swiper/vue";
// Import Swiper styles
import "swiper/css";

import "swiper/css/pagination";

import "swiper/css/navigation";

// import required modules
import { Navigation } from "swiper";

import img1 from "@/assets/story1.avif";
import img2 from "@/assets/story2.avif";
import img3 from "@/assets/story3.avif";
import img4 from "@/assets/story4.avif";
import img5 from "@/assets/story5.avif";
import img6 from "@/assets/story6.avif";
export default {
  name: "SummerStyles",
  components: {
    Button,
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Navigation],
    };
  },
  data() {
    return {
      slidesPerView: 1, // Default number of slides per view
      swiperBreakpoints: {
        // Define breakpoints and corresponding slides per view
        0: {
          slidesPerView: 1,
          spaceBetween: 10,
        },
        521: {
          slidesPerView: 1.4,
          // spaceBetween: 20,
        },
        860: {
          slidesPerView: 2.1,
          // spaceBetween: 20,
        },
        960: {
          slidesPerView: 2.3,
          // spaceBetween: 10,
        },
        1260: {
          slidesPerView: 3.1,
          spaceBetween: 30,
        },
      },

      sum_data: [
        {
          id: 1,
          image: img1,
          header: "Introducing MO.ONSHOT",
          text: "learn more about the world's first net zero carbon shoe, and how its landmark 0.0kg C02e carbon footprint was achieved without relying on a single carbon offset.",
        },
        {
          id: 2,
          image: img2,
          header: "Allbirds ReRun",
          text: "Introducing our resale marketplace where you shop slightly imperfect and gently used products, extending their life and lowering our impact on the planet.",
        },
        {
          id: 3,
          image: img3,
          header: "2022 Flight Status Report",
          text: "Our version of a sustainability report is here, highlighting our progress across a variety of areas in 2022.",
        },
        {
          id: 4,
          image: img4,
          header: "Allbirds x Marshawn Lynch",
          text: 'In episode two of "Schooled" Marshawn and his classmates learn that if we just listen to Mother Nature, she will give us everything we need.',
        },
        {
          id: 5,
          image: img5,
          header: "Giving Mother Nature a Seat at the Table",
          text: "We are prioritizing the planet, not just profits. Introduucing the next generation business.",
        },
        {
          id: 6,
          image: img6,
          header: "We're A Certified B Corp",
          text: "From the very beginning, the environment has been a stakeholder here.",
        },
      ],
    };
  },
};
</script>

<style scoped>
.summer-style-bg {
  background-image: url(@/assets/summer-styles-background.avif);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  width: 100vw;
  height: 90vh;
  overflow-x: hidden;
  margin-bottom: 3rem;
}
.intro-section {
  text-align: center;
  margin: 4rem 0;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.slide-secton {
  padding: 0 3rem;
}
.slide-secton .title {
  margin: 2rem 0.5rem;
}
.intro-section .btn-div {
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  /* margin: 1rem 0; */
}
.sum_box {
  width: 23rem;
  height: 32rem;
  background-color: #fff;
  box-shadow: rgb(51, 51, 51, 0.5) 5px 0 9px 0px;
  padding-bottom: 2rem;
}
.sum_box img {
  width: 23rem;
  height: 22rem;
}
.text {
  margin: 0 1rem;
  padding: 0.5rem 0;
}
.slider-navigation {
  display: flex;
  justify-content: space-between;
  position: relative;
  align-items: center;
  bottom: 18rem;
  z-index: 10;
}
.nav-indicator {
  cursor: pointer;
  margin: 0 0.3rem;
  /* background-color: rgb(255, 255, 255, 0.85); */
  border-radius: 50%;
  width: max-content;
  height: max-content;
}
.nav-indicator img {
  width: 5rem;
  height: 5rem;
}
.description {
  padding: 0 1rem;
}
.intro-section .btn-div #btn:hover {
  background-color: "#fff" !important;
  color: " #212a2f";
  border-radius: "3px";
  border: "5px #212a2f";
}

@media screen and (min-width: 1025px) {
  .sum_box {
    width: 25rem;
    height: 34rem;
    /* padding-bottom: 2rem; */
  }
  .sum_box img {
    width: 25rem;
    height: 22rem;
  }
}
/* mobile */
@media screen and (max-width: 995px) {
  .sum_box {
    width: 22rem;
    height: 34rem;
  }
  .sum_box img {
    width: 22rem;
    height: 22rem;
  }
}
@media screen and (max-width: 861px) {
  .sum_box {
    width: 60vw;
    height: 34rem;
  }
  .sum_box img {
    width: 60vw;
    height: 20rem;
  }
  .slide-secton {
    padding: 0 2rem;
  }
}
@media screen and (max-width: 520px) {
  .summer_img_div {
    height: 50vh;
  }

  .summer-style-bg {
    background-image: url(@/assets/summer-style-mobile-bg.avif);
    height: 50vh;
  }
  .sum_box {
    width: 90vw;
  }
  .sum_box img {
    width: 90vw;
  }
  .slide-secton {
    padding: 0 1rem;
  }
  .intro-section h1 {
    font-size: 1.8rem;
    margin: 0 1rem;
  }
  .intro-section .btn-div {
    display: flex;
    justify-content: center;
    gap: 1rem;
    /* margin: 1rem 0; */
  }

  @media screen and (max-width: 320px) {
    .intro-section .btn-div {
      display: flex;
      justify-content: center;
      gap: 0.2rem;
      margin: 0 2rem;
    }
    .intro-section .btn-div #btn {
      /* width: 3rem; */
      margin: 0;
    }
  }
}
</style>
