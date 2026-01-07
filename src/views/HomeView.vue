<script>
import ToolbarComp from '@/components/ToolbarComp.vue'
import FooterComp from '@/components/FooterComp.vue'
import AAU from '@/assets/AAUicon.png'
import Oscar from '@/assets/OscarBookstore.png'
import Yadi from '@/assets/YaDipinjam.png'
import Saya from '@/assets/rescale.png'

export default {
  name: 'Home',
  components: {
    ToolbarComp,
    FooterComp
  },
  data() {
    return {
      Saya,
      isMobile: false,
      colors: ['indigo', 'warning', 'pink darken-2', 'red lighten-1', 'deep-purple accent-4'],
      tech: [
        { id: 1, title: 'Vue.js', icon: 'mdi-vuejs', color: '#42b883' },
        { id: 2, title: 'Laravel', icon: 'mdi-laravel', color: '#f05340' },
        { id: 3, title: 'AdonisJS', icon: 'mdi-alpha-a-box', color: '#5a2c82' },
        { id: 4, title: 'Bootstrap', icon: 'mdi-bootstrap', color: '#7952b3' },
        { id: 5, title: 'Tailwind CSS', icon: 'mdi-tailwind', color: '#38b2ac' },
        { id: 6, title: 'PostgreSQL', icon: 'mdi-database', color: '#336791' },
        { id: 7, title: 'MySQL', icon: 'mdi-database', color: '#00758f' },
        { id: 8, title: 'JavaScript', icon: 'mdi-language-javascript', color: '#f7df1e' },
        { id: 9, title: 'TypeScript', icon: 'mdi-language-typescript', color: '#007acc' },
        { id: 10, title: 'Docker', icon: 'mdi-docker', color: '#2496ed' }
      ],
      items: [
        {
          src: '../src/assets/background.svg'
        }
      ],
      years: [
        {
          color: 'cyan',
          year: '2021-2022',
          title: 'Video Editor',
          company: 'Turah Parthayana',
          desc: 'Online Video Editor untuk Channel Turah Parthayana'
        },
        {
          color: 'green',
          year: '2023-Now',
          title: 'Fullstack Developer',
          company: 'PT Transforma Dinamika Unggul',
          desc: 'Bekerja menjadi Fullstack Web Developer untuk PT Transforma Dinamika Unggul'
        }
      ],
      projects: [
        {
          id: 1,
          img: Oscar,
          title: 'Toko Buku Oscar',
          rating: '4',
          desc: 'Aplikasi penjualan dan pembelian buku yang mendukung transaksi secara online maupun onsite, memudahkan pelanggan dalam mencari dan mendapatkan buku.',
          category: [
            {
              id: 1,
              name: 'Diagram'
            },
            {
              id: 2,
              name: 'Use Case'
            }
          ]
        },
        {
          id: 2,
          img: Yadi,
          title: 'YaDipinjam',
          rating: '4.5',
          desc: 'Website perpustakaan kolektif yang memungkinkan pengguna meminjam dan meminjamkan buku secara langsung antar pengguna.',
          category: [
            {
              id: 1,
              name: 'Website'
            },
            {
              id: 2,
              name: 'Landing Page'
            }
          ]
        },
        {
          id: 3,
          img: AAU,
          title: 'CDC AAU',
          rating: '4.5',
          desc: 'Aplikasi untuk membantu pengguna mengembangkan karakter pribadi dengan fitur evaluasi, penilaian untuk Taruna Akademi Angkatan Udara Indonesia.',
          category: [
            {
              id: 1,
              name: '3D Model'
            },
            {
              id: 2,
              name: 'Animation'
            }
          ]
        },
        {
          id: 4,
          img: AAU,
          title: 'Administrasi AAU',
          rating: '3.5',
          desc: 'Sistem untuk membantu pengguna dalam administrasi untuk Akademi Angkatan Udara Indonesia.',
          category: [
            {
              id: 1,
              name: '3D Model'
            },
            {
              id: 2,
              name: 'Animation'
            }
          ]
        }
      ]
    }
  },
  methods: {
    PushToOurMenus() {
      this.$router.push('/projects')
    },
    checkScreenSize() {
      this.isMobile = window.innerWidth <= 600
    }
  },
  mounted() {
    this.checkScreenSize()
    window.addEventListener('resize', this.checkScreenSize)
  }
}
</script>

<template>
  <ToolbarComp>
    <v-container fluid style="background-color: #0d1b2a">
      <v-row class="about-us">
        <v-col cols="12" md="6" align-self="center">
          <v-row justify="center">
            <v-avatar :size="isMobile ? 200 : 450">
              <v-img alt="Ava" :src="Saya"></v-img>
            </v-avatar>
          </v-row>
        </v-col>
        <v-col cols="12" md="6" align-self="center">
          <v-row class="titlesm-row">
            <a class="fw-semibold text-light"> Web Developer | Fullstack Developer </a>
          </v-row>
          <v-row class="title-row">
            <a class="fw-bolder text-light lh-1"> Farrel Ahmad Darmawan </a>
          </v-row>
          <v-row class="content-row">
            <p class="lh-base text-light">
              Graduated Full-Stack Web Developer bootcamp program from harisenin.com for deepening
              skills in Web Developer. Explore my latest projects, showcasing my expertise in web
              development.
            </p>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <v-container fluid style="background-color: #1b263b">
      <v-row class="about-us">
        <v-col class="align-self-center my-education" data-aos="fade-up">
          <v-row class="subtitle-row">
            <a style="font-weight: 600"> &mdash; Tentang Saya </a>
          </v-row>
          <v-row class="title-row">
            <a style="font-weight: 800">My Education </a>
          </v-row>
        </v-col>
        <v-col class="align-self-center" data-aos="fade-up">
          <v-row class="content-row">
            <v-timeline align="start" side="end">
              <v-timeline-item dot-color="pink" size="small">
                <div class="d-flex text-light">
                  <strong class="me-4">2014</strong>
                  <div>
                    <strong>SDIT At-Taqwa</strong>
                    <div class="text-caption">Sekolah Dasar</div>
                  </div>
                </div>
              </v-timeline-item>

              <v-timeline-item dot-color="teal-lighten-3" size="small">
                <div class="d-flex text-light">
                  <strong class="me-4">2017</strong>
                  <div>
                    <strong>SMP Negeri 1 Surabaya</strong>
                    <div class="text-caption mb-2">Junior Highscool</div>
                  </div>
                </div>
              </v-timeline-item>

              <v-timeline-item dot-color="pink" size="small">
                <div class="d-flex text-light">
                  <strong class="me-4">2020</strong>
                  <div>
                    <strong>SMA Negeri 2 Surabaya</strong>
                    <div class="text-caption mb-2">Senior Highschool</div>
                  </div>
                </div>
              </v-timeline-item>

              <v-timeline-item dot-color="teal-lighten-3" size="small">
                <div class="d-flex text-light">
                  <strong class="me-4">2024</strong>
                  <div>
                    <strong>Telkom University Surabaya</strong>
                    <div class="text-caption mb-2">University</div>
                  </div>
                </div>
              </v-timeline-item>
            </v-timeline>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <v-container fluid style="background-color: #0d1b2a">
      <v-row class="about-us">
        <v-col class="my-education" cols="12" data-aos="fade-up" align-self="center">
          <v-row class="title-row mb-7" justify="center">
            <a style="font-weight: 800">My Career</a>
          </v-row>
          <v-row class="career-row px-2" justify="center">
            <v-timeline align="start" style="padding-bottom: 100px">
              <v-timeline-item
                v-for="(year, i) in years"
                :key="i"
                :dot-color="year.color"
                size="small"
              >
                <template v-slot:opposite>
                  <div
                    :class="`pt-1 headline font-weight-bold text-${year.color}`"
                    v-text="year.year"
                  ></div>
                </template>
                <div>
                  <p
                    :class="`mt-n1 headline font-weight-bold text-${year.color}`"
                    :style="{ color: '#FFF', fontSize: isMobile ? '16px' : '20px' }"
                  >
                    {{ year.company }}
                  </p>
                  <p
                    :class="`mt-n1 headline font-weight-light mb-4 text-${year.color}`"
                    :style="{ color: '#FFF', fontSize: isMobile ? '12px' : '20px' }"
                  >
                    {{ year.title }}
                  </p>
                  <p
                    :class="`mb-4`"
                    :style="{
                      width: isMobile ? '120px' : '500px',
                      color: '#FFF',
                      fontSize: isMobile ? '14px' : '18px'
                    }"
                  >
                    {{ year.desc }}
                  </p>
                </div>
              </v-timeline-item>
            </v-timeline>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <v-container fluid style="background-color: #1b263b">
      <v-row class="about-us">
        <v-col cols="12" md="6" class="align-self-center my-education" data-aos="fade-up">
          <v-row class="subtitle-row">
            <a style="font-weight: 800"> &mdash; Tentang Saya </a>
          </v-row>
          <v-row class="title-row">
            <a style="font-weight: 800"> My Tech Stack </a>
          </v-row>
        </v-col>
        <v-col cols="12" md="6" class="align-self-center" data-aos="fade-up">
          <v-row class="content-row">
            <v-col v-for="item in tech.slice(0, 5)" :key="item.id" class="text-center">
              <v-icon :icon="item.icon" :color="item.color" :size="isMobile ? 60 : 80"> </v-icon>
              <p style="font-weight: 500; font-size: 12px; color: white">{{ item.title }}</p>
            </v-col>
          </v-row>
          <v-row class="content-row mt-9">
            <v-col v-for="item in tech.slice(5)" :key="item.id" class="text-center">
              <v-icon :icon="item.icon" :color="item.color" :size="isMobile ? 60 : 80"> </v-icon>
              <p style="font-weight: 500; font-size: 12px; color: white">{{ item.title }}</p>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <v-container fluid style="background-color: #0d1b2a">
      <v-row class="projects">
        <v-col align-self="center">
          <v-row>
            <v-col>
              <a class="project-header text-white"> My Projects </a>
            </v-col>
            <v-col class="text-end align-end me-5">
              <a
                @click="PushToOurMenus"
                style="font-size: 15px; font-weight: 200; color: white; cursor: pointer"
              >
                See More <v-icon icon="mdi-arrow-right-thin" size="small"></v-icon>
              </a>
            </v-col>
          </v-row>
          <v-row class="pt-7 pb-5">
            <v-col cols="6" sm="3" v-for="(item, index) in coffees" :key="index">
              <!-- <v-card
                  class="mx-1 mb-2 mobile-card"
                  :max-width="isMobile ? '300' : '378'"
                  :min-height="isMobile ? '400' : '500'"
                  style="display: flex; flex-direction: column; border-radius: 12px;"
                  color="#2c3a4a"
                >
                  <v-img
                    class="align-end text-white"
                    :src="item.img"
                    :max-height="isMobile ? '150' : '300'"
                    cover
                  >
                  </v-img>
                  <v-card-title class="px-3 pt-2">
                    <p :style="{ fontWeight: '700', color: '#FFF', fontSize: isMobile ? '14px' : '20px' }">
                      {{ item.title }}
                    </p>
                  </v-card-title>
                  <v-card-text class="px-3 mb-2">
                    <p :style="{ fontWeight: '300', color: '#FFF', fontSize: isMobile ? '11px' : '14px' }">
                      {{ item.desc }}
                    </p>
                  </v-card-text>
                </v-card> -->
              <div class="card mx-2 card-style mb-2">
                <img
                  class="card-img-top p-2"
                  style="border-radius: 14px"
                  :src="item.img"
                  alt="Card image cap"
                />
                <h5 class="card-title p-2">{{ item.title }}</h5>
                <div class="card-body p-2">
                  <p class="card-text card-desc">{{ item.desc }}</p>
                </div>
              </div>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </ToolbarComp>
  <FooterComp />
</template>

<style scoped>
* {
  padding: 0;
  margin: 0;
  font-family: 'Poppins';
  text-decoration: none;
  list-style: none;
}

.fade-img {
  position: relative;
}

.fade-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(
    to right,
    rgba(255, 255, 255, 0) 60%,
    rgba(255, 255, 255, 1) 95%,
    rgba(255, 255, 255, 1) 100%
  );
}

.titlesm-row {
  font-size: 24px;
}
.title-row {
  font-size: 64px;
}

.subtitle-row {
  font-size: 24px;
}

.text-content h3 {
  font-size: 2rem;
  margin: 0;
}

.text-content p {
  font-size: 1rem;
  margin: 0;
}

.about-us {
  padding-top: 60px;
  min-height: 100vh;
}

.my-education {
  padding-left: 80px;
  color: white;
}

.content-row {
  padding-top: 0;
  padding-right: 100px;
  font-size: 20px;
}

.career-row {
  padding-top: 0;
  font-size: 20px;
}

.content-owner {
  padding-right: 80px;
  font-size: 24px;
}

.service {
  padding-left: 130px;
  padding-right: 130px;
  padding-top: 100px;
  padding-bottom: 100px;
}

.title-profile {
  font-size: 32px;
  color: #080808;
}

.text-owner {
  font-size: 32px;
  color: #080808;
}

.service-paragraph {
  padding-top: 30px;
}

.projects {
  padding-left: 130px;
  padding-right: 130px;
  padding-top: 100px;
  min-height: 100vh;
}

.project-header {
  font-size: 36px;
  font-weight: 600;
  color: #212529;
}
.card-style {
  background-color: #2c3a4a;
  color: #fff;
  height: 400px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.card-desc {
  font-size: 14px;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 4; /* Limit to 3 lines */
  -webkit-box-orient: vertical;
  height: auto;
}

@media (max-width: 600px) {
  [data-aos] {
    opacity: 1 !important;
    transform: none !important;
    transition: none !important;
  }
  .fade-img {
    position: relative;
  }
  .fade-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 200px;
    background: linear-gradient(
      to right,
      rgba(255, 255, 255, 0) 100%,
      rgba(255, 255, 255, 1) 95%,
      rgba(255, 255, 255, 1) 100%
    );
  }

  .titlesm-row {
    font-size: 14px;
    margin-top: 20px;
    padding-left: 10px;
    padding-right: 10px;
  }
  .title-row {
    font-size: 32px;
    padding-left: 10px;
    padding-right: 10px;
  }

  .title-profile {
    font-size: 24px;
    color: #080808;
  }
  .text-owner {
    font-size: 22px;
    color: #080808;
  }
  .carousel-block {
    width: 100%;
    height: 100%;
    max-height: 150px;
    margin-top: 10px;
  }

  .carousel-item {
    position: relative;
    height: 300px;
  }

  .transparent-sheet {
    background-color: transparent !important;
    box-shadow: none;
    height: 20%;
  }

  .text-content h3 {
    padding-top: 40px;
    font-size: 1.15rem;
  }
  .text-content p {
    font-size: 0.575rem;
  }

  .about-us {
    padding-left: 10px;
    padding-right: 10px;
    padding-top: 120px;
  }
  .content-row {
    padding-top: 20px;
    padding-left: 10px;
    padding-right: 10px;
    margin-bottom: 100px;
    font-size: 18px;
  }

  .career-row {
    padding-top: 20px;
    padding-left: 10px;
    padding-right: 10px;
    margin-bottom: 100px;
    font-size: 18px;
  }

  .my-education {
    padding-left: 10px;
  }

  .service {
    padding-left: 10px;
    padding-right: 10px;
  }

  .projects {
    padding-left: 10px;
    padding-right: 10px;
  }

  .project-header {
    font-size: 24px;
    font-weight: 600;
    color: #212529;
  }

  .mobile-card {
    height: 200px;
  }

  .card-style {
    height: 350px;
  }
  .card-desc {
    font-size: 11px;
    -webkit-line-clamp: none; /* Adjust line clamp for mobile if needed */
  }
}
</style>
