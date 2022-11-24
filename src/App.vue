<template>

  <div class="page-wrapper">

    <div class="clock-wrapper">

      <h1>{{time}}</h1>

    </div>

    <h2>Jim Garner</h2>

  </div>
  
</template>

<script setup>
import { ref } from 'vue';

//Reactive variable
let time = ref()

const getTime = (() => {
  time.value = new Date
  time.value = time.value.toString()
  time.value = time.value.split(' ')
  time.value = time.value[4]
})

getTime()


setInterval(getTime, 1000)

</script>


<style lang="scss" >
@import url('https://fonts.googleapis.com/css2?family=Lato:wght@100;300;400&display=swap');

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.page-wrapper {
  height: 100vh;
  display: grid;
  place-content: center;
  background: #1a1a1a;
  position: relative;
}

h1 {
  font-size: 72px;
  font-family: 'Lato', sans-serif;
  font-weight: 100;
  color: white;
}

h2 {
  position: absolute;
  bottom: 10px;
  right: 10px;
  color: white;
  font-family: 'Lato', sans-serif;
  font-weight: 300;
  text-transform: uppercase;
  letter-spacing: 3px;
}
</style>
