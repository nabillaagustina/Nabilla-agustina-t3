<template>
  <footer class="footer-section">
    <div class="container">
      <div class="row">
        <div class="col-lg-4 col-md-6 mb-4">
          <div class="footer-widget">
            <h5 class="footer-title">
              <i class="fas fa-shopping-bag me-2"></i>
              Nabilla Store
            </h5>
            <p class="footer-description">Toko online terpercaya dengan produk berkualitas tinggi. Kami berkomitmen memberikan pengalaman berbelanja terbaik untuk pelanggan kami.</p>
            <div class="social-links">
              <a href="#" class="social-link" title="Facebook">
                <i class="fab fa-facebook-f"></i>
              </a>
              <a href="#" class="social-link" title="Instagram">
                <i class="fab fa-instagram"></i>
              </a>
              <a href="#" class="social-link" title="Twitter">
                <i class="fab fa-twitter"></i>
              </a>
              <a href="#" class="social-link" title="YouTube">
                <i class="fab fa-youtube"></i>
              </a>
            </div>
          </div>
        </div>

        <div class="col-lg-2 col-md-6 mb-4">
          <div class="footer-widget">
            <h5 class="footer-title">Produk</h5>
            <ul class="footer-links">
              <li>
                <a href="#"><i class="fas fa-angle-right me-2"></i>Elektronik</a>
              </li>
              <li>
                <a href="#"><i class="fas fa-angle-right me-2"></i>Fashion</a>
              </li>
              <li>
                <a href="#"><i class="fas fa-angle-right me-2"></i>Kesehatan</a>
              </li>
              <li>
                <a href="#"><i class="fas fa-angle-right me-2"></i>Olahraga</a>
              </li>
              <li>
                <a href="#"><i class="fas fa-angle-right me-2"></i>Hobi</a>
              </li>
            </ul>
          </div>
        </div>

        <div class="col-lg-3 col-md-6 mb-4">
          <div class="footer-widget">
            <h5 class="footer-title">Layanan</h5>
            <ul class="footer-links">
              <li>
                <a href="#"><i class="fas fa-angle-right me-2"></i>Pengiriman Cepat</a>
              </li>
              <li>
                <a href="#"><i class="fas fa-angle-right me-2"></i>Garansi 100%</a>
              </li>
              <li>
                <a href="#"><i class="fas fa-angle-right me-2"></i>Pembayaran Aman</a>
              </li>
              <li>
                <a href="#"><i class="fas fa-angle-right me-2"></i>Layanan Pelanggan</a>
              </li>
              <li>
                <a href="#"><i class="fas fa-angle-right me-2"></i>Program Loyalitas</a>
              </li>
            </ul>
          </div>
        </div>

        <div class="col-lg-3 col-md-6 mb-4">
          <div class="footer-widget">
            <h5 class="footer-title">Kontak</h5>
            <div class="contact-info">
              <div class="contact-item">
                <i class="fas fa-map-marker-alt"></i>
                <div>
                  <strong>Alamat:</strong><br />
                  Jl. Sudirman No. 123, Jakarta Pusat
                </div>
              </div>
              <div class="contact-item">
                <i class="fas fa-phone"></i>
                <div>
                  <strong>Telepon:</strong><br />
                  +62 812-3456-7890
                </div>
              </div>
              <div class="contact-item">
                <i class="fas fa-envelope"></i>
                <div>
                  <strong>Email:</strong><br />
                  info@nabillastore.com
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <hr class="footer-divider" />

      <div class="row align-items-center">
        <div class="col-md-6">
          <p class="copyright">&copy; 2025 <strong>Nabilla Store</strong>. All Rights Reserved.</p>
        </div>
        <div class="col-md-6">
          <div class="footer-bottom-links">
            <a href="#">Syarat & Ketentuan</a>
            <a href="#">Kebijakan Privasi</a>
            <a href="#">Peta Situs</a>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
.footer-section {
  background: linear-gradient(135deg, var(--dark-color), #374151);
  color: var(--white-color);
  padding: 3rem 0 1rem;
  position: relative;
}

.footer-section::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
}

.footer-title {
  color: var(--white-color);
  font-weight: 600;
  margin-bottom: 1.5rem;
  position: relative;
  padding-bottom: 0.5rem;
}

.footer-title::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 50px;
  height: 2px;
  background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
}

.footer-description {
  color: #d1d5db;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  color: var(--white-color);
  text-decoration: none;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: var(--primary-color);
  color: var(--white-color);
  transform: translateY(-3px);
}

.footer-links {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-links li {
  margin-bottom: 0.75rem;
}

.footer-links a {
  color: #d1d5db;
  text-decoration: none;
  transition: all 0.3s ease;
  display: inline-block;
}

.footer-links a:hover {
  color: var(--primary-color);
  transform: translateX(5px);
}

.contact-info {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.contact-item {
  display: flex;
  align-items: flex-start;
  gap: 0.75rem;
}

.contact-item i {
  color: var(--primary-color);
  font-size: 1.1rem;
  margin-top: 0.25rem;
  min-width: 20px;
}

.contact-item div {
  color: #d1d5db;
  line-height: 1.5;
}

.contact-item strong {
  color: var(--white-color);
}

.footer-divider {
  border-color: rgba(255, 255, 255, 0.1);
  margin: 2rem 0 1rem;
}

.copyright {
  color: #9ca3af;
  margin: 0;
}

.footer-bottom-links {
  display: flex;
  justify-content: flex-end;
  gap: 1.5rem;
}

.footer-bottom-links a {
  color: #9ca3af;
  text-decoration: none;
  font-size: 0.9rem;
  transition: color 0.3s ease;
}

.footer-bottom-links a:hover {
  color: var(--primary-color);
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .footer-section {
    padding: 2rem 0 1rem;
  }

  .footer-bottom-links {
    justify-content: flex-start;
    margin-top: 1rem;
  }

  .social-links {
    justify-content: center;
  }

  .contact-item {
    flex-direction: column;
    text-align: center;
  }

  .contact-item i {
    margin: 0 auto 0.5rem;
  }
}

/* Animation for social links */
.social-link {
  animation: fadeInUp 0.6s ease forwards;
  opacity: 0;
}

.social-link:nth-child(1) {
  animation-delay: 0.1s;
}
.social-link:nth-child(2) {
  animation-delay: 0.2s;
}
.social-link:nth-child(3) {
  animation-delay: 0.3s;
}
.social-link:nth-child(4) {
  animation-delay: 0.4s;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
