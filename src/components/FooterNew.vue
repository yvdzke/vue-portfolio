<template>
  <footer class="footer-section text-center text-white py-5 position-relative">
    <!-- Scroll to top button -->
    <div
      class="scroll-top-btn position-absolute start-50 translate-middle bg-white d-flex align-items-center justify-content-center"
      @click="scrollToTop"
    >
      <i class="bi bi-chevron-up text-dark fs-5"></i>
    </div>

    <!-- Social icons -->
    <div class="d-flex justify-content-center gap-4 mb-3" style="padding-top: 30px">
      <a href="https://github.com/yvdzke" target="_blank" class="social-icon">
        <iconify-icon icon="mdi:github" width="28" height="28"></iconify-icon>
      </a>
      <a href="https://www.linkedin.com/in/yvdzpradana/" target="_blank" class="social-icon">
        <iconify-icon icon="mdi:linkedin" width="28" height="28"></iconify-icon>
      </a>
      <a href="https://www.instagram.com/yvdzke/" target="_blank" class="social-icon">
        <iconify-icon icon="mdi:instagram" width="28" height="28"></iconify-icon>
      </a>
    </div>

    <!-- Copyright -->
    <small class="text-light d-block mt-2">&copy; Copyright 2025 Yuda Pradana</small>
  </footer>
</template>

<script>
export default {
  name: 'FooterComponent',
  methods: {
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: 'smooth' })
    }
  }
}
</script>

<style scoped>
.footer-section {
  background-color: #0d0d0d;
  border-top: 1px solid rgba(255, 255, 255, 0.05);
  position: relative;
}

.scroll-top-btn {
  top: 0;
  transform: translate(-50%, -50%);
  width: 48px;
  height: 48px;
  border-radius: 50%;
  cursor: pointer;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.4);
  transition:
    transform 0.3s ease,
    box-shadow 0.3s ease;
}

.scroll-top-btn:hover {
  transform: translate(-50%, -50%) scale(1.1);
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.5);
}

.social-icon {
  color: white;
  width: 45px;
  height: 45px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.5s ease;
  position: relative;
  z-index: 2;
}

.social-icon:hover {
  transform: rotate(360deg);
  background: rgba(168, 85, 247, 0.2);
}
</style>
