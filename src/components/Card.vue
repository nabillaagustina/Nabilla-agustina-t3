<template>
  <div class="card h-100 product-card" :class="{ 'border-success': purchased }">
    <div class="card-img-wrapper">
      <img :src="image" class="card-img-top" :alt="name" />
      <div class="card-overlay">
        <button class="btn btn-sm" :class="purchased ? 'btn-danger' : 'btn-primary'" @click="$emit('toggle-purchase')">
          <i :class="purchased ? 'fas fa-times' : 'fas fa-shopping-cart'" class="me-1"></i>
          {{ purchased ? "Batal" : "Beli" }}
        </button>
      </div>
      <div class="card-badge" v-if="purchased">
        <i class="fas fa-check"></i>
      </div>
    </div>
    <div class="card-body d-flex flex-column">
      <h5 class="card-title">{{ name }}</h5>
      <p class="card-text text-muted">{{ description }}</p>
      <div class="mt-auto">
        <div class="d-flex justify-content-between align-items-center">
          <span class="badge" :class="purchased ? 'bg-success' : 'bg-warning'">
            <i :class="purchased ? 'fas fa-check' : 'fas fa-clock'" class="me-1"></i>
            {{ purchased ? "Terbeli" : "Tersedia" }}
          </span>
          <div class="price-tag">
            <span class="currency">Rp</span>
            <span class="amount">{{ price }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: {
    name: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    image: {
      type: String,
      required: true,
    },
    price: {
      type: String,
      default: "299.000",
    },
    purchased: {
      type: Boolean,
      default: false,
    },
  },
  emits: ["toggle-purchase"],
};
</script>

<style scoped>
.product-card {
  position: relative;
  overflow: hidden;
  border: none;
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  background: var(--white-color);
}

.product-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
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

.card-badge {
  position: absolute;
  top: 15px;
  right: 15px;
  width: 40px;
  height: 40px;
  background: var(--success-color);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 1.2rem;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0% {
    transform: scale(1);
    box-shadow: 0 0 0 0 rgba(16, 185, 129, 0.7);
  }
  70% {
    transform: scale(1.1);
    box-shadow: 0 0 0 10px rgba(16, 185, 129, 0);
  }
  100% {
    transform: scale(1);
    box-shadow: 0 0 0 0 rgba(16, 185, 129, 0);
  }
}

.card-title {
  font-weight: 600;
  color: var(--dark-color);
  margin-bottom: 0.5rem;
}

.card-text {
  font-size: 0.9rem;
  line-height: 1.5;
}

.price-tag {
  display: flex;
  align-items: baseline;
  gap: 2px;
}

.currency {
  font-size: 0.8rem;
  color: var(--gray-color);
  font-weight: 500;
}

.amount {
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--primary-color);
}

.border-success {
  border: 3px solid var(--success-color) !important;
  box-shadow: 0 0 20px rgba(16, 185, 129, 0.3);
}

.badge {
  font-size: 0.75rem;
  padding: 0.5rem 0.75rem;
  border-radius: 20px;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .card-img-top {
    height: 200px;
  }

  .card-badge {
    width: 35px;
    height: 35px;
    font-size: 1rem;
  }

  .amount {
    font-size: 1rem;
  }
}
</style>
