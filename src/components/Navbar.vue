<template>
  <div class="Navbar">
    <div class="ad">
      <p>
        The palm Springs Collecton Is Here. <a href="/">Shop Men</a>|
        <a href="/">Shop Women</a>
      </p>
    </div>
    <nav>
      <ul class="first_list">
        <li><router-link to="/men">MEN</router-link></li>
        <li><router-link to="/">WOMEN</router-link></li>
        <li><router-link to="/">KIDS</router-link></li>
        <li><router-link to="/">ARRIVALS</router-link></li>
        <li><router-link to="/">SALE</router-link></li>
      </ul>
      <div class="img_div">
        <img src="@/assets/allbirds-logo.svg" alt="allbirds" />
      </div>
      <ul class="second_list">
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
    </nav>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
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
</style>
