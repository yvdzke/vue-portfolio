<template>
  <Navbar />

  <!-- Section Home -->
  <section
    id="home"
    class="vh-100 d-flex flex-column justify-content-center align-items-center text-center text-white position-relative"
  >
    <!-- Background -->
    <div class="background-dark"></div>

    <!-- Gambar samar dengan potongan diagonal -->
    <img :src="Saya" alt="Saya" class="bg-saya-diagonal" />

    <div class="content d-flex flex-column justify-content-center align-items-center h-100">
      <h1 class="display-1 fw-bold text-gradient home-anim">HELLO!</h1>

      <h5 class="tagline mt-4 mb-4 home-anim">
        <span class="tag-white">I am a</span>
        <span class="tag-gradient"> Fullstack Web Developer</span>
      </h5>

      <p class="desc-text mx-auto mb-5 home-anim py-5">
        Graduated Full-Stack Web Developer bootcamp program from harisenin.com for deepening skills
        in Web Developer. Explore my latest projects, showcasing my expertise in web development.
      </p>

      <div class="d-flex gap-3 mt-3 home-anim">
        <button
          class="btn-view-more d-flex align-items-center gap-2 mb-5 home-anim"
          @mouseenter="hoverIcon = true"
          @mouseleave="hoverIcon = false"
          @click="scrollToAbout"
        >
          View More
          <iconify-icon
            icon="formkit:arrowdown"
            width="26"
            height="26"
            :class="{ rotated: hoverIcon }"
          />
        </button>

        <a
          href="https://discord.gg/ZWmGSYYHuP"
          target="_blank"
          class="btn-discord d-flex align-items-center gap-2 mb-5 home-anim"
          @mouseenter="discordHover = true"
          @mouseleave="discordHover = false"
        >
          My Forum
          <iconify-icon
            icon="ic:baseline-discord"
            width="26"
            height="26"
            :class="{ 'rotate-once': discordHover }"
          />
        </a>
      </div>

      <div
        class="scroll-indicator mt-5 pt-4 home-anim justify-content-center"
        @click="scrollToAbout"
      >
        <div class="pill">
          <div class="dot"></div>
        </div>
        <small class="mt-2 text-light">SCROLL</small>
      </div>
    </div>
  </section>

  <!-- Section About -->
  <section id="about" class="about-section min-vh-100 px-3 text-white">
    <div class="container pt-5">
      <h2 class="text-gradient text-center fw-bold mb-3">About Me ✨</h2>
      <p class="text-center mb-5">Sekilas tentang saya</p>

      <div class="row align-items-start responsive-abt">
        <!-- LEFT: Deskripsi + Stats -->
        <div class="col-lg-7 mb-5">
          <h3 class="fw-bold">YUDA PRADANA</h3>
          <p class="text-purple">Fullstack Web Developer</p>
          <div class="d-flex gap-3 mt-3 home-anim">
            <a href="https://github.com/yvdzke" target="_blank" class="social-icon">
              <iconify-icon icon="mdi:github" width="28" height="28"></iconify-icon>
            </a>
            <a
              href="https://www.linkedin.com/in/yuda-pradana-8243182a3/"
              target="_blank"
              class="social-icon"
            >
              <iconify-icon icon="mdi:linkedin" width="28" height="28"></iconify-icon>
            </a>
            <a href="https://www.instagram.com/yvdzke/" target="_blank" class="social-icon">
              <iconify-icon icon="mdi:instagram" width="28" height="28"></iconify-icon>
            </a>
          </div>

          <p>
            I started my journey as a video editor, which unexpectedly sparked my interest in the
            world of technology and problem-solving through software development.
          </p>
          <p>
            Now, I focus on creating efficient and scalable web applications using modern
            technologies like Vue, React, and Node.js, always striving for clean code and great user
            experiences.
          </p>

          <!-- STATS -->
          <!-- <div class="d-flex gap-3 mt-4 flex-wrap">
            <div class="stat-box text-center flex-fill">
              <h4 class="fw-bold">2+</h4>
              <p class="mb-0">Years</p>
            </div>
            <div class="stat-box text-center flex-fill">
              <h4 class="fw-bold">20+</h4>
              <p class="mb-0">Projects</p>
            </div>
            <div class="stat-box text-center flex-fill">
              <h4 class="fw-bold">5+</h4>
              <p class="mb-0">Clients</p>
            </div>
          </div> -->
        </div>

        <!-- right -->

        <div class="col-lg-5">
          <div class="d-flex align-items-center gap-2 mb-3 pb-4 tk-skills">
            <iconify-icon icon="material-symbols:code" width="28" height="28"></iconify-icon>
            <h2 class="fw-bold mb-0">Technical Skills</h2>
          </div>

          <div class="accordion accordion-flush" id="techAccordion">
            <!-- UI Frameworks & Libraries -->
            <div class="accordion-item skill-category">
              <h2 class="accordion-header">
                <button
                  class="accordion-button collapsed"
                  type="button"
                  data-bs-toggle="collapse"
                  data-bs-target="#flush-ui"
                  aria-expanded="false"
                >
                  <iconify-icon icon="bx:layer" width="28" height="28"></iconify-icon>&nbsp;
                  Frameworks
                </button>
              </h2>
              <div
                id="flush-ui"
                class="accordion-collapse collapse"
                data-bs-parent="#techAccordion"
              >
                <div class="accordion-body d-flex flex-wrap gap-3">
                  <!-- Vue -->
                  <div class="skill-card border-gradient-green">
                    <img
                      src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg"
                      width="32"
                    />
                    <div>
                      <strong>Vue</strong>
                    </div>
                  </div>
                  <!-- ReactJs -->
                  <div class="skill-card border-gradient-cyan">
                    <img
                      src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/1200px-React-icon.svg.png"
                      width="32"
                    />
                    <div>
                      <strong>React</strong>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <!-- Languages -->
            <div class="accordion-item skill-category">
              <h2 class="accordion-header">
                <button
                  class="accordion-button collapsed"
                  type="button"
                  data-bs-toggle="collapse"
                  data-bs-target="#flush-lang"
                  aria-expanded="false"
                >
                  <iconify-icon icon="ooui:code" width="28" height="28"></iconify-icon>&nbsp;
                  Languages
                </button>
              </h2>
              <div
                id="flush-lang"
                class="accordion-collapse collapse"
                data-bs-parent="#techAccordion"
              >
                <div class="accordion-body d-flex flex-wrap gap-3">
                  <div class="skill-card border-gradient-yellow">
                    <img
                      src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg"
                      width="32"
                    />
                    <div>
                      <strong>JavaScript</strong>
                    </div>
                  </div>
                  <!-- <div class="skill-card border-gradient-bluepk">
                    <img
                      src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/27/PHP-logo.svg/1422px-PHP-logo.svg.png?20180502235434"
                      width="32"
                    />
                    <div>
                      <strong>PHP</strong>
                    </div>
                  </div> -->
                  <div class="skill-card border-gradient-blue">
                    <img
                      src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg"
                      width="32"
                    />
                    <div>
                      <strong>TypeScript</strong>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <!-- Design -->
            <div class="accordion-item skill-category">
              <h2 class="accordion-header">
                <button
                  class="accordion-button collapsed"
                  type="button"
                  data-bs-toggle="collapse"
                  data-bs-target="#flush-design"
                  aria-expanded="false"
                >
                  <iconify-icon
                    icon="fluent:design-ideas-20-regular"
                    width="28"
                    height="28"
                  ></iconify-icon
                  >&nbsp; Design
                </button>
              </h2>
              <div
                id="flush-design"
                class="accordion-collapse collapse"
                data-bs-parent="#techAccordion"
              >
                <div class="accordion-body d-flex flex-wrap gap-3">
                  <div class="skill-card border-gradient-pink">
                    <img
                      src="https://upload.wikimedia.org/wikipedia/commons/d/d5/Tailwind_CSS_Logo.svg"
                      width="32"
                    />
                    <div>
                      <strong>Tailwind</strong>
                    </div>
                  </div>
                  <div class="skill-card border-gradient-indigo">
                    <img
                      src="https://upload.wikimedia.org/wikipedia/commons/b/b2/Bootstrap_logo.svg"
                      width="32"
                    />
                    <div>
                      <strong>Bootstrap</strong>
                    </div>
                  </div>
                  <div class="skill-card border-gradient-red">
                    <img
                      src="https://res.cloudinary.com/dvym5vxsw/image/upload/v1767849481/20260108_120856_xwpbyv.png"
                      width="32"
                    />
                    <div>
                      <strong>Figma</strong>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <!-- Tools -->
            <div class="accordion-item skill-category">
              <h2 class="accordion-header">
                <button
                  class="accordion-button collapsed"
                  type="button"
                  data-bs-toggle="collapse"
                  data-bs-target="#flush-tools"
                  aria-expanded="false"
                >
                  <iconify-icon icon="mdi:tools" width="28" height="28"></iconify-icon>&nbsp; Tools
                </button>
              </h2>
              <div
                id="flush-tools"
                class="accordion-collapse collapse"
                data-bs-parent="#techAccordion"
              >
                <div class="accordion-body d-flex flex-wrap gap-3">
                  <div class="skill-card border-gradient-gray">
                    <img
                      src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg"
                      width="32"
                    />
                    <div>
                      <strong>Git</strong>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Section My Journey -->
  <section id="my-journey" class="my-journey-section">
    <div class="container pt-5">
      <!-- Title -->
      <h2 class="text-gradient text-center fw-bold mb-3">My Journey</h2>
      <p class="text-center mb-5">Sedikit perjalanan karir dan pendidikan saya</p>

      <!-- Toggle Pills (Bootstrap) -->
      <div class="row mb-5">
        <div class="col text-center">
          <div class="btn-group">
            <button
              type="button"
              class="btn journey-btn"
              :class="selectedTab === 'career' ? 'btn-fill' : 'btn-outline'"
              @click="switchTab('career')"
            >
              Career
            </button>
            <button
              type="button"
              class="btn journey-btn"
              :class="selectedTab === 'education' ? 'btn-fill' : 'btn-outline'"
              @click="switchTab('education')"
            >
              Education
            </button>
          </div>
        </div>
      </div>

      <!-- Timeline -->
      <div ref="timelineWrapper">
        <v-timeline v-if="selectedTab === 'education'" class="custom-timeline" side="start">
          <v-timeline-item
            v-for="(edu, i) in education"
            :key="`edu-${i}`"
            dot-color="transparent"
            class="custom-timeline-item timeline-anim"
          >
            <template v-slot:icon>
              <div class="custom-dot" :style="{ borderColor: edu.color }"></div>
            </template>
            <div class="timeline-content">
              <span class="year-label" :style="{ color: edu.color }">{{ edu.year }}</span>
              <h5 class="item-title">{{ edu.school }}</h5>
              <p class="item-subtitle">{{ edu.degree }}</p>
              <p class="item-desc">{{ edu.desc }}</p>
            </div>
          </v-timeline-item>
        </v-timeline>

        <v-timeline v-else class="custom-timeline" side="start">
          <v-timeline-item
            v-for="(job, i) in career"
            :key="`career-${i}`"
            dot-color="transparent"
            class="custom-timeline-item timeline-anim"
          >
            <template v-slot:icon>
              <div class="custom-dot" :style="{ borderColor: job.color }"></div>
            </template>
            <div class="timeline-content">
              <span class="year-label" :style="{ color: job.color }">{{ job.year }}</span>
              <h5 class="item-title">{{ job.company }}</h5>
              <p class="item-subtitle">{{ job.title }}</p>
              <p class="item-desc">{{ job.desc }}</p>
            </div>
          </v-timeline-item>
        </v-timeline>
      </div>
    </div>
  </section>

  <section
    id="project"
    class="project-section min-vh-100 px-3 text-white"
    style="background-color: #0e0e10"
  >
    <div class="container py-5">
      <h2 class="text-gradient text-center fw-bold mb-3">Personal Project</h2>
      <p class="text-center mb-5">Recent project participated</p>

      <div
        id="projectCarousel"
        class="carousel slide position-relative responsive-abt"
        data-bs-ride="carousel"
      >
        <div class="carousel-inner">
          <div
            v-for="(chunk, index) in chunkedProjects"
            :key="index"
            class="carousel-item"
            :class="{ active: index === 0 }"
          >
            <div class="row g-4 justify-content-center align-items-stretch">
              <div v-for="project in chunk" :key="project.id" class="col-12 col-md-6 col-lg-4">
                <div
                  class="card text-white h-100 shadow rounded-4 overflow-hidden project-card"
                  style="background-color: #1b1127; min-height: 480px"
                >
                  <div class="position-relative">
                    <img
                      :src="project.img"
                      class="card-img-top object-fit-cover project-img"
                      :alt="project.title"
                    />
                    <span
                      class="position-absolute top-0 start-0 m-3 badge text-white rounded-pill px-3 py-2 shadow"
                      style="background-color: #7e22ce"
                    >
                      Web Development
                    </span>
                  </div>
                  <div class="card-body d-flex flex-column justify-content-between">
                    <h5 class="card-title">{{ project.title }}</h5>
                    <p class="card-text text-truncate-3">{{ project.desc }}</p>
                    <div class="d-flex flex-wrap gap-2 mb-3">
                      <span
                        v-for="cat in project.category"
                        :key="cat.id"
                        class="badge rounded-pill border border-purple-400 text-purple-200 bg-dark"
                        style="
                          border: 1px solid #9f7aea;
                          background-color: rgba(159, 122, 234, 0.1);
                        "
                      >
                        {{ cat.name }}
                      </span>
                    </div>
                    <a
                      v-if="project.link"
                      :href="project.link"
                      target="_blank"
                      class="btn btn-outline-light rounded-pill w-100 d-flex justify-content-center align-items-center gap-2 project-link-btn"
                    >
                      View Project
                      <iconify-icon
                        icon="material-symbols:link"
                        width="20"
                        height="20"
                        class="link-icon"
                      ></iconify-icon>
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <button
          class="carousel-control-prev custom-carousel-btn"
          type="button"
          data-bs-target="#projectCarousel"
          data-bs-slide="prev"
        >
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button
          class="carousel-control-next custom-carousel-btn"
          type="button"
          data-bs-target="#projectCarousel"
          data-bs-slide="next"
        >
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>

        <div class="carousel-indicators mt-4 bottom-0 d-flex justify-content-center">
          <button
            v-for="(chunk, index) in chunkedProjects"
            :key="'indicator-' + index"
            type="button"
            data-bs-target="#projectCarousel"
            :data-bs-slide-to="index"
            :class="['rounded-circle bg-light', { active: index === 0 }]"
            style="width: 10px; height: 10px"
            :aria-label="'Slide ' + (index + 1)"
          ></button>
        </div>
      </div>
    </div>
  </section>
  <Footer />
</template>

<script>
import Navbar from '@/components/NavbarNew.vue'
import Footer from '@/components/FooterNew.vue'
import { gsap } from 'gsap'
import Saya from '@/assets/FarrAAU.png'
import AAU from '@/assets/AAUicon.png'
import Oscar from '@/assets/OscarBookstore.png'
import Yadi from '@/assets/YaDipinjam.png'
import trax from '@/assets/trax.png'
import hiwaya from '@/assets/hiwaya.png'

export default {
  name: 'Home',
  components: { Navbar, Footer },
  data() {
    return {
      hoverIcon: false,
      infoCards: [
        '✨ Pixel Perfect',
        '🚀 Performance First',
        '📱 Responsive Design',
        '🧼 Clean Code'
      ],
      Saya,
      hoverDiscord: false,
      selectedTab: 'career',
      education: [
        // {
        //   year: '2014 - 2017',
        //   school: 'SMP Negeri 1 Surabaya',
        //   degree: '-',
        //   desc: ' Sekolah Menengah Pertama',
        //   color: '#a855f7'
        // },
        {
          year: '2019 - 2020',
          school: 'RISTEK NUSANTARA',
          degree: 'ILMU PENGETAHUAN SOSIAL',
          desc: ' Sekolah Menengah Atas ',
          color: '#a855f7'
        },
        {
          year: '2022 - 2026',
          school: 'ITBS SWADHARMA',
          degree: 'TEKNIK INFORMATIKA',
          desc: ' Menjalani pendidikan tinggi di bidang Teknik Informatika untuk memperdalam pengetahuan dan keterampilan dalam pengembangan perangkat lunak serta teknologi informasi.',
          color: '#a855f7'
        }
        // {
        //   year: '2020 - 2024',
        //   school: 'Telkom University Surabaya',
        //   degree: 'Software Engineering',
        //   desc: 'Mendalami rekayasa perangkat lunak dan teknologi web modern.',
        //   color: '#3b82f6'
        // }
      ],
      career: [
        {
          year: '2018',
          company: 'Youtube',
          title: 'Youtuber Gaming',
          desc: 'Buat dan kelola konten gaming di YouTube, membangun komunitas penggemar yang aktif.',
          color: '#ec4899'
        },
        {
          year: '2021',
          company: 'Just Dero',
          title: 'Video Editor',
          desc: 'Menghasilkan konten video berkualitas tinggi untuk YouTube channel Just Dero.',
          color: '#ec4899'
        },
        {
          year: '2025',
          company: 'Bootcamp Harisenin',
          title: 'Fullstack Web Developer',
          desc: 'Menyelesaikan program bootcamp intensif untuk menjadi Fullstack Web Developer.',
          color: '#22c55e'
        }
        // {
        //   year: '2025',
        //   company: 'PT Hilwayn Nusantara Digital',
        //   title: 'Co-Founder',
        //   desc: 'Mendirikan software house Hiwaya, berfokus pada solusi web modern dan scalable.',
        //   color: '#06b6d4'
        // }
      ],
      projects: [
        {
          id: 1,
          img: hiwaya,
          title: 'Yvdzflix',
          desc: 'Platform streaming video on demand yang menyediakan berbagai konten menarik untuk pengguna.',
          category: [
            { id: 1, name: 'Website' },
            { id: 2, name: 'Express' },
            { id: 3, name: 'React' }
          ],
          link: 'https://yudzflix.vercel.app/movie'
        }
        // {
        //   id: 1,
        //   img: trax,
        //   title: 'TRAX',
        //   desc: 'Consultant Company, PT Transforma Dinamika Unggul, bergerak di bidang Human Resource',
        //   category: [
        //     { id: 1, name: 'Website' },
        //     { id: 2, name: 'Landing Page' },
        //     { id: 3, name: 'Vue' },
        //     { id: 3, name: 'Adonis.js' }
        //   ],
        //   link: 'https://trax.co.id'
        // },
        // {
        //   id: 1,
        //   img: Oscar,
        //   title: 'Toko Buku Oscar',
        //   desc: 'Aplikasi penjualan dan pembelian buku yang mendukung transaksi secara online maupun onsite, memudahkan pelanggan dalam mencari dan mendapatkan buku.',
        //   category: [
        //     { id: 1, name: 'Web Design' },
        //     { id: 2, name: 'Online Shop' },
        //     { id: 3, name: 'Vue' },
        //     { id: 3, name: 'Laravel' }
        //   ],
        //   link: null
        // },
        // {
        //   id: 2,
        //   img: Yadi,
        //   title: 'YaDipinjam',
        //   desc: 'Website perpustakaan kolektif yang memungkinkan pengguna meminjam dan meminjamkan buku secara langsung antar pengguna.',
        //   category: [
        //     { id: 1, name: 'Website' },
        //     { id: 2, name: 'Landing Page' },
        //     { id: 3, name: 'Vue' },
        //     { id: 4, name: 'Laravel' }
        //   ],
        //   link: null
        // },
        // {
        //   id: 3,
        //   img: AAU,
        //   title: 'CDC AAU',
        //   desc: 'Aplikasi untuk membantu pengguna mengembangkan karakter pribadi dengan fitur evaluasi, penilaian untuk Taruna Akademi Angkatan Udara Indonesia.',
        //   category: [
        //     { id: 1, name: 'CDC System' },
        //     { id: 2, name: 'Website' },
        //     { id: 2, name: 'Laravel' }
        //   ],
        //   link: null
        // },
        // {
        //   id: 4,
        //   img: AAU,
        //   title: 'Administrasi AAU',
        //   desc: 'Sistem untuk membantu pengguna dalam administrasi untuk Akademi Angkatan Udara Indonesia.',
        //   category: [
        //     { id: 1, name: 'Website' },
        //     { id: 2, name: 'PHP' },
        //     { id: 2, name: 'Laravel' }
        //   ],
        //   link: null
        // },
        // {
        //   id: 5,
        //   img: AAU,
        //   title: 'MKP Perbekalan AAU',
        //   desc: 'Aplikasi untuk membantu pengelolaan perbekalan Akademi Angkatan Udara Indonesia',
        //   category: [
        //     { id: 1, name: 'Website' },
        //     { id: 2, name: 'Vue' },
        //     { id: 2, name: 'Laravel' }
        //   ],
        //   link: null
        // },
        // {
        //   id: 6,
        //   img: AAU,
        //   title: 'Administrasi AAU',
        //   desc: 'Aplikasi untuk membantu pengguna dalam administrasi Akademi Angkatan Udara Indonesia.',
        //   category: [
        //     { id: 1, name: 'Website' },
        //     { id: 2, name: 'PHP' },
        //     { id: 2, name: 'Laravel' }
        //   ],
        //   link: null
        // }
      ]
    }
  },
  computed: {
    chunkedProjects() {
      const chunkSize = window.innerWidth < 768 ? 1 : 3
      const result = []
      for (let i = 0; i < this.projects.length; i += chunkSize) {
        result.push(this.projects.slice(i, i + chunkSize))
      }
      return result
    }
  },
  methods: {
    scrollToAbout() {
      document.getElementById('about').scrollIntoView({ behavior: 'smooth' })
    },
    animateHero() {
      gsap.timeline({ delay: 0.3 }).fromTo(
        '.home-anim',
        { opacity: 0, y: 30, scale: 0.95 },
        {
          opacity: 1,
          y: 0,
          scale: 1,
          duration: 0.6,
          stagger: 0.25,
          ease: 'power2.out',
          clearProps: 'all'
        }
      )
    },
    switchTab(tab) {
      if (this.selectedTab !== tab) {
        this.selectedTab = tab
        this.$nextTick(() => {
          this.animateTimeline()
        })
      }
    },
    animateTimeline() {
      const items = this.$refs.timelineWrapper.querySelectorAll('.timeline-anim')
      gsap.fromTo(
        items,
        { opacity: 0, y: 40, scale: 0.95 },
        {
          opacity: 1,
          y: 0,
          scale: 1,
          duration: 0.6,
          stagger: 0.2,
          ease: 'power2.out'
        }
      )
    },
    chunkProjects() {
      const chunkSize = window.innerWidth < 768 ? 1 : 3 // mobile = 1, desktop = 3
      this.chunkedProjects = []
      for (let i = 0; i < this.projects.length; i += chunkSize) {
        this.chunkedProjects.push(this.projects.slice(i, i + chunkSize))
      }
    }
  },
  mounted() {
    this.animateHero()
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;700&display=swap');

* {
  font-family: 'DM Sans', sans-serif;
}

/* Background */
#home {
  position: relative;
  z-index: 0;
  background: radial-gradient(circle at 30% 30%, rgba(168, 85, 247, 0.08), transparent),
    radial-gradient(circle at bottom right, rgba(100, 72, 255, 0.12), transparent), #0b0014;
  padding-top: 4rem;
  padding-left: 1.5rem;
  /* ~24px */
  padding-right: 1.5rem;
}

.tagline {
  font-weight: 600;
  font-size: 1.6rem;
  margin-top: 1.8rem;
  margin-bottom: 1.8rem;
}

.desc-text {
  font-size: 1.2rem;
  font-weight: 500;
  opacity: 0.85;
  max-width: 700px;
  line-height: 1.7;
}

@media (max-width: 768px) {
  /* Heading Hello lebih kecil dan turun */
  .home-anim.display-1 {
    font-size: 2rem;
    /* default Bootstrap display-1 itu besar banget */
    margin-top: 3rem;
  }

  .tagline {
    font-size: 1rem;
  }

  /* Deskripsi lebih kecil dan padding dikurangi */
  .desc-text {
    font-size: 0.85rem;
    line-height: 1.6;
    padding-left: 0.5rem;
    padding-right: 0.5rem;
  }

  /* Geser seluruh konten ke bawah */
  #home .content {
    justify-content: flex-start;
  }

  #home {
    padding-top: 0rem;
  }
}

@media (min-width: 992px) {
  #home {
    padding-left: 0;
    padding-right: 0;
  }
}

/* Lapisan gelap ambiance ungu */
.background-dark {
  position: absolute;
  inset: 0;
  background: linear-gradient(180deg, #0f0f10 0%, #1a0b1f 100%);
  z-index: 0;
}

/* Foto di sisi kanan dengan potongan diagonal & opacity */
.bg-saya-diagonal {
  position: absolute;
  inset: 0;
  object-fit: cover;
  width: 100%;
  height: 100%;
  opacity: 0.25;
  filter: grayscale(20%) blur(1px);
  clip-path: polygon(60% 0, 100% 0, 100% 100%, 35% 100%);
  z-index: 1;
}

/* Konten di atas semua layer */
.content {
  position: relative;
  z-index: 2;
}

/* Watermark */
.bg-title {
  position: absolute;
  font-size: 15rem;
  font-weight: 900;
  color: rgba(200, 100, 255, 0.03);
  z-index: 0;
  pointer-events: none;
}

/* Tagline */

.tag-white {
  color: #ffffff;
}

.tag-gradient {
  background: linear-gradient(90deg, #60a5fa, #a855f7);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* Tombol Discord selalu fill */
.btn-discord {
  background: #a855f7 !important;
  /* fill langsung */
  color: #fff !important;
  border: 2px solid #a855f7 !important;
  font-weight: 600;
  padding: 12px 32px;
  border-radius: 50px;
  transition: all 0.3s ease;
  position: relative;
  z-index: 2;
}

/* Hover efek */
.btn-discord:hover {
  background: #9333ea !important;
  border-color: #9333ea !important;
}

/* Animasi icon Discord */
.rotate-once {
  animation: rotateIcon 0.5s ease forwards;
}

@keyframes rotateIcon {
  from {
    transform: rotate(0);
  }

  to {
    transform: rotate(360deg);
  }
}

/* Mobile sedikit mengecil */
@media (max-width: 576px) {
  .btn-discord iconify-icon {
    width: 22px !important;
    height: 22px !important;
  }
}

.btn-view-more,
.btn-discord {
  background: transparent;
  border: 2px solid #a855f7;
  color: #a855f7;
  font-weight: 600;
  padding: 8px 24px;
  /* lebih kecil */
  border-radius: 50px;
  font-size: 0.95rem;
  /* perkecil font */
  transition: all 0.3s ease;
  position: relative;
  z-index: 2;
}

.btn-discord:hover,
.btn-view-more:hover {
  background: #a855f7;
  color: #fff;
}

/* Animasi rotasi sekali */
.rotate-once {
  animation: spinOnce 0.6s ease;
}

@keyframes spinOnce {
  from {
    transform: rotate(0);
  }

  to {
    transform: rotate(360deg);
  }
}

/* ===== MOBILE RESPONSIVE ===== */
@media (max-width: 576px) {
  .btn-discord {
    background: #a855f7;
    color: #fff;
    border: 2px solid #a855f7;
  }

  /* Hover Discord -> sedikit lebih terang */
  .btn-discord:hover {
    background: #9333ea;
    /* ungu sedikit lebih gelap/terang */
    border-color: #9333ea;
  }

  .btn-view-more,
  .btn-discord {
    padding: 6px 18px;
    /* lebih ramping di mobile */
    font-size: 0.85rem;
    /* font lebih kecil */
  }

  .btn-discord iconify-icon,
  .btn-view-more iconify-icon {
    width: 22px !important;
    /* icon lebih kecil */
    height: 22px !important;
  }
}

iconify-icon {
  transition: transform 0.4s ease;
}

.rotated {
  transform: rotate(-90deg);
  /* arrowdown → arrowleft */
}

/* Social Icon */
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

/* Scroll Indicator */
.scroll-indicator {
  cursor: pointer;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  z-index: 2;
}

.pill {
  width: 28px;
  height: 48px;
  border: 2px solid #a855f7;
  border-radius: 999px;
  display: flex;
  align-items: flex-start;
  justify-content: center;
  padding: 4px;
}

.dot {
  width: 8px;
  height: 8px;
  background: #a855f7;
  border-radius: 50%;
  animation: bounce 1s infinite ease-in-out;
}

@keyframes bounce {
  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(10px);
  }
}

/* Gradient Text FARREL */
.text-gradient {
  background: linear-gradient(90deg, #a855f7, #6366f1);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* Scroll indicator */
.scroll-indicator {
  cursor: pointer;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.pill {
  width: 28px;
  height: 48px;
  border: 2px solid #a855f7;
  border-radius: 999px;
  display: flex;
  align-items: flex-start;
  justify-content: center;
  padding: 4px;
}

.dot {
  width: 8px;
  height: 8px;
  background: #a855f7;
  border-radius: 50%;
  animation: bounce 1s infinite ease-in-out;
}

@keyframes bounce {
  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(10px);
  }
}

/* About section background */
.about-section {
  background: linear-gradient(180deg, #0b0014, #1e0036);
  padding-top: 5rem;
  padding-bottom: 4rem;
}

.responsive-abt {
  padding-top: 20px;
}

.tk-skills {
  padding-top: 70px;
}

@media (min-width: 992px) {
  /* Bootstrap breakpoint untuk lg */
  .responsive-abt {
    padding-top: 120px;
  }

  .tk-skills {
    padding-top: 0px;
  }
}

/* Stat box */
.stat-box {
  border: 1px solid #a855f7;
  border-radius: 1rem;
  padding: 1rem;
  background-color: rgba(168, 85, 247, 0.05);
  flex: 1 1 30%;
}

/* Skill category box */
.skill-category {
  border: 1px solid rgba(168, 85, 247, 0.3);
  border-radius: 1rem;
  padding: 0.1rem 1.5rem;
  background-color: rgba(255, 255, 255, 0.02);
  box-shadow: 0 0 10px rgba(168, 85, 247, 0.1);
}

/* Skill icon style */
.skill-icon img {
  border-radius: 0.5rem;
  background-color: #1e1e2f;
  padding: 0.5rem;
}

.skill-icon p {
  color: #ddd;
  font-size: 0.9rem;
}

.accordion-button {
  background-color: transparent;
  color: #fff;
  font-weight: 600;
}

.accordion-button:focus {
  box-shadow: none;
}

.accordion-button:not(.collapsed) {
  background-color: rgba(168, 85, 247, 0.1);
  color: #a855f7;
}

.skill-category {
  border: 1px solid rgba(168, 85, 247, 0.2);
  border-radius: 1rem;
  background-color: rgba(255, 255, 255, 0.02);
  margin-bottom: 1rem;
  overflow: hidden;
}

/* Skill Card Box */
.skill-card {
  display: flex;
  gap: 0.75rem;
  align-items: center;
  background-color: #1e1e2f;
  padding: 0.8rem 1rem;
  border-radius: 0.75rem;
  min-width: 160px;
  border: 2px solid transparent;
  color: #fff;
}

/* Border Variants */
.border-gradient-purple {
  border-color: #a855f7;
}

.border-gradient-blue {
  border-color: #3b82f6;
}

.border-gradient-bluepk {
  border-color: #3868b4;
}

.border-gradient-green {
  border-color: #22c55e;
}

.border-gradient-yellow {
  border-color: #facc15;
}

.border-gradient-red {
  border-color: #fc0606;
}

.border-gradient-pink {
  border-color: #06b6d4;
}

.border-gradient-indigo {
  border-color: #6366f1;
}

.border-gradient-cyan {
  border-color: #06b6d4;
}

.border-gradient-gray {
  border-color: #6b7280;
}

/* Badge & warna tambahan */
.bg-purple {
  background-color: #a855f7 !important;
  color: white;
}

.text-purple {
  color: #c084fc;
}

/* Background watermark */
.bg-title {
  position: absolute;
  font-size: 15rem;
  font-weight: 900;
  color: rgba(200, 100, 255, 0.03);
  z-index: 0;
  pointer-events: none;
}

/* // Journey */

.my-journey-section {
  background: linear-gradient(180deg, #0f0f10, #1a0b1f);
  color: #fff;
  min-height: 100vh;
  padding-top: 5rem;
}

.text-gradient {
  background: linear-gradient(90deg, #60a5fa, #a855f7);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* Pills Toggle */
.journey-btn {
  border-radius: 50px;
  font-weight: 600;
  padding: 8px 24px;
  margin: 0 5px;
  transition: all 0.3s ease;
}

.btn-fill {
  background: linear-gradient(90deg, #60a5fa, #a855f7);
  color: #fff !important;
  border: none;
}

.btn-outline {
  background: transparent;
  color: #fff !important;
  border: 2px solid rgba(255, 255, 255, 0.3);
}

.btn-outline:hover {
  background: rgba(255, 255, 255, 0.1);
}

/* Timeline */
.custom-timeline {
  padding-left: 1rem !important;
}

.custom-timeline-item {
  padding-bottom: 2rem;
}

.custom-dot {
  width: 16px;
  height: 16px;
  border: 3px solid;
  border-radius: 50%;
  background: #111;
  box-shadow: 0 0 10px rgba(255, 255, 255, 0.15);
}

/* Timeline Content on the right */
.timeline-content {
  margin-left: 1rem;
}

.year-label {
  font-size: 1rem;
  font-weight: 700;
}

.item-title {
  font-size: 1.2rem;
  font-weight: 700;
}

.item-subtitle {
  font-size: 1rem;
  font-weight: 500;
  opacity: 0.9;
}

.item-desc {
  font-size: 0.95rem;
  opacity: 0.8;
  max-width: 500px;
}

/* Responsive */
@media (max-width: 768px) {
  .item-title {
    font-size: 1rem;
  }

  .item-subtitle {
    font-size: 0.85rem;
  }

  .item-desc {
    font-size: 0.8rem;
    max-width: 250px;
  }

  .year-label {
    font-size: 0.9rem;
  }
}

.project-section {
  background: linear-gradient(180deg, #0b0014, #1a0929);
  padding-top: 5rem;
  padding-bottom: 4rem;
}

.carousel-item {
  transition: transform 0.6s ease;
  min-height: 100%;
}

.project-img {
  transition: transform 0.5s ease;
  height: 240px;
  object-fit: cover;
}

.project-card:hover .project-img {
  transform: scale(1.05);
}

.custom-carousel-btn {
  background-color: #6f42c1;
  border-radius: 20%;
  width: 38px;
  height: 38px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: none;
  box-shadow: 0 0 10px rgba(111, 66, 193, 0.5);
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  z-index: 10;
}

.custom-carousel-btn .carousel-control-prev-icon,
.custom-carousel-btn .carousel-control-next-icon {
  filter: invert(1);
}

.text-truncate-3 {
  overflow: hidden;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  min-height: 80px;
}

.carousel-indicators {
  bottom: -2rem !important;
  justify-content: start;
  gap: 0.5rem;
}

.carousel-inner {
  padding-bottom: 3rem;
}

.project-link-btn .link-icon {
  transition: transform 0.3s ease;
}

.project-link-btn:hover .link-icon {
  transform: translateY(-3px);
}
</style>
