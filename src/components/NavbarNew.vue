<template>
  <nav class="navbar fixed-top navbar-expand-lg glass-nav px-4 py-2 mx-auto">
    <div class="container-fluid px-3">
      <!-- Brand -->
      <a class="navbar-brand gradient-logo fw-bold me-auto" href="#home">KE</a>

      <!-- Toggle button for mobile -->
      <!-- Toggle button hanya muncul di mobile -->
      <button class="custom-toggler d-lg-none" type="button" @click="toggleMenu">
        <span :class="['line', { open: isMenuOpen, top: true }]"></span>
        <span :class="['line', { open: isMenuOpen, middle: true }]"></span>
        <span :class="['line', { open: isMenuOpen, bottom: true }]"></span>
      </button>

      <!-- Links -->
      <div
        class="collapse navbar-collapse"
        :class="{ show: isMenuOpen, 'menu-center': isMenuOpen }"
      >
        <ul class="navbar-nav ms-lg-auto">
          <li
            class="nav-item fade-link"
            v-for="(link, index) in links"
            :key="link.id"
            :style="{ transitionDelay: isMenuOpen ? index * 0.1 + 's' : '0s' }"
          >
            <a
              class="nav-link"
              :class="{ active: activeSection === link.id }"
              :href="`#${link.id}`"
              @click="closeMenu"
              >{{ link.name }}</a
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'NavbarNew',
  data() {
    return {
      activeSection: 'home',
      isMenuOpen: false,
      links: [
        { id: 'home', name: 'Home' },
        { id: 'about', name: 'About' },
        { id: 'my-journey', name: 'Journey' },
        { id: 'project', name: 'Project' }
      ]
    }
  },
  mounted() {
    this.observeSections()
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    },
    closeMenu() {
      this.isMenuOpen = false
    },
    observeSections() {
      const sections = document.querySelectorAll('section[id]')
      const observer = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              this.activeSection = entry.target.id
            }
          })
        },
        { threshold: 0.6 }
      )
      sections.forEach((section) => observer.observe(section))
    }
  }
}
</script>

<style scoped>
.glass-nav {
  width: calc(100% - 40px);
  margin: 12px auto 0 auto;
  /* kurangi jarak dari atas */
  border-radius: 2rem;
  /* lebih ramping, bukan 2rem */
  background: rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(15px);
  padding-top: 0.15rem !important;
  /* kurangi tinggi atas */
  padding-bottom: 0.15rem !important;
  /* kurangi tinggi bawah */
  transition:
    background 0.3s ease,
    box-shadow 0.3s ease;
  z-index: 1030;
}

/* Brand gradient animated */
.gradient-logo {
  font-size: 1.5rem;
  background: linear-gradient(270deg, #a855f7, #3b82f6, #22d3ee, #a855f7);
  background-size: 800% 800%;
  -webkit-background-clip: text;
  color: transparent;
  animation: gradientShift 6s ease infinite;
}

@keyframes gradientShift {
  0% {
    background-position: 0% 50%;
  }

  50% {
    background-position: 100% 50%;
  }

  100% {
    background-position: 0% 50%;
  }
}

/* Hamburger */
.custom-toggler {
  width: 38px;
  height: 38px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border: none;
  gap: 6px;
  transition: background 0.3s ease;
}

/* Pastikan hamburger hanya muncul di mobile */
.custom-toggler.d-lg-none {
  display: flex !important;
}

@media (min-width: 992px) {
  .custom-toggler.d-lg-none {
    display: none !important;
  }

  /* Desktop menu tanpa animasi collapse */
  .collapse.navbar-collapse {
    max-height: none !important;
    opacity: 1 !important;
    transform: none !important;
    overflow: visible !important;
  }

  .fade-link {
    opacity: 1 !important;
    transform: none !important;
    transition: none !important;
  }

  .navbar-nav {
    margin: 0 auto;
    display: flex;
    gap: 2rem;
  }
}

.custom-toggler:hover {
  background: rgba(255, 255, 255, 0.3);
}

.line {
  width: 22px;
  height: 2px;
  background: white;
  border-radius: 2px;
  transition: all 0.4s ease;
}

.line.top.open {
  transform: rotate(45deg) translate(5px, 5px);
}

.line.middle.open {
  opacity: 0;
}

.line.bottom.open {
  transform: rotate(-45deg) translate(5px, -5px);
}

/* Menu tengah saat terbuka */
.menu-center .navbar-nav {
  flex-direction: column !important;
  text-align: center;
  width: 100%;
}

/* Animasi link */
.fade-link {
  opacity: 0;
  transform: translateY(10px);
  transition:
    opacity 0.4s ease,
    transform 0.4s ease;
}

.menu-center .fade-link {
  opacity: 1;
  transform: translateY(0);
}

/* Nav link style */
.nav-link {
  color: #c084fc !important;
  font-weight: 500;
  border-radius: 50px;
  padding: 0.4rem 1rem;
  transition:
    color 0.3s ease,
    background 0.3s ease;
}

.nav-link:hover {
  color: #e9d5ff !important;
}

.nav-link.active {
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(20px);
  color: #fff !important;
  font-weight: 600;
}

/* ===== Smooth spring-like animation for menu ===== */
.collapse.navbar-collapse {
  max-height: 0;
  overflow: hidden;
  opacity: 0;
  transform: translateY(-15px);
  transition:
    max-height 0.5s cubic-bezier(0.22, 1, 0.36, 1),
    opacity 0.4s ease,
    transform 0.5s cubic-bezier(0.22, 1, 0.36, 1);
}

.collapse.navbar-collapse.show {
  max-height: 500px;
  /* adjust for menu content */
  opacity: 1;
  transform: translateY(0);
}
</style>
