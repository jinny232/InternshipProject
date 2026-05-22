<template>
  <v-app>
    <v-main>
      <v-container class="fill-height justify-center align-center flex-col" style="max-width: 800px;">
        <div class="text-hf font-weight-bold text-center mb-6 text-primary">
          Explore  destination
          </div>
          <v-carousel height="400"  show-arrows="hover" class="rounded-xl elevation-3" >
          <v-carousel-item v-for="(item,index) in destinations" :key="index" :src="item.src" cover>
            <div d-flex fill-height align-end justify-center pb-10>
              <div text-h5 text-white bg-black px-4 and py-2 rounded-lg>
                {{ item.title }}

              </div>
            </div>
          </v-carousel-item>
        </v-carousel>

      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
import {ref} from 'vue'
import 'vuetify/styles'

const destinations=ref([
  {
    title:'Japan',
    src:'https://images.unsplash.com/photo-1549693578-d683be217e58?w=800'
  },
  {
    title:'Italy',
    src:'https://images.unsplash.com/photo-1516483638261-f4dbaf036963?w=800'
  },
  {
    title:'Maldives',
    src:'https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=800'
  }
])
</script>