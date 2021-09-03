<template>
  <div>
    <div
      class="hero"
      :style="{
        'background-image': `url('${backgroundImg}')`,
        'background-size': 'cover',
      }"
    >
      <v-app-bar color="transparent" dark>
        <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>

        <v-spacer></v-spacer>
        <v-btn text>Catálogo</v-btn>
        <v-btn text>Refacciones</v-btn>
        <v-btn text>Accesorios</v-btn>
        <div style="width: 10%">
          <v-text-field
            hide-details
            append-icon="mdi-magnify"
            single-line
            placeholder="Buscar"
          ></v-text-field>
        </div>
      </v-app-bar>
      <v-navigation-drawer v-model="drawer" absolute temporary>
        <v-list nav dense>
          <v-list-item-group v-model="group">
            <v-list-item>
              <!-- <v-list-item-icon>
                <v-icon>mdi-home</v-icon>
              </v-list-item-icon> -->
              <v-list-item-title>Inicio</v-list-item-title>
            </v-list-item>

            <v-list-item>
              <!-- <v-list-item-icon>
                <v-icon>mdi-account</v-icon>
              </v-list-item-icon> -->
              <v-list-item-title>Sobre nosotros</v-list-item-title>
            </v-list-item>
            <v-list-item>
              <!-- <v-list-item-icon>
                <v-icon>mdi-account</v-icon>
              </v-list-item-icon> -->
              <v-list-item-title>Cotizaciones</v-list-item-title>
            </v-list-item>
            <v-list-item>
              <!-- <v-list-item-icon>
                <v-icon>mdi-account</v-icon>
              </v-list-item-icon> -->
              <v-list-item-title>Contáctanos</v-list-item-title>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-navigation-drawer>
      <v-container>
        <v-row class="mt-5">
          <v-col class="mt-5">
            <v-carousel hide-delimiters height="200" class="mt-5">
              <v-carousel-item
                v-for="(item, i) in items"
                :key="i"
                reverse-transition="fade-transition"
                transition="fade-transition"
              >
                <v-row
                  class="fill-height d-flex justify-space-around"
                  align="center"
                >
                  <img :src="item.src" height="80%" width="auto" />
                  <div class="text-center">
                    <h3>Nuevos Modelos</h3>
                    <h2>Aston Martin DB11</h2>
                    <p>El modelo mas poderoso de la historia</p>
                    <v-btn tile outlined color="#FAFAFA">Ver detalles</v-btn>
                  </div>
                </v-row>
              </v-carousel-item>
            </v-carousel>
          </v-col>
        </v-row>
      </v-container>
    </div>
    <v-container>
      <v-card
        :loading="loading"
        class="mx-auto my-12 text-center"
        max-width="374"
      >
        <template slot="progress">
          <v-progress-linear
            color="deep-purple"
            height="10"
            indeterminate
          ></v-progress-linear>
        </template>

        <v-img
          height="200"
          src="https://www.fiat.com.mx/content/uploads/2017/10/2011-2017-Fiat-Mobi.png"
        ></v-img>
        <br />
        <div class="text-center">
          <img
            height="50"
            src="https://1000marcas.net/wp-content/uploads/2020/01/Fiat-logo.png"
          />
        </div>
        <v-card-title class="justify-center">Lorem ipsum dolor</v-card-title>

        <v-card-text>
          <div>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
            eiusmod tempor incididunt ut ero labore et dolore
          </div>
        </v-card-text>
        <v-card-title class="justify-center">$1,200.00 MXN</v-card-title>
        <v-btn tile width="50%" color="black">
          <span style="color: #fff">COMPRAR</span>
        </v-btn>
        <br />
        <v-card-actions> </v-card-actions>
      </v-card>
    </v-container>
    <v-footer dark>
      <v-row class="justify-center text-center">
        <v-col> &copy;F.H.A {{ new Date().getFullYear() }} </v-col>
        <v-col>
          <ul>
            <li>Sobre nosotros</li>
            <li>Contacto</li>
            <li>Terminos & Condiciones</li>
          </ul>
        </v-col>
        <v-col>
          <v-list>
            <v-list-item>
              <v-icon> mdi-twitter</v-icon>
              <v-list-item-content>
                <v-list-item-title> TWITTER</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
            <v-list-item>
              <v-icon> mdi-facebook</v-icon>
              <v-list-item-content>
                <v-list-item-title> FACEBOOK</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-col>
      </v-row>
    </v-footer>
  </div>
</template>

<script>
export default {
  name: "Home",

  components: {},
  data: () => ({
    loading: false,
    selection: 1,
    drawer: false,
    backgroundImg: require("@/assets/cover/cover23.jpg"),
    items: [
      {
        src: require("@/assets/cover/car2.png"),
      },
      {
        src: require("@/assets/cover/car.png"),
      },
      {
        src: require("@/assets/cover/car3.png"),
      },
      {
        src: "https://cdn.vuetifyjs.com/images/carousel/planet.jpg",
      },
    ],
  }),
  methods: {
    reserve() {
      this.loading = true;

      setTimeout(() => (this.loading = false), 2000);
    },
  },
};
</script>
<style>
.hero {
  height: 500px;
  background-origin: center center;
  background-size: cover;
  background-position: center;
}
h3,
h2,
p {
  color: white;
}
</style>
