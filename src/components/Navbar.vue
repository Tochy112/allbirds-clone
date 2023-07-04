<template>
  <header class="Navbar">
    <div class="ad" v-show="scrollAd">
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
        <i class="fa-solid fa-bars" style="color: #212a24"></i>
      </div>

      <ul class="first_list" v-show="!mobile">
        <li><router-link to="/men">MEN</router-link></li>
        <li><router-link to="/">WOMEN</router-link></li>
        <li><router-link to="/">KIDS</router-link></li>
        <li><router-link to="/">ARRIVALS</router-link></li>
        <li><router-link to="/" id="sales">SALE</router-link></li>
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
            <i class="fa-solid fa-magnifying-glass" style="color: #212a2f"></i>
          </router-link>
        </li>
        <li>
          <router-link to="/">
            <i class="fa-regular fa-user" style="color: #212a2f"></i>
          </router-link>
        </li>
        <li>
          <router-link to="/">
            <i class="fa-regular fa-circle-question" style="color: #212a2f"></i>
          </router-link>
        </li>
        <li>
          <router-link to="/">
            <i class="fa-solid fa-cart-plus" style="color: #212a2f"></i>
          </router-link>
        </li>
      </ul>

      <div class="mobile-icons" v-show="mobile">
        <li>
          <router-link to="/">
            <i class="fa-solid fa-magnifying-glass" style="color: #212a2f"></i>
          </router-link>
        </li>
        <li>
          <router-link to="/">
            <i class="fa-solid fa-cart-plus" style="color: #212a2f"></i>
          </router-link>
        </li>
      </div>
    </nav>

    <!-- mobile navigation -->
    <transition name="mobile-nav">
      <ul class="dropdown-nav" v-show="mobileNav">
        <li>
          <router-link to="/"> MEN </router-link>
        </li>
        <li><router-link to="/">WOMEN</router-link></li>
        <li><router-link to="/">KIDS</router-link></li>
        <li><router-link to="/">ARRIVALS</router-link></li>
        <li><router-link to="/" id="sales">SALE</router-link></li>
        <li><router-link to="/">SUSTAINABILITY</router-link></li>
        <li><router-link to="/">RERUN</router-link></li>
        <li><router-link to="/">STORES</router-link></li>
        <li><router-link to="/" class="acc">Account</router-link></li>
        <li><router-link to="/" class>Help</router-link></li>
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
      scrollAd: true,
    };
  },
  created() {
    window.addEventListener("resize", this.checkScreen);
    this.checkScreen();

    window.addEventListener("scroll", this.scrollNav);
    this.scrollNav();
  },
  methods: {
    toggleMobileNav() {
      this.mobileNav = !this.mobileNav;
    },
    checkScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 1124) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      this.mobileNav = false;
      return;
    },
    scrollNav() {
      this.scrollAd = window.scrollY;
      if (this.scrollAd >= 200) {
        this.scrollAd = false;
        return;
      }
      this.scrollAd = true;
    },
  },
};
</script>

<style scoped>
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
  font-size: 0.9rem;
  font-weight: 600;
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
#hamburger {
  margin-left: 1rem;
}
i {
  font-size: 24px;
  cursor: pointer;
}

.dropdown-nav {
  display: flex;
  flex-direction: column;
  background-color: #fff;
  padding-top: 1rem;
  gap: 1rem;
  width: 100vw;
  height: 100vh;
  overflow-y: scroll;
}
.dropdown-nav li {
  list-style: none;
  border-bottom: 1px solid rgb(50, 50, 50, 0.4);
  padding-bottom: 1rem;
  font-size: 0.9rem;
  font-weight: 600;
}
.dropdown-nav li a {
  display: flex;
  align-items: center;
}
.mobile-icons {
  display: flex;
  gap: 0.5rem;
  align-items: center;
}
.mobile-icons li {
  list-style: none;
}
.dropdown-nav li a {
  color: #000;
  text-decoration: none;
  margin: 0 0 0 1.5rem;
  width: 100%;
}
#sales {
  color: #ad1f00;
}
.mobile-nav-enter-active,
.mobile-nav-leave-active {
  transition: 1s ease all;
}
.mobile-nav-enter-from {
  height: 0;
}
.mobile-nav-leave-to {
  height: 0;
}
.mobile-nav-enter-to {
  height: 100;
}
</style>
