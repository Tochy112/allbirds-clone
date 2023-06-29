<template>
  <div class="summer_section">
    <div class="summer_img_div"></div>

    <div class="intro-section">
      <h1>
        Summer Trips Need Super Packable <br />
        Shoes
      </h1>
      <p>We’ve got your 10,000 steps covered, easy.</p>
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
      <h2 class="title">Shop The Collections</h2>

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
  </div>
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

import img1 from "@/assets/summer-slide1.avif";
import img2 from "@/assets/summer-slide2.avif";
import img3 from "@/assets/summer-slide3.avif";
import img4 from "@/assets/summer-slide4.avif";
import img5 from "@/assets/summer-slide5.jpg";
import img6 from "@/assets/summer-slide6.avif";
import img7 from "@/assets/summer-slide7.jpg";
export default {
  name: "Summer",
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
          header: "Summer Styles",
          text: "Breathable shoes are the difference between along walk and a confy one. Shop shoes made from eucalyptus",
        },
        {
          id: 2,
          image: img2,
          header: "New Arrivals",
          text: "The latest styles and limited edition colors that you can only find here (while they last, that is).",
        },
        {
          id: 3,
          image: img3,
          header: "Summer Travel Essentials",
          text: "Easygoing. Super packable. The only hard part will be figuiring out where you're taking them...",
        },
        {
          id: 4,
          image: img4,
          header: "Best Sellers",
          text: "We asked around, and it turns out these styles have a pretty devoted fanbase",
        },
        {
          id: 5,
          image: img5,
          header: "The SuperLight Collection",
          text: "Barely-there feel. Light-as-air fit. Meet our lightest and lowest carbon footprint to date.",
        },
        {
          id: 6,
          image: img6,
          header: "The Running Shop",
          text: "Break a sweat, not the planet in our running shoes, trail shoes, and performance apparel- all made with a mix of sustainable materials.",
        },
        {
          id: 7,
          image: img7,
          header: "Best For Adventure",
          text: "The window for adventure is wide open. We've got things to help you hit the trials, pitvh the tents, and road the trips",
        },
      ],
    };
  },
};
</script>

<style scoped>
.summer_section {
  padding: 3rem 0;
}
.summer_img_div {
  background-image: url(@/assets/summer-trip1.jpg);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  width: 100vw;
  height: 90vh;
  overflow-x: hidden;
}
.slide-secton {
  padding: 0 3rem;
}
.slide-secton .title {
  margin: 2rem 1rem;
}
.intro-section {
  text-align: center;
  margin: 4rem 0;
  display: flex;
  flex-direction: column;
  gap: 1rem;
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
  bottom: 19rem;
  z-index: 10;
}
.nav-indicator {
  cursor: pointer;
  margin: 0 0.3rem;
  /* background-color: rgb(255, 255, 255, 0.85); */
  border-radius: 50%;
  width: 5rem;
  height: 5rem;
}
.nav-indicator img {
  width: 5rem;
  height: 5rem;
}
.description {
  padding: 0 1rem;
}

@media screen and (min-width: 1025px) {
  .sum_box {
    width: 25rem;
    height: 32rem;
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
    height: 32rem;
  }
  .sum_box img {
    width: 22rem;
    height: 22rem;
  }
}
@media screen and (max-width: 861px) {
  .sum_box {
    width: 60vw;
    height: 32rem;
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
    margin: 0 0.1rem;
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
    .intro-section .btn-div .btn {
      /* width: 3rem; */
      margin: 0;
    }
  }
}
</style>
