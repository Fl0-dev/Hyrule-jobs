<template>
  <div id="app">
    <div>
      {{ name }} - {{ age }}
    </div>
    <input type="text" v-model="newName" />
    <button @click="changeName">Change Name</button>
    <br>
    <input type="text" v-model="newAge" />
    <button @click="changeAge">Change Age</button>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const name = ref('Link')
const age = ref<number | string>(20)
const newName = ref('')
const newAge = ref('')

const changeName = () => {
  name.value = newName.value
}

const changeAge = () => {
  age.value = newAge.value
}
</script>
