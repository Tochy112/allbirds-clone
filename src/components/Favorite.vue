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
                <Button content="SHOP MEN" />
                <Button content="SHOP WOMEN" />
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
                <Button content="SHOP MEN" />
                <Button content="SHOP WOMEN" />
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

            <div class="child-box">
              <div class="btn-div">
                <Button content="SHOP MEN" />
                <Button content="SHOP WOMEN" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Button from "@/Reusables/Button.vue";
import img1 from "@/assets/favourite1.avif";
import img2 from "@/assets/favourite2.avif";
import img3 from "@/assets/favourite3.avif";
import img4 from "@/assets/favourite4.avif";
import img5 from "@/assets/favourite5.avif";
import img6 from "@/assets/favourite6.avif";
import img7 from "@/assets/favourite7.avif";
import img8 from "@/assets/favourite8.avif";
import img9 from "@/assets/favourite9.avif";
import tree from "@/assets/Tree.jpg";
import wool from "@/assets/Wool.jpg";

export default {
  name: "Favorite",
  components: {
    Button,
  },
  data() {
    return {
      activePort: "firstSet",
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
          header: "Wool Runner",
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
    };
  },
};
</script>

<style scoped>
.favorite_section {
  padding: 3rem;
  background-color: #fefefe;
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
  /* background-color: red; */
  /* padding: 1rem; */
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

/* media query */
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
    width: 23rem;
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
    width: 21rem;
    height: 22rem;
  }
}

@media screen and (max-width: 1120px) {
  .fav_box {
    width: 18.5rem;
    height: 28rem;
  }
  .img {
    width: 18.5rem;
    height: 20rem;
  }
  .child-box {
    background-color: rgba(51, 51, 51, 0.5);
    width: 18.5rem;
    height: 20rem;
  }
}

/* mobile view */
@media screen and (max-width: 995px) {
  .desktop-view {
    display: none;
  }
}
</style>
