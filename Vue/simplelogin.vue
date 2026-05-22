<template>
  <v-app>
    <v-main>
      <v-container class="fill-height justify-center margin-center">
        <v-card width="400" class="pa-6">
          <v-card-title>Account Login</v-card-title>
          <v-text-field v-model="email" label="Email" variant="outlined"></v-text-field>
          <v-text-field v-model="password" label="Password" type="password" variant="outlined"></v-text-field>
          <v-btn color="primary" class="mt-4" block @click="handleLogin">Login</v-btn>
        </v-card>
      </v-container>   
 </v-main>
  </v-app>
</template>

<script setup>
import {ref} from 'vue'
import 'vuetify/styles'

const email=ref('')
const password=ref('')

function handleLogin(){
  if (email.value=== '') {
    alert('Please enter your email password')
    return  
  } else {
    if(password.value.length<6){
      alert('Password must be at least 6 character long')
      return
    }
    else{
      alert ('login successful')
    }
  }
}
</script>