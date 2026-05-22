<template>
  <v-app>
    <v-main>
      <v-container class="fill-height justify-center">
        <v-row>
          <v-col cols="9">
            <v-text-field v-model="newTask" label="Enter Your task" variant="outline" clearable></v-text-field>
          </v-col>
          <v-col cols="3">
            <v-btn @click="addTask" color="success" block>
              Add
            </v-btn>
          </v-col>
        </v-row>

        <v-list class="w-100 mt-4 rounded-lg border">
          <v-list-item v-for="(task, index) in tasks" :key="index" class="py-2">
            
            <v-list-item-title class="text-body-1">{{ task }}</v-list-item-title>

            <template #append>
              <v-btn 
                icon="mdi-delete" 
                variant="text" 
                color="error" 
                @click="deleteTask(index)"
              ></v-btn>
            </template>

          </v-list-item>
        </v-list>
      </v-container>
    </v-main>
  </v-app>
</template>

<script setup>
import { ref } from 'vue'
import 'vuetify/styles'

import '@mdi/font/css/materialdesignicons.css' 

const newTask = ref('')
const tasks = ref(['Play MLBB', 'Practice Vue'])

function addTask() {
  if (newTask.value.trim() !== '') {
    tasks.value.push(newTask.value)
    newTask.value = ''
  }
}

function deleteTask(index) {
  tasks.value.splice(index, 1)
}
</script>