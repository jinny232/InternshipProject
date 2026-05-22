<template>
  <v-app>
    <v-main>
      <v-container class="fill-height justify-center align-center">
        <v-card width="400" class="pa-6 elevation-4 rounded-lg text-center">
          <v-card-title class="text-h5 font-weight-bold mb-2">
            Hello ,{{ username||'Guest' }}!
          </v-card-title>
          <v-card-text>
            <v-text-field v-model="username" label="Enter your name" variant="outlined" clearable class="mb-4">
            </v-text-field>
            <p class="text-subtitle-1 mb-4">
              Current Count:<strong class="text-primary text-h4">{{ count }}</strong>
            </p>
          </v-card-text>
          <v-card-actions class="justify-center">
            <v-btn color="success" variant="elevated" size="large" @click="increment">
              Add 1
            </v-btn>
            <v-btn color="error" variant="outlined" size="large" @click="reset">
              Reset
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>

import {ref} from 'vue'
import 'vuetify/styles'

const username=ref('')
const count=ref(0)

function increment(){
  count.value++
}
function reset(){
  count.value=0
  username.value=''
}
</script>