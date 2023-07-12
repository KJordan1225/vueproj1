<template>  
  <div class="home">

    <h2>{{ appTitle }}</h2>

    <h3>{{ counterData.title }}:</h3>
    <div>
      <button @click="decreaseCounter(2)" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter(2)" class="btn">+</button>
    </div>

    <p>This counter is {{ oddOrEven }}</p>

    <div class="edit">
      <h4>Edit Counter Title:</h4>
      <input v-model="counterData.title" type="text">
    </div>
  </div> 
  
</template>

<script setup>
import { reactive, computed, watch } from 'vue'
import {useCounter} from '@/use/useCounter'

const appTitle = 'My Amazing Counter App'
const {counterData, oddOrEven, increaseCounter, decreaseCounter} =
  useCounter()

// const counter = ref(0)
// const counterTitle = ref('My Counter Title')


</script>

<!-- <script>
import { ref } from 'vue'

export default {
  setup() {
    const counter = ref(0)

    const increaseCounter = () => {
      counter.value++
    }

    const decreaseCounter = () => {
      counter.value--
    }


    return {
      counter,
      increaseCounter,
      decreaseCounter
    }
  }
}
</script> -->

<!-- <script>
  export default{
    data() {
      return {
        counter: 0
      }
    }, 
    methods: {
      increaseCounter() {
        this.counter++
      },
      decreaseCounter() {
        this.counter--
      }
    }
  }
</script> -->

<style>
  .home {
    text-align: center;
    padding: 20px;
  }

  .btn, .counter {
    font-size: 40px;
    margin: 10px;
  }

  .edit {
   margin-top: 60px; 
  }
</style>
