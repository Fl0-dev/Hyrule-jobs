<template>
  <div id="app">
    <header>
      <div class="title">
        <img src="./assets/heart.svg" alt="site logo">
        <h1>Hyrule Jobs</h1>
      </div>
      <div class="order">
        <button @click="handleClick('title')">Order by title</button>
        <button @click="handleClick('salary')">Order by salary</button>
        <button @click="handleClick('location')">Order by location</button>
      </div>
    </header>
    <jobList :jobs="jobs" :order="order"/>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import { Job } from './types/Job'
import { OrderTerm } from './types/OrderTerm';
import JobList from './components/JobList.vue'

const jobs = ref<Job[]>([
  {
    id: '1',
    title: 'Farm worker',
    location: 'Lon Lon Ranch',
    salary: '30000',
  },
  {
    id: '2',
    title: 'Quarryman',
    location: 'Death Mountain',
    salary: '40000',
  },
  {
    id: '3',
    title: 'Flute player',
    location: 'The Lost Woods',
    salary: '35000',
  },
  {
    id: '4',
    title: 'FisherMan',
    location: 'Lake Hylia',
    salary: '21000',
  },
  {
    id: '5',
    title: 'Prison Guard',
    location: 'Gerudo Valley',
    salary: '32000',
  }
])
const order = ref<OrderTerm>('title')

const handleClick = (key: OrderTerm) => {
  
  order.value = key

}
</script>

<style>
  header {
    text-align: center;
  }
  header .order {
    margin-top: 20px;
  }
  button {
    margin: 0 10px;
    color: #1195c9;
    border: 3px solid #1195c9;
    background: #d5f0ff;
    padding: 8px 16px;
    border-radius: 4px;
    cursor: pointer;
    font-weight: bold;
  }
  header .title{
    display: flex;
    justify-content: center;
  }
  header img {
    width: 60px;
    margin-right: 20px;
  }
  header h1 {
    font-size: 3em;
  }
</style>
