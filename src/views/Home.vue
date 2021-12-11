<template>
  <div class="home container">
    <section class="hero">
      <div class="hero-content">
        <div class="bg-img">
          <img src="../assets/images/hero_img.jpg" alt="hero image">
        </div>
        <div class="text-content">
          <h1 class="main-text">
            <span>DISCOVER &</span>
            <span>SHOP THE TREND</span>
          </h1>
          <p class="subtext">Discover and shop all trending and quality clothes, shoes, toys and everthing you need for your kids.</p>
          <button class="btn btn-hero">Shop Now</button>
        </div>
        <div class="bottom-info">
          <h1 class="info">275 Shops</h1>
          <h1 class="info">64318 People Served</h1>
          <h1 class="info">64318 Registered Users</h1>
        </div>
      </div>
    </section>
    <section class="process">
      <div class="process-content">
        <h1 class="section-title center">How it works</h1>
        <div class="flex-items">
          <div class="card">
            <div class="icon-wrapper">
              <img src="../assets/images/search-icon.png" alt="search icon" class="search-img">
            </div>
            <h2 class="card-title">Search by address</h2>
            <p class="card-text">Search Shops by your location</p>
          </div>
          <div class="card">
            <div class="icon-wrapper">
              <img src="../assets/images/ellipse.png" class="ellipse" alt="ellipse">
              <img src="../assets/images/store.png" alt="store" class="center-icon">
            </div>
            <h2 class="card-title">Choose a shop</h2>
            <p class="card-text">Choose from our most popular stores.</p>
          </div>
          <div class="card">
            <div class="icon-wrapper">
              <img src="../assets/images/ellipse.png" class="ellipse" alt="ellipse">
              <img src="../assets/images/card.png" alt="store" class="center-icon">
            </div>
            <h2 class="card-title">Pay by card or cash</h2>
            <p class="card-text">Pay your order online easily.</p>
          </div>
          <div class="card">
            <div class="icon-wrapper">
              <img src="../assets/images/ellipse.png" class="ellipse" alt="ellipse">
              <img src="../assets/images/truck.png" alt="store" class="center-icon">
            </div>
            <h2 class="card-title">Clothes Delivery or Takeaway</h2>
            <p class="card-text">Need food delivery? Are you backing home?</p>
          </div>
        </div>
      </div>
    </section>
    <section class="shops">
      <div class="shops-header">
        <h1 class="section-title no-center">Popular Shops</h1>
        <router-link to="/shops">
          <button class="btn btn-section">View all Shops</button>
        </router-link>
      </div>
      <div class="shops-content">
        <div class="shop-flex">
          <div class="shop-card">
            <img src="../assets/images/shop_logo.png" alt="zara logo" class="shop-img">
            <div class="selected-show">
              <div class="show-img">
                <img src="../assets/images/cloth1.png" alt="baby cloth">
              </div>
              <div class="show-img">
                <img src="../assets/images/cloth1.png" alt="baby cloth">
                <router-link to="/" class="view-all">View All</router-link>
              </div>
              <div class="show-img">
                <img src="../assets/images/cloth1.png" alt="baby cloth">
                <router-link to="/" class="view-all">View All</router-link>
              </div>
            </div>
          </div>
          <div class="shop-card">
            <img src="../assets/images/shop_logo.png" alt="zara logo" class="shop-img">
            <div class="selected-show">
              <div class="show-img">
                <img src="../assets/images/cloth1.png" alt="baby cloth">
              </div>
              <div class="show-img">
                <img src="../assets/images/cloth1.png" alt="baby cloth">
                <router-link to="/" class="view-all">View All</router-link>
              </div>
              <div class="show-img">
                <img src="../assets/images/cloth1.png" alt="baby cloth">
                <router-link to="/" class="view-all">View All</router-link>
              </div>
            </div>
          </div>
          <div class="shop-card">
            <img src="../assets/images/shop_logo.png" alt="zara logo" class="shop-img">
            <div class="selected-show">
              <div class="show-img">
                <img src="../assets/images/cloth1.png" alt="baby cloth">
              </div>
              <div class="show-img">
                <img src="../assets/images/cloth1.png" alt="baby cloth">
                <router-link to="/" class="view-all">View All</router-link>
              </div>
              <div class="show-img">
                <img src="../assets/images/cloth1.png" alt="baby cloth">
                <router-link to="/" class="view-all">View All</router-link>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="bottom-link">
        <router-link to="/shops">
          <button class="btn btn-section">View all Shops</button>
        </router-link>
      </div>
    </section>
    <section class="trending">
      <div class="trending-content">
        <div class="trend-header">
          <h1 class="section-title no-center">Trending Baby Products</h1>
          <router-link to="/products">
            <button class="btn btn-section">View all Products</button>
          </router-link>
        </div>
        <div class="items-container">
          <div class="items">
            <Product v-for="(item, idx) in products" :item="item" :key="idx" />
          </div>
        </div>
        <div class="bottom-link">
          <router-link to="/shops">
            <button class="btn btn-section">View all Products</button>
          </router-link>
        </div>
      </div>
    </section>
    <section class="new-arrivals">
      <div class="arrival-content">
        <div class="arrival-header">
          <h1 class="section-title no-center">New Arrival Products</h1>
        </div>
        <div class="arrival-flex">
          <div class="arrived">
            <img src="../assets/images/pillow.png" alt="new product image">
          </div>
          <div class="arrived">
            <img src="../assets/images/pillow.png" alt="new product image">
          </div>
          <div class="arrived">
            <img src="../assets/images/pillow.png" alt="new product image">
          </div>
          <div class="arrived">
            <img src="../assets/images/pillow.png" alt="new product image">
          </div>
        </div>
      </div>
    </section>
    <Footer />
  </div>
</template>

<script>
import '../assets/styles/home.css'
import Product from '../components/Product.vue'
import Footer from '../components/Footer.vue'

export default {
  name: 'Home',
  components: {
    Product,
    Footer
  },
  computed: {
    products() {
      return this.$store.state.products;
    }
  }
}
</script>
