<template>
  <v-app>
<NavBar />
<v-container fluid>
  <v-card
        color="#F7F7F7"
        height="180px"
        tile
        flat
        class="d-flex align-center justify-center mt-12"
        dark
      >
        <v-row>
          <v-col cols="12" sm="12">
            <v-item-group mandatory class="mt-n1">
              <v-container>
                <v-row justify="center" class="space">
                  <v-col
                    cols="12"
                    xs="12"
                    sm="4"
                    md="2"
                    v-for="(cetegory, i) in categories"
                    :key="i"
                  >
                    <v-item v-slot="{ active, toggle }">
                      <v-card
                        :color="active ? '#D5F0DB' : 'white'"
                        :class="active ? 'borderme' : 'borderout'"
                        class="d-flex align-center rounded-lg mx-2"
                        dark
                        height="170"
                        @click="toggle"
                        flat
                      >
                        <v-row>
                          <v-col cols="12" sm="12">
                            <v-list-item three-line class="text-center">
                              <v-list-item-content>
                                <div align="center" justify="center">
                                  <v-img
                                    :src="cetegory.img"
                                    max-height="80"
                                    max-width="80"
                                    contain
                                  ></v-img>
                                </div>
                                <v-list-item-subtitle
                                  :class="
                                    active ? 'green--text' : 'black--text'
                                  "
                                  class="caption mt-4"
                                  >{{ cetegory.title }}</v-list-item-subtitle
                                >
                              </v-list-item-content>
                            </v-list-item>
                          </v-col>
                        </v-row>
                      </v-card>
                    </v-item>
                  </v-col>
                </v-row>
              </v-container>
            </v-item-group>
          </v-col>
        </v-row>
      </v-card>
      <v-toolbar color="transparent" dark class="mt-3">
        <v-checkbox v-model="chair" label="Available Products" class="check mt-4"></v-checkbox>
        <v-checkbox v-model="other" label="Unavailable Products" class="check mt-4"></v-checkbox>
        <v-divider vertical></v-divider>
        <v-btn variant="text">Genre
          <v-icon right class="ml-2 mt-n1">fas fa-caret-right</v-icon>
        </v-btn>
        <v-divider vertical></v-divider>
        <v-btn variant="text">Choose Record
          <v-icon right class="ml-2 mt-n1">fas fa-caret-right</v-icon>
        </v-btn>
        <v-divider vertical></v-divider>
       <span class="text-caption mx-2">Price till</span>
       <v-slider v-model="slider2" label="track-color" class="mt-5"></v-slider>
       <span class="text-caption mx-2">$9,700</span>
      </v-toolbar>
      <v-divider class=mt-2></v-divider>
      <v-toolbar color="transparent">
        <v-toolbar-title>Products</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn variant="text" color="grey">Sort by :</v-btn>
        <v-btn variant="text" color="">Name</v-btn>
        <v-btn variant="text" color="grey">Popularity</v-btn>
        <v-btn variant="text" color="grey">Price</v-btn>
      </v-toolbar>
      <v-row>
          <v-col cols="12" sm="3" v-for="(chair,i) in chairs" :key="i" >
              <v-card height="300" align="center" flat outlined tile>
                <v-img :src="chair.image" width="200" height="200" contain></v-img>
                <v-card-text class="mt-n1">
                  <strong>{{chair.title}}</strong>
                </v-card-text>
                <v-card-text class="mt-n4">
                  <strong>{{chair.price}}</strong>
                </v-card-text>
              </v-card>
          </v-col>
      </v-row>
      <v-divider></v-divider>
      <v-toolbar color="transparent">
        <v-toolbar-title class="text-caption">Show more products</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-icon color="grey" left class="mr-4 mt-n1">fas fa-long-arrow-alt-left</v-icon>
        <span class="text-caption">3</span>
        <v-icon color="grey" left class="ml-4 mt-n1 mr-2">fas fa-long-arrow-alt-right</v-icon>
      </v-toolbar>
</v-container>
<FooterView />
  </v-app>
  
</template>

<script>
import { defineComponent } from 'vue';

// Components
import NavBar from '@/components/NavBar.vue';
import FooterView from '@/components/FooterView.vue';

export default defineComponent({
  name: 'HomeView',
setup(){
  return {
    chair: true,
    other: false,
    slider2: 50,
    categories: [
    { img: "c16.png", title: "HATS" },
        { img: "c1.jpg", title: "RECORDS" },
        { img: "1.png", title: "SHOES" },
        { img: "c15.jpg", title: "SWEATERS" },
        { img: "7.png", title: "SIGNATURE" },
        { img: "8.png", title: "ACCESSORIES" },
    ],
    chairs:[
    {
          class: "pa-0",
          image: "c1.jpg",
          title: "Record 1",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c2.jpg",
          title: "Record 2",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c3.png",
          title: "Record 3",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c4.png",
          title: "Record 4",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c5.png",
          title: "Record 5",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c6.png",
          title: "Record 6",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c7.png",
          title: "Record 7",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c8.png",
          title: "Record 8",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c9.png",
          title: "Record 9",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c10.png",
          title: "Record 10",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c11.png",
          title: "Record 11",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c12.jpg",
          title: "Record 12",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c13.jpg",
          title: "Record 13",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c14.jpg",
          title: "Record 14",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c15.jpg",
          title: "Sweater",
          price: "$ 145.00",
        },
        {
          class: "pa-0",
          image: "c16.png",
          title: "Hat",
          price: "$ 145.00",
        },
    ]
  }
}, 
  components: {
    NavBar,
    FooterView
},
});
</script>
<style scoped>
  .v-container{
    width: 100%;
    padding: 16px 0px !important;
    margin-right: auto;
    margin-left: auto;
  }
  .v-card.borderme {
    border: 2px solid black !important;
  }
  .v-card.borderout {
    border: 1px solid #d5f0db !important;
  }
</style>