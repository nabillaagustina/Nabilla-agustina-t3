<template>
  <div>
    <nav class="navbar navbar-expand-lg fixed-top">
      <div class="container">
        <a class="navbar-brand" href="#">
          <i class="fas fa-shopping-bag me-2"></i>
          Nabilla Store
        </a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item">
              <a class="nav-link" href="#home">Beranda</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#products">Produk</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#about">Tentang</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#contact">Kontak</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <section id="home" class="hero-section">
      <div class="container">
        <div class="row align-items-center min-vh-100">
          <div class="col-lg-6 fade-in">
            <h1 class="hero-title">Selamat Datang di Nabilla Store</h1>
            <p class="hero-subtitle">Temukan produk-produk berkualitas dengan harga terbaik. Kami menyediakan berbagai macam produk untuk memenuhi kebutuhan Anda.</p>
            <div class="hero-buttons">
              <a href="#products" class="btn btn-primary btn-lg me-3">
                <i class="fas fa-shopping-cart me-2"></i>
                Belanja Sekarang
              </a>
              <a href="#about" class="btn btn-outline-primary btn-lg">
                <i class="fas fa-info-circle me-2"></i>
                Pelajari Lebih Lanjut
              </a>
            </div>
          </div>
          <div class="col-lg-6 slide-in">
            <div class="hero-image">
              <img src="https://images.unsplash.com/photo-1441986300917-64674bd600d8?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Shopping" class="img-fluid rounded-4 shadow-lg" />
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="py-5">
      <div class="container">
        <div class="row">
          <div class="col-12">
            <h2 class="text-center mb-5">
              <i class="fas fa-star text-warning me-2"></i>
              Produk Unggulan
            </h2>
          </div>
        </div>
        <div id="productCarousel" class="carousel slide" data-bs-ride="carousel">
          <div class="carousel-inner">
            <div v-for="(product, index) in products" :key="index" class="carousel-item" :class="{ active: index === 0 }">
              <img :src="getImage(product.image)" class="d-block w-100" :alt="product.name" />
              <div class="carousel-caption">
                <h3>{{ product.name }}</h3>
                <p>{{ product.desc }}</p>
              </div>
            </div>
          </div>
          <button class="carousel-control-prev" type="button" data-bs-target="#productCarousel" data-bs-slide="prev">
            <span class="carousel-control-prev-icon"></span>
          </button>
          <button class="carousel-control-next" type="button" data-bs-target="#productCarousel" data-bs-slide="next">
            <span class="carousel-control-next-icon"></span>
          </button>
        </div>
      </div>
    </section>

    <section id="products" class="py-5 bg-light">
      <div class="container">
        <div class="row">
          <div class="col-12">
            <h2 class="text-center mb-5">
              <i class="fas fa-box-open text-primary me-2"></i>
              Katalog Produk
            </h2>
          </div>
        </div>
        <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4 g-4">
          <div class="col" v-for="(product, index) in products" :key="index">
            <div class="card h-100 product-card" :class="{ 'border-success': product.purchased }">
              <div class="card-img-wrapper">
                <img :src="getImage(product.image)" class="card-img-top" :alt="product.name" />
                <div class="card-overlay">
                  <button class="btn btn-sm" :class="product.purchased ? 'btn-danger' : 'btn-primary'" @click="togglePurchase(index)">
                    <i :class="product.purchased ? 'fas fa-times' : 'fas fa-shopping-cart'" class="me-1"></i>
                    {{ product.purchased ? "Batal" : "Beli" }}
                  </button>
                </div>
              </div>
              <div class="card-body d-flex flex-column">
                <h5 class="card-title">{{ product.name }}</h5>
                <p class="card-text text-muted">{{ product.desc }}</p>
                <div class="mt-auto">
                  <div class="d-flex justify-content-between align-items-center">
                    <span class="badge bg-success" v-if="product.purchased">
                      <i class="fas fa-check me-1"></i>
                      Terbeli
                    </span>
                    <span class="badge bg-warning" v-else>
                      <i class="fas fa-clock me-1"></i>
                      Tersedia
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="about" class="py-5">
      <div class="container">
        <div class="row align-items-center">
          <div class="col-lg-6">
            <h2 class="mb-4">
              <i class="fas fa-store text-primary me-2"></i>
              Tentang Nabilla Store
            </h2>
            <p class="lead mb-4">Kami adalah toko online terpercaya yang menyediakan berbagai produk berkualitas dengan harga yang terjangkau.</p>
            <div class="row">
              <div class="col-6">
                <div class="feature-item text-center mb-4">
                  <i class="fas fa-shipping-fast fa-2x text-primary mb-3"></i>
                  <h5>Pengiriman Cepat</h5>
                  <p class="text-muted">Layanan pengiriman yang cepat dan aman</p>
                </div>
              </div>
              <div class="col-6">
                <div class="feature-item text-center mb-4">
                  <i class="fas fa-shield-alt fa-2x text-success mb-3"></i>
                  <h5>Garansi 100%</h5>
                  <p class="text-muted">Garansi uang kembali jika tidak puas</p>
                </div>
              </div>
            </div>
          </div>
          <div class="col-lg-6">
            <img src="https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="About Us" class="img-fluid rounded-4 shadow-lg" />
          </div>
        </div>
      </div>
    </section>

    <footer class="text-center">
      <div class="container">
        <div class="row">
          <div class="col-md-4">
            <h5 class="mb-3">
              <i class="fas fa-shopping-bag me-2"></i>
              Nabilla Store
            </h5>
            <p>Toko online terpercaya dengan produk berkualitas</p>
          </div>
          <div class="col-md-4">
            <h5 class="mb-3">Kontak</h5>
            <p>
              <i class="fas fa-envelope me-2"></i>
              info@nabillastore.com<br />
              <i class="fas fa-phone me-2"></i>
              +62 812-3456-7890
            </p>
          </div>
          <div class="col-md-4">
            <h5 class="mb-3">Ikuti Kami</h5>
            <div class="social-links">
              <a href="#" class="me-3"><i class="fab fa-facebook fa-lg"></i></a>
              <a href="#" class="me-3"><i class="fab fa-instagram fa-lg"></i></a>
              <a href="#" class="me-3"><i class="fab fa-twitter fa-lg"></i></a>
              <a href="#"><i class="fab fa-youtube fa-lg"></i></a>
            </div>
          </div>
        </div>
        <hr class="my-4" />
        <p>&copy; 2025 Nabilla Store. All Rights Reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      products: [
        { name: "Botol Hijau", desc: "Botol minum ramah lingkungan dengan desain modern.", image: "botol.jpg", purchased: false },
        { name: "Kacamata Hitam", desc: "Kacamata gaya Ray-Ban dengan kualitas premium.", image: "kacamata.jpg", purchased: false },
        { name: "Parfum Chanel", desc: "Parfum elegan untuk wanita modern dengan aroma yang memikat.", image: "parfum.jpg", purchased: false },
        { name: "Headphone Wireless", desc: "Headphone wireless dengan kualitas suara tinggi dan baterai tahan lama.", image: "headphone.jpg", purchased: false },
      ],
    };
  },
  methods: {
    getImage(fileName) {
      return new URL(`./assets/${fileName}`, import.meta.url).href;
    },
    togglePurchase(index) {
      this.products[index].purchased = !this.products[index].purchased;
    },
  },
};
</script>

<style scoped>
.hero-section {
  background: linear-gradient(135deg, rgba(99, 102, 241, 0.1) 0%, rgba(139, 92, 246, 0.1) 100%);
  padding-top: 80px;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 700;
  background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 1.5rem;
}

.hero-subtitle {
  font-size: 1.2rem;
  color: var(--gray-color);
  margin-bottom: 2rem;
  line-height: 1.8;
}

.hero-buttons {
  margin-bottom: 2rem;
}

.hero-image img {
  transition: transform 0.3s ease;
}

.hero-image img:hover {
  transform: scale(1.05);
}

.carousel-caption {
  background: rgba(0, 0, 0, 0.7);
  border-radius: 15px;
  padding: 20px;
  bottom: 30px;
}

.product-card {
  position: relative;
  overflow: hidden;
}

.card-img-wrapper {
  position: relative;
  overflow: hidden;
}

.card-img-top {
  height: 250px;
  width: 100%;
  object-fit: cover;
  object-position: center;
  transition: transform 0.3s ease;
}

.card-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.product-card:hover .card-overlay {
  opacity: 1;
}

.product-card:hover .card-img-top {
  transform: scale(1.1);
}

.border-success {
  border: 3px solid var(--success-color) !important;
  box-shadow: 0 0 20px rgba(16, 185, 129, 0.3);
}

.feature-item {
  padding: 20px;
  border-radius: 15px;
  background: var(--white-color);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.feature-item:hover {
  transform: translateY(-5px);
}

.social-links a {
  color: var(--white-color);
  transition: all 0.3s ease;
}

.social-links a:hover {
  color: var(--primary-color);
  transform: translateY(-3px);
}

.btn-outline-primary {
  border: 2px solid var(--primary-color);
  color: var(--primary-color);
  background: transparent;
}

.btn-outline-primary:hover {
  background: var(--primary-color);
  color: var(--white-color);
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 2.5rem;
  }

  .hero-subtitle {
    font-size: 1rem;
  }

  .hero-buttons .btn {
    display: block;
    width: 100%;
    margin-bottom: 1rem;
  }

  .carousel-caption {
    bottom: 10px;
    padding: 15px;
  }

  .carousel-caption h3 {
    font-size: 1.2rem;
  }

  .carousel-caption p {
    font-size: 0.9rem;
  }
}

html {
  scroll-behavior: smooth;
}

.fade-in {
  animation-delay: 0.2s;
}

.slide-in {
  animation-delay: 0.4s;
}
</style>
