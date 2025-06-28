<template>
  <div>
    <!-- Navbar -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Toko Online</a>
      </div>
    </nav>

    <!-- Carousel -->
    <div id="productCarousel" class="carousel slide mt-5" data-bs-ride="carousel">
      <div class="carousel-inner">
        <div
          v-for="(product, index) in products"
          :key="index"
          class="carousel-item"
          :class="{ active: index === 0 }"
        >
          <img :src="getImage(product.image)" class="d-block w-100" :alt="product.name" />
        </div>
      </div>
      <button class="carousel-control-prev" type="button" data-bs-target="#productCarousel" data-bs-slide="prev">
        <span class="carousel-control-prev-icon"></span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#productCarousel" data-bs-slide="next">
        <span class="carousel-control-next-icon"></span>
      </button>
    </div>

    <!-- Cards -->
    <div class="container mt-5">
      <div class="row row-cols-1 row-cols-md-4 g-4">
        <div class="col" v-for="(product, index) in products" :key="index">
          <div class="card h-100" :class="{ 'border-success': product.purchased }">
            <img :src="getImage(product.image)" class="card-img-top" :alt="product.name" />
            <div class="card-body d-flex flex-column">
              <h5 class="card-title">{{ product.name }}</h5>
              <p class="card-text">{{ product.desc }}</p>
              <button
                class="btn mt-auto"
                :class="product.purchased ? 'btn-danger' : 'btn-primary'"
                @click="togglePurchase(index)"
              >
                {{ product.purchased ? 'Batal Beli' : 'Beli' }}
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Footer -->
    <footer class="bg-dark text-white text-center p-4 mt-5">
      <p>&copy; 2025 Toko Online. All Rights Reserved.</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      products: [
        { name: 'Botol Hijau', desc: 'Botol minum ramah lingkungan.', image: 'botol.jpg', purchased: false },
        { name: 'Kacamata Hitam', desc: 'Kacamata gaya Ray-Ban.', image: 'kacamata.jpg', purchased: false },
        { name: 'Parfum Chanel', desc: 'Parfum elegan untuk wanita modern.', image: 'parfum.jpg', purchased: false },
        { name: 'Headphone', desc: 'Headphone wireless kualitas tinggi.', image: 'headphone.jpg', purchased: false }
      ]
    };
  },
  methods: {
    getImage(fileName) {
      return new URL(`./assets/${fileName}`, import.meta.url).href;
    },
    togglePurchase(index) {
      this.products[index].purchased = !this.products[index].purchased;
    }
  }
};
</script>


<style scoped>
body {
  padding-top: 56px;
}
.card-img-top {
  height: 300px;
  object-fit: cover;
}
.border-success {
  border: 2px solid #28a745 !important;
}
</style>
