<template>
  <section class="favorite_section">
    <h1>Our Favorites</h1>

    <div class="clickable_slide">
      <h3 @click="activePort = 'firstSet'">FOR EVERYDAY</h3>
      <h3 @click="activePort = 'secondSet'">FOR ACTIVITY</h3>
      <h3 @click="activePort = 'thirdSet'">FOR TRAVEL</h3>
    </div>
    <div class="scroll_div">
      <div v-show="activePort === 'firstSet'"></div>
      <div v-show="activePort === 'secondSet'"></div>
      <div v-show="activePort === 'thirdSet'"></div>
    </div>
    <!-- Desktop view -->
    <div class="desktop-view">
      <!-- first batch -->
      <div v-if="activePort === 'firstSet'" class="container">
        <div
          class="parent"
          v-for="favourite in favourites1"
          :key="favourite.id"
        >
          <div class="fav_box">
            <div class="img">
              <img :src="favourite.image" alt="images" />
            </div>
            <div class="text">
              <h2>{{ favourite.header }}</h2>
            </div>

            <div class="para">
              <img :src="favourite.icon" alt="icon" />
              <p>{{ favourite.text }}</p>
            </div>

            <div class="child-box">
              <div class="btn-div">
                <Button content="SHOP MEN" width="10rem" />
                <Button content="SHOP WOMEN" width="10rem" />
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- second batch -->
      <div v-if="activePort === 'secondSet'" class="container">
        <div
          class="parent"
          v-for="favourite in favourites2"
          :key="favourite.id"
        >
          <div class="fav_box">
            <div class="img">
              <img :src="favourite.image" alt="images" />
            </div>
            <div class="text">
              <h2>{{ favourite.header }}</h2>
            </div>

            <div class="para">
              <img :src="favourite.icon" alt="icon" />
              <p>{{ favourite.text }}</p>
            </div>

            <div class="child-box">
              <div class="btn-div">
                <Button content="SHOP MEN" width="10rem" />
                <Button content="SHOP WOMEN" width="10rem" />
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- third batch -->
      <div v-if="activePort === 'thirdSet'" class="container">
        <div
          class="parent"
          v-for="favourite in favourites3"
          :key="favourite.id"
        >
          <div class="fav_box">
            <div class="img">
              <img :src="favourite.image" alt="images" />
            </div>
            <div class="text">
              <h2>{{ favourite.header }}</h2>
            </div>

            <div class="para">
              <img :src="favourite.icon" alt="icon" />
              <p>{{ favourite.text }}</p>
            </div>

            <div class="child-box" id="child-box">
              <div class="btn-div">
                <Button content="SHOP MEN" width="10rem" />
                <Button content="SHOP WOMEN" width="10rem" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- mobile view -->
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
        <Swiper-slide v-for="data in mobile_data" :key="data.id">
          <div class="fav_box">
            <div class="img">
              <img :src="data.image" alt="images" />
            </div>
            <div class="text">
              <h2>{{ data.header }}</h2>
            </div>

            <div class="swipe">
              <div class="para">
                <img :src="data.icon" alt="icon" />
                <p>{{ data.text }}</p>
              </div>
              <div class="child-box">
                <div class="btn-div">
                  <Button
                    content="SHOP MEN"
                    id="btn"
                    width="100%"
                    bgcolor="#212a2f"
                    color="#fff"
                  />
                  <Button
                    content="SHOP WOMEN"
                    id="btn"
                    width="100%"
                    bgcolor="#212a2f"
                    color="#fff"
                  />
                </div>
              </div>
            </div>
          </div>
        </Swiper-slide>
      </Swiper>
    </div>
  </section>
</template>

<script>
import Button from "@/Reusables/Button.vue";
import img1 from "@/assets/summer0.jpg";
import img2 from "@/assets/summer1.jpg";
import img3 from "@/assets/summer3.jpg";
import img4 from "@/assets/summer2.jpg";
import img5 from "@/assets/favourite5.avif";
import img6 from "@/assets/favourite6.avif";
import img7 from "@/assets/favourite7.avif";
import img8 from "@/assets/favourite8.avif";
import img9 from "@/assets/favourite9.avif";
import tree from "@/assets/Tree.jpg";
import wool from "@/assets/Wool.jpg";

import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import "swiper/css/pagination";

import "swiper/css/navigation";

// import required modules
import { Navigation } from "swiper";

export default {
  name: "Favorite",
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
      activePort: "firstSet",
      slidesPerView: 1, // Default number of slides per view
      swiperBreakpoints: {
        // Define breakpoints and corresponding slides per view
        0: {
          slidesPerView: 1,
          // spaceBetween: 20,
        },
        521: {
          slidesPerView: 1.3,
          // spaceBetween: 20,
        },
        820: {
          slidesPerView: 2.1,
          // spaceBetween: 20,
        },
      },
      favourites1: [
        {
          id: 1,
          image: img1,
          header: "Tree Runner",
          icon: tree,
          text: "Light and Breezy Sneaker",
        },
        {
          id: 2,
          image: img2,
          header: "Tree Breezer",
          icon: tree,
          text: "Breezy Flat",
        },
        {
          id: 3,
          image: img3,
          header: "Tree Lounger",
          icon: wool,
          text: "Cozy Sneaker",
        },
      ],

      favourites2: [
        {
          id: 1,
          image: img4,
          header: "Tree Dasher 2",
          icon: tree,
          text: "Comfy, Breezy, Everyday Runs",
        },
        {
          id: 2,
          image: img5,
          header: "Golf Dasher",
          icon: tree,
          text: "stabilizing And Comfy For The Green",
        },
        {
          id: 3,
          image: img6,
          header: "Tree Flyer",
          icon: tree,
          text: "Light, Bouncy, Long Distance Runs",
        },
      ],

      favourites3: [
        {
          id: 1,
          image: img7,
          header: "Tree Lounger",
          icon: tree,
          text: "Breezy Slip-On",
        },
        {
          id: 2,
          image: img8,
          header: "Allgood Cotton Tee",
          icon: tree,
          text: "Everyday organic Cotton T-Shirt",
        },
        {
          id: 3,
          image: img9,
          header: "Plant pacer",
          icon: wool,
          text: "Classic Pacer",
        },
      ],

      mobile_data: [
        {
          id: 1,
          image: img1,
          header: "Tree Runner",
          icon: tree,
          text: "Light and Breezy Sneaker",
        },
        {
          id: 2,
          image: img2,
          header: "Tree Breezer",
          icon: tree,
          text: "Breezy Flat",
        },
        {
          id: 3,
          image: img3,
          header: "Tree Lounger",
          icon: wool,
          text: "Cozy Sneaker",
        },
        {
          id: 4,
          image: img4,
          header: "Tree Dasher 2",
          icon: tree,
          text: "Comfy, Breezy, Everyday Runs",
        },
        {
          id: 5,
          image: img5,
          header: "Golf Dasher",
          icon: tree,
          text: "stabilizing And Comfy For The Green",
        },
        {
          id: 6,
          image: img6,
          header: "Tree Flyer",
          icon: tree,
          text: "Light, Bouncy, Long Distance Runs",
        },
        {
          id: 7,
          image: img7,
          header: "Tree Lounger",
          icon: tree,
          text: "Breezy Slip-On",
        },
        {
          id: 8,
          image: img8,
          header: "Allgood Cotton Tee",
          icon: tree,
          text: "Everyday organic Cotton T-Shirt",
        },
        {
          id: 9,
          image: img9,
          header: "Plant pacer",
          icon: wool,
          text: "Classic Pacer",
        },
      ],
    };
  },
};
</script>

<style scoped>
.favorite_section {
  padding: 1rem 3rem;
  background-color: #fefefe;
  /* margin-bottom: 1rem; */
}
.favorite_section h1 {
  text-align: center;
  color: #212a2f;
  font-size: 2rem;
}
.clickable_slide {
  display: flex;
  justify-content: center;
  gap: 10rem;
  margin: 2rem 0;
  border-bottom: 2px solid #d3d4d5;
  padding: 0.5rem 0;
}
.clickable_slide h3 {
  color: #4a4d50;
  cursor: pointer;
  position: relative;
}
.scroll_div {
  display: flex;
  gap: 7rem;
  margin: 0 2rem;
  justify-content: center;
  align-items: center;
  overflow-x: visible;
}
.scroll_div div {
  width: 10rem;
  height: 2px;
  background-color: #000;
  position: relative;
  bottom: 2.1rem;
}

.container {
  display: flex;
  justify-content: space-between;
}
.mobile_view {
  display: none;
}
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
  background-color: #fff;
  box-shadow: rgb(51, 51, 51, 0.5) 5px 0 9px 0px;
  position: relative;
}
.text {
  margin: 0 1rem;
  border-bottom: 2px solid #d3d4d5;
  padding: 0.5rem 0;
}
.para {
  display: flex;
  align-items: center;
  gap: 1.2rem;
  font-size: 15px;
  margin: 1rem;
}
.para img {
  width: 2rem;
}

/* MEDIA QUERY */
@media screen and (max-width: 1300px) {
  .fav_box {
    width: 23rem;
    height: 32rem;
  }
  .img {
    width: 23rem;
    height: 24rem;
  }
  .child-box {
    background-color: rgba(51, 51, 51, 0.5);
    height: 24rem;
  }
}

@media screen and (max-width: 1220px) {
  .fav_box {
    width: 21rem;
    height: 30rem;
  }
  .img {
    width: 21rem;
    height: 22rem;
  }
  .child-box {
    background-color: rgba(51, 51, 51, 0.5);
    height: 22rem;
  }
}

@media screen and (max-width: 1120px) {
  .fav_box {
    width: 19rem;
    height: 27rem;
  }
  .img {
    width: 19rem;
    height: 18rem;
  }
  .child-box {
    background-color: rgba(51, 51, 51, 0.5);
    height: 18rem;
  }
}

@media screen and (min-width: 996px) {
  .child-box {
    background-color: rgba(51, 51, 51, 0.5);
    width: 100%;
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
}

/* MOBILE VIEW */
@media screen and (max-width: 995px) {
  .desktop-view {
    display: none;
  }
  .clickable_slide {
    display: none;
  }
  .scroll_div {
    display: none;
  }
  .mobile_view {
    display: block;
  }
  .favorite_section {
    padding: 0 1rem;
    background-color: #fefefe;
  }
  .favorite_section h1 {
    text-align: center;
    color: #212a2f;
    font-size: 2rem;
    padding: 2rem 0;
  }
  .fav_box {
    width: 22rem;
    height: 33.5rem;
  }
  .img {
    width: 22rem;
    height: 18rem;
  }
  .child-box {
    background: none;
    padding: 0 1rem;
    margin: auto;
    height: max-content;
    width: 100%;
  }
  .child-box .btn-div {
    display: flex;
    flex-direction: column;
    gap: 10px;
    width: 100%;
  }
  .child-box .btn-div #btn {
    width: 100%;
  }

  .slider-navigation {
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    bottom: 20.5rem;
    z-index: 10;
    /* margin: 0 !important; */
  }
  .nav-indicator {
    cursor: pointer;
    /* background-color: rgb(255, 255, 255, 0.85); */
    border-radius: 50%;
    width: max-content;
    height: 5rem;
  }
  .nav-indicator img {
    width: 5rem;
    height: 5rem;
  }
}

@media screen and (max-width: 819px) {
  .favorite_section {
    padding: 0 2rem;
    background-color: #fefefe;
  }
  .fav_box {
    width: 60vw;
    height: 36rem;
  }
  .img {
    width: 60vw;
    height: 20rem;
  }
}
@media screen and (max-width: 520px) {
  .favorite_section {
    padding: 0 1rem;
    background-color: #fefefe;
  }
  .fav_box {
    width: 90vw;
  }
  .img {
    width: 90vw;
  }
}
</style>
