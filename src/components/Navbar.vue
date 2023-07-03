<template>
  <header class="Navbar">
    <div class="ad">
      <p>
        The palm Springs Collecton Is Here. <a href="/">Shop Men</a>|
        <a href="/">Shop Women</a>
      </p>
    </div>
    <nav>
      <div
        id="hamburger"
        @click="toggleMobileNav"
        v-show="mobile"
        :class="{ 'icon-active': mobileNav }"
      >
        menu
      </div>

      <ul class="first_list" v-show="!mobile">
        <li><router-link to="/men">MEN</router-link></li>
        <li><router-link to="/">WOMEN</router-link></li>
        <li><router-link to="/">KIDS</router-link></li>
        <li><router-link to="/">ARRIVALS</router-link></li>
        <li><router-link to="/">SALE</router-link></li>
      </ul>

      <div class="img_div branding">
        <img src="@/assets/allbirds-logo.svg" alt="allbirds" />
      </div>

      <ul class="second_list" v-show="!mobile">
        <li><router-link to="/">SUSTAINABILITY</router-link></li>
        <li><router-link to="/">RERUN</router-link></li>
        <li><router-link to="/">STORES</router-link></li>
        <li>
          <router-link to="/">
            <img src="../assets/serach-icon.svg" alt="search-icon" />
          </router-link>
        </li>
        <li>
          <router-link to="/">
            <!-- <img src="../assets/serach-icon.svg" alt="search-icon" /> -->
          </router-link>
        </li>
        <li>
          <font-awesome-icon :icon="['fas', 'magnifying-glass']" />
        </li>
      </ul>

      <div class="mobile-icons" v-show="mobile">
        <li>
          <router-link to="/">
            <img src="../assets/serach-icon.svg" alt="search-icon" />
          </router-link>
        </li>
      </div>
    </nav>

    <!-- mobile navigation -->
    <transition name="mobile-nav">
      <ul class="dropdown-nav" v-show="mobileNav">
        <li><router-link to="/men">MEN</router-link></li>
        <li><router-link to="/">WOMEN</router-link></li>
        <li><router-link to="/">KIDS</router-link></li>
        <li><router-link to="/">ARRIVALS</router-link></li>
        <li><router-link to="/">SALE</router-link></li>
        <li><router-link to="/">SUSTAINABILITY</router-link></li>
        <li><router-link to="/">RERUN</router-link></li>
        <li><router-link to="/">STORES</router-link></li>
      </ul>
    </transition>
  </header>
</template>

<script>
export default {
  name: "Navbar",
  props: {
    msg: String,
  },
  data() {
    return {
      mobile: false,
      windowWidth: null,
      mobileNav: false,
    };
  },
  methods: {
    toggleMobileNav(mobileNav) {
      this.mobileNav = mobileNav;
    },
  },
};
</script>

<style scoped>
/* nav a.router-link-exact-active {
  color: #42b983;
} */

.Navbar {
  position: fixed;
  width: 100%;
  z-index: 10;
}
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  align-content: center;
  background-color: #fff;
  margin: auto 0;
  padding: 10px;
  overflow-x: scroll;
}
.Navbar::-webkit-scrollbar {
  width: 2rem;
}
nav ul {
  display: flex;
  gap: 2rem;
  margin: 0 20px;
  align-items: center;
  text-align: center;
}
nav ul li {
  list-style: none;
  font-size: 14px;
  font-weight: 400;
}
nav ul li a {
  text-decoration: none;
  color: #212a2f;
}

.img_div {
  width: 7rem;
}
li a img {
  width: 1.2rem;
  height: 1.2rem;
}

/* ad side */
.ad {
  text-align: center;
  background-color: #212a2f;
  color: #fff;
  font-size: 13px;
  padding: 0.7rem;
}
.ad a {
  color: #fff;
  text-decoration: underline;
  margin-right: 5px;
}

/* mobile styling */
#hamburger {
  transition: 0.8s ease all;
}
.icon-active {
  transform: rotate(180deg);
}
.dropdown-nav {
  display: flex;
  flex-direction: column;
  background-color: #fff;
  padding: 10px;
  gap: 2rem;
  width: 100vw;
  height: 100vh;
}
.dropdown-nav li {
  margin-left: 1rem;
  border-bottom: 1px solid #212a2f;
  list-style: none;
}
.dropdown-nav li a {
  color: #212a2f;
  text-decoration: none;
}
</style>
