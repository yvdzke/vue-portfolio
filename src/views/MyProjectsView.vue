<script>
import ToolbarComp from '@/components/ToolbarComp.vue'
import FooterComp from '@/components/FooterComp.vue'
import AAU from '@/assets/AAUicon.png';
import Oscar from '@/assets/OscarBookstore.png';
import Yadi from '@/assets/YaDipinjam.png';
import Saya from '@/assets/rescale.png';

export default {
  name: 'Our Menus',
  components: {
    ToolbarComp,
    FooterComp
  },
  data () {
      return {
        loaded: false,
        loading: false,
        colors: [
          'indigo',
          'warning',
          'pink darken-2',
          'red lighten-1',
          'deep-purple accent-4',
        ],
        items: [
          {
            src: '../src/assets/background.svg',
          },
        ],
        services: [
        {
            id: 1,
            title: 'Unified Modelling Language',
            desc: 'Kami menyediakan layanan pembuatan diagram UML, seperti Use Case, Activity Diagram, Sequence Diagram, dan lainnya dengan harga terjangkau'
          },  
        {
            id: 2,
            title: 'Pembuatan Website',
            desc: 'Kami menyediakan layanan pembuatan website untuk bisnis anda, sistem manajemen, website pembelian dan lainnya dengan harga terjangkau'
          },
          {
            id: 3,
            title: '3D Modelling',
            desc: 'Kami menyediakan layanan pembuatan website untuk pembelian'
          },
          
        ],
        chunkedCoffees: [],
        coffees: [
          {
            id: 1,
            img: Oscar,
            title: 'Toko Buku Oscar',
            rating: '4',
            desc: 'Aplikasi penjualan dan pembelian buku yang mendukung transaksi secara online maupun onsite, memudahkan pelanggan dalam mencari dan mendapatkan buku.',
            category: [
              { 
                id: 1,
                name: "Diagram"
              },
              { 
                id: 2,
                name: "Use Case"
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
                name: "Website"
              },
              { 
                id: 2,
                name: "Landing Page"
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
                name: "3D Model"
              },
              { 
                id: 2,
                name: "Animation"
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
                name: "3D Model"
              },
              { 
                id: 2,
                name: "Animation"
              }
            ]
          },
        ],
        category: [
          {
            id: 1,
            name: "Website"
          },
          {
            id: 2,
            name: "Landing Page"
          },
          {
            id: 3,
            name: "Diagrams"
          },
          {
            id: 4,
            name: "Mobile"
          },
          {
            id: 5,
            name: "Front End "
          },
          {
            id: 6,
            name: "Back End"
          },
        ]
      }
  },
  methods: {
    chunkCoffees() {
      this.chunkedCoffees = [];
      for (let i = 0; i < this.coffees.length; i += 4) {
        this.chunkedCoffees.push(this.coffees.slice(i, i + 4));
      }
    },
    onClick () {
      this.loading = true

      setTimeout(() => {
        this.loading = false
        this.loaded = true
      }, 2000)
    },
  },
  mounted() {
    this.chunkCoffees();
  }

}
</script>

<template>
  <ToolbarComp>
    <v-container fluid style="background-color: #0d1b2a">
        <v-row class="projects">
        <v-col cols="12" sm="2" class="sidebar">
            <v-row class="align-center text-navbar">
              <a class="me-7 text-white text-muted">Search by Category</a>
              <v-chip-group
                column
                color="teal-lighten-4"
                selected-class="text-primary"
              >
                <v-chip
                  v-for="item in category"
                  :key="item.id"
                  class="text-white mb-2"
                >
                  <a>{{ item.name }}</a>
                </v-chip>
              </v-chip-group>
            </v-row>
          </v-col>
          <v-col cols="12" sm="10">
            <v-row class="pt-7 pb-5 mb-5">
              <v-col cols="6" sm="3" v-for="(item, index) in coffees"
              :key="index">
                <div class="card mx-2 card-style mb-2 h-100" >
                  <img class="card-img-top p-2" style="border-radius: 14px;" :src="item.img" alt="Card image cap">
                  <h5 class="card-title p-2"> {{ item.title }}</h5>
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

.carousel-block {
  width: 100%;
  height: 100%;
  max-height: 300px;
  margin-left: 10px;
  margin-right: 30px;
  margin-top: 10px;
  border-radius: 24px;
}

.carousel-item {
  position: relative;
}

.transparent-sheet {
  background-color: transparent !important;
  box-shadow: none;
  height: 60%;
}

.text-navbar {
  font-size: 1rem;
}

.text-content h3 {
  font-size: 3rem; 
  margin: 0;
  font-weight: bold;
}

.text-content p {
  font-size: 1rem; 
  margin: 0;
}

.about-us {
  padding-left: 130px;
  padding-right: 130px;
  padding-top: 60px;
  margin-bottom: 80px;
}


.service {
  padding-left: 130px;
  padding-right: 130px;
  padding-top: 60px;
}

.service-paragraph{
  padding-top: 30px;
}

.projects {
  padding-top: 120px;
  padding-left: 130px;
  padding-right: 130px;
  padding-bottom: 200px;
}

.card-style {
  background-color: #2c3a4a;
  color: #FFF;
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

  .text-navbar {
    font-size: 0.775rem;
    margin-left: 5px
  }

  .about-us {
    padding-left: 10px;
    padding-right: 10px;
  }
  .content-row {
    padding-top: 0 !important;
  }

  .service {
    padding-left: 10px;
    padding-right: 10px;
  }

  .projects {
    padding-left: 10px;
    padding-right: 10px;
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