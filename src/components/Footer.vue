<template>
  <section class="footer">
    <div class="footer-header">
      <h1>Want First Dibs?</h1>
      <p>
        Join our email list and be the first to know about new limited edition
        products, material innovations, <br />
        and lots of other fun updates.
      </p>
      <div class="form">
        <input
          type="email"
          placeholder="Enter Your Email Address"
          name="email"
          :v-model="email"
        />

        <Button content="SIGN UP" id="btn" bgcolor="#212a2f" color="#fff" />

        <button>SIGN UP</button>
      </div>

      <p class="policy">
        Note: You can opt-out at any time. See our
        <a href="#">Privacy Policy</a> and <a href="#">Terms</a>.
      </p>
    </div>

    <div class="footer-footer">
      <div class="first-section">
        <div class="help">
          <h4>HELP</h4>
          <p>1-888-963-8944</p>
          <p>1-814-251-9966 (Text)</p>
          <p>help@allbirds.com</p>
          <p>Returns/Exchanges</p>
          <p>FAQ/Contact Us</p>
          <p>Afterpay</p>
        </div>
        <div class="shop">
          <h4>SHOP</h4>
          <p>Men's Shoes</p>
          <p>Women's Shoes</p>
          <p>Men's Apparel</p>
          <p>Women's Apparel</p>
          <p>Socks</p>
          <p>Socks</p>
          <p>Refer a Friend</p>
          <p>Download the Allbirds App</p>
        </div>
        <div class="company">
          <h4>COMPANY</h4>
          <p>Our Stores</p>
          <p>Our Story</p>
          <p>Our Materials</p>
          <p>Sustainability</p>
          <p>Investors</p>
          <p>Shoe Care</p>
          <p>Partnerships</p>
          <p>Product Testing</p>
          <p>Affiliates</p>
          <p>Bulk Orders</p>
          <p>Careers</p>
          <p>Press</p>
          <p>California Transparency Act</p>
          <p>Community Offers</p>
        </div>
        <!-- <div></div>
        <div></div>
        <div></div> -->
      </div>

      <div class="second-section">
        <div class="follow">
          <h4>FOLLOW THE FLOCK</h4>
          <P>
            Exclusive offers, a heads up on new things, and sightings of
            Allbirds in the wild. Oh, we have cute sheep, too. #weareallbirds
          </P>
          <div class="socials-div">
            <img src="@/assets/insta.svg" alt="instagram" />
            <img src="@/assets/twitter2.svg" alt="twitter" />
            <img src="@/assets/fb.svg" alt="facebook" />
            <img src="@/assets/pinterest.svg" alt="pinterest" />
          </div>
        </div>

        <div class="certified">
          <img src="@/assets/corp-logo.svg" alt="icons" />
        </div>

        <div class="flag-div">
          <img src="@/assets/flag1.svg" alt="flag" />
          <img src="@/assets/flag2.svg" alt="flag" />
          <img src="@/assets/flag3.svg" alt="flag" />
          <img src="@/assets/flag4.svg" alt="flag" />
          <img src="@/assets/flag5.svg" alt="flag" />
          <img src="@/assets/flag6.svg" alt="flag" />
          <img src="@/assets/flag7.svg" alt="flag" />
          <img src="@/assets/flag8.svg" alt="flag" />
        </div>
      </div>

      <div class="copyright">
        <p>
          &copy; 2022 Allbirds, Inc. All Rights Reserved. Terms, Privacy &
          Accessibility
        </p>
        <p><a href="#">Do Not Sell My Personal Information</a></p>
      </div>
    </div>
  </section>
</template>

<script>
import Button from "@/Reusables/Button";
export default {
  name: "Footer",
  components: {
    Button,
  },
  data() {
    return {
      email: "",
    };
  },
};
</script>

<style scoped>
.footer-header {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  gap: 2rem;
  background-color: #f8f7f5;
  padding: 2rem 0.5rem;
}
.footer-header .form {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
}
.footer-header .form input {
  height: 3rem;
  padding: 0 1rem;
  width: 30rem;
  border-bottom: 2px solid #212a2f;
  border-top: hidden;
  border-right: hidden;
  border-left: hidden;
}
.footer-header .policy {
  font-size: small;
}
.certified img {
  width: 8rem;
  height: 8rem;
  color: #fff;
  background: #fff;
}
.copyright {
  text-align: center;
  font-size: small;
}
.copyright p {
  margin-bottom: 0.5rem;
}
.copyright a {
  color: #fff;
}
.footer-header .policy a {
  color: #4d5559;
  font-weight: 900;
}
#btn {
  width: "7rem" !important;
}
button {
  width: 30rem;
  height: 3rem;
  padding: 0 1rem;
  font-weight: 545;
  color: #fff;
  font-size: 0.9rem;
  border-radius: 3px;
  transition: background-color 0.1s ease-in-out;
  cursor: pointer;
  border: 5px #fff;
  margin: 0 auto;
  background-color: #212a2f;
  display: none;
}
.footer-footer {
  background-color: #212a2f;
  padding: 4rem 2rem;
  color: #fff;
}
.first-section {
  display: grid;
  /* justify-content: space-between; */
  grid-template-columns: repeat(4, 1fr);
}
.second-section {
  display: grid;
  grid-template-columns: 1fr 1fr 2.8fr;
  gap: 6rem;
  margin: 4rem 0;
}
.flag-div img {
  margin-right: 1.5rem;
}
.first-section p,
.second-section p {
  font-size: small;
  margin: 0.5rem 0;
}
.socials-div {
  display: flex;
  gap: 1.5rem;
}

@media screen and (max-width: 1024px) {
  .first-section,
  .second-section {
    display: flex;
    justify-content: center;
    flex-direction: column;
    text-align: center;
    gap: 3rem;
    margin: 2.2rem 0;
  }
  .socials-div {
    justify-content: center;
    margin-top: 1rem;
  }
}
@media screen and (max-width: 720px) {
  .footer-header .form {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 0.5rem;
  }
  #btn {
    display: none;
  }
  button {
    display: block;
    width: 75vw;
  }
  .footer-header .form input {
    width: 75vw;
  }
}
</style>
