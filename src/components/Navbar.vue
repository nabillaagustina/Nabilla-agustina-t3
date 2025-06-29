<template>
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
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style scoped>
.navbar {
  backdrop-filter: blur(10px);
  background: rgba(255, 255, 255, 0.95) !important;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.navbar-brand {
  font-weight: 700;
  font-size: 1.5rem;
  color: var(--primary-color) !important;
  transition: all 0.3s ease;
}

.navbar-brand:hover {
  transform: scale(1.05);
}

.nav-link {
  font-weight: 500;
  color: var(--dark-color) !important;
  margin: 0 10px;
  position: relative;
  transition: all 0.3s ease;
}

.nav-link::after {
  content: "";
  position: absolute;
  bottom: -5px;
  left: 50%;
  width: 0;
  height: 2px;
  background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
  transition: all 0.3s ease;
  transform: translateX(-50%);
}

.nav-link:hover::after {
  width: 100%;
}

.nav-link:hover {
  color: var(--primary-color) !important;
  transform: translateY(-2px);
}

.navbar-toggler {
  border: none;
  padding: 0.25rem 0.5rem;
}

.navbar-toggler:focus {
  box-shadow: none;
}

@media (max-width: 991.98px) {
  .navbar-nav {
    text-align: center;
    padding: 1rem 0;
  }

  .nav-link {
    margin: 0.5rem 0;
  }
}
</style>
